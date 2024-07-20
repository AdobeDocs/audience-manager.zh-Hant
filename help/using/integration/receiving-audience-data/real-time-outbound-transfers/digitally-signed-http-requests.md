---
description: Audience Manager需要對HTTP(S)伺服器對伺服器要求進行數位簽署以確認有效性。 本檔案說明如何使用私密金鑰簽署HTTP請求。
seo-description: Audience Manager requires the HTTP(S) server-to-server requests to be digitally signed for validity. This document describes how you can sign HTTP(S) requests with private keys.
seo-title: Digitally Signed HTTP(S) Requests
solution: Audience Manager
title: 數位簽署的HTTP(S)請求
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 0%

---

# 數位簽署的`HTTP(S)`個要求 {#digitally-signed-http-requests}

Audience Manager需要數位簽署`HTTP(S)`伺服器對伺服器要求才能有效。 本檔案說明如何使用私密金鑰簽署`HTTP(S)`請求。

## 概述 {#overview}

<!-- digitally_signed_http_requests.xml -->

我們可以使用您提供並與[!DNL Audience Manager]共用的私密金鑰，以數位方式簽署在[IRIS](../../../reference/system-components/components-data-action.md#iris)與您的HTTP(S)伺服器之間傳送的`HTTP(S)`個要求。 這可確保：

* **認證**：只有擁有私密金鑰([!UICONTROL IRIS])的寄件者才能傳送有效的`HTTP(S)`郵件給合作夥伴。
* **訊息完整性**：使用此方法，即使在`HTTP`上，您也會受到保護，不會受到中間人攻擊的訊息失真。

[!UICONTROL IRIS]已內建支援，可在零停機時間旋轉金鑰，如下方的[旋轉私密金鑰](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key)區段所示。

## 您需要提供的資訊 {#info-to-provide}

若為`HTTP(S)`即時伺服器對伺服器目的地，請連絡您的[!DNL Audience Manager]顧問並指定：

* 用來簽署要求的金鑰。
* 將保留所產生簽章的`HTTP(S)`標頭名稱（下方範例標頭中的X-Signature）。
* 可選：用於簽名的雜湊型別(md5、sha1、sha256)。

```
* Connected to partner.website.com (127.0.0.1) port 80 (#0)
> POST /webpage HTTP/1.1
> Host: partner.host.com
> Accept: */*
> Content-Type: application/json
> Content-Length: 20
> X-Signature: +wFdR/afZNoVqtGl8/e1KJ4ykPU=
POST message content
```

## 運作方式 {#how-it-works}

1. [!UICONTROL IRIS]建立要傳送給合作夥伴的`HTTP(S)`訊息。
1. [!UICONTROL IRIS]會根據`HTTP(S)`訊息和協力電腦所通訊的私密金鑰建立簽章。
1. [!UICONTROL IRIS]傳送`HTTP(S)`要求給合作夥伴。 此訊息包含簽名和實際訊息，如上面的範例所示。
1. 夥伴伺服器接收`HTTP(S)`要求。 讀取從[!UICONTROL IRIS]收到的郵件內文和簽章。
1. 合作夥伴伺服器會根據收到的訊息本文和私密金鑰重新計算簽章。 請參閱下方的[如何計算簽章](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature)一節，瞭解如何達成此目的。
1. 比較夥伴伺服器（接收者）上建立的簽章與從[!UICONTROL IRIS] （傳送者）收到的簽章。
1. 如果簽章相符，則已驗證&#x200B;**真實性**&#x200B;和&#x200B;**郵件完整性**。 只有擁有私密金鑰的寄件者才能傳送有效的簽章（真實性）。 此外，中間人無法修改訊息並產生新的有效簽章，因為他們沒有私密金鑰（訊息完整性）。

![](assets/iris-digitally-sign-http-request.png)

## 如何計算簽名 {#calculate-signature}

[!DNL HMAC] （雜湊式訊息驗證碼）是[!UICONTROL IRIS]用於訊息簽署的方法。 實作和程式庫基本上提供每種程式語言版本。 [!DNL HMAC]沒有已知的延伸攻擊。 請參閱以下[!DNL Java]中的範例：

```
// Message to be signed.
// For GET type HTTP(S) destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP(S) destinations, the message used for signing will be the REQUEST_BODY.
// String getData = "/from-aam-s2s?sids=1,2,3";
String postData = "POST message content";
// Algorithm used. Currently supported: HmacSHA1, HmacSHA256, HmacMD5.
String algorithm = "HmacSHA1";
// Private key shared between the partner and Adobe Audience Manager.
String key = "sample_partner_private_key";
  
// Perform signing.
SecretKeySpec signingKey = new SecretKeySpec(key.getBytes(), algorithm);
Mac mac = Mac.getInstance(algorithm);
mac.init(signingKey);
byte[] result = mac.doFinal(postData.getBytes());
  
String signature = Base64.encodeBase64String(result).trim(); 
// signature = +wFdR/afZNoVqtGl8/e1KJ4ykPU=
```

[!DNL HMAC]雜湊實作的RFC是[https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt)。 測試網站： [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) （請注意，您必須[將](https://tomeko.net/online_tools/hex_to_base64.php?lang=en)十六進位編碼轉換為base64）。

## 旋轉私密金鑰 {#rotate-private-key}

若要輪換私密金鑰，合作夥伴必須將新的私密金鑰傳達給其[!DNL Adobe Audience Manager]顧問。 舊金鑰已從[!DNL Audience Manager]中移除，[!UICONTROL IRIS]只會傳送新的簽章標題。 金鑰已旋轉。

## 用於簽署的資料 {#data-signing}

對於`GET`型別目的地，用於簽署的訊息將為&#x200B;*REQUEST_PATH +查詢字串* （例如&#x200B;*/from-aam-s2s？sids=1,2，3*）。 IRIS未考量主機名稱或`HTTP(S)`標題 — 這些可能會沿著路徑修改/錯誤設定或報告不正確。

對於`POST`型別目的地，用於簽署的訊息是&#x200B;*要求內文*。 同樣地，標頭或其他請求引數會被忽略。
