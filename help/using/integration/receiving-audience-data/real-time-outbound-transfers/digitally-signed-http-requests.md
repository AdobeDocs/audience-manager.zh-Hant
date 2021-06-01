---
description: Audience Manager要求對HTTP(S)伺服器對伺服器要求進行數位簽署，以確保有效性。 本檔案說明如何使用私密金鑰簽署HTTP請求。
seo-description: Audience Manager要求對HTTP(S)伺服器對伺服器要求進行數位簽署，以確保有效性。 本檔案說明如何使用私密金鑰簽署HTTP(S)請求。
seo-title: 數位簽署的HTTP(S)要求
solution: Audience Manager
title: 數位簽署的HTTP(S)要求
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: 傳出資料傳輸
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---

# 數字簽名`HTTP(S)`請求{#digitally-signed-http-requests}

Audience Manager要求對`HTTP(S)`伺服器對伺服器請求進行數字簽名以確保有效。 本檔案說明如何使用私密金鑰簽署`HTTP(S)`請求。

## 概述 {#overview}

<!-- digitally_signed_http_requests.xml -->

使用您提供並與[!DNL Audience Manager]共用的私密金鑰，我們可以數位簽署在[IRIS](../../../reference/system-components/components-data-action.md#iris)和您的HTTP(S)伺服器之間傳送的`HTTP(S)`請求。 這可確保：

* **真實性**:只有具有私密金鑰([!UICONTROL IRIS])的傳送者才能傳送有 `HTTP(S)` 效的訊息給合作夥伴。
* **消息完整性**:使用這種方法，即使 `HTTP`是在中間攻擊時，您也能受到保護，這樣消息就會被扭曲。

[!UICONTROL IRIS] 已內建支援零停機時旋轉金鑰，如下方「旋轉私 [密金鑰」](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) 一節所示。

## 需要提供{#info-to-provide}的資訊

有關`HTTP(S)`即時伺服器對伺服器目標的資訊，請與[!DNL Audience Manager]顧問聯繫，並指定：

* 用來簽署要求的金鑰。
* 將保存生成簽名的`HTTP(S)`標頭的名稱（下面示例標頭中的X-Signature）。
* 可選：用於簽名的哈希類型(md5、sha1、sha256)。

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

## 其運作方式{#how-it-works}

1. [!UICONTROL IRIS] 建立 `HTTP(S)` 要傳送給合作夥伴的訊息。
1. [!UICONTROL IRIS] 根據該消息和該合 `HTTP(S)` 作夥伴傳送的私鑰建立簽名。
1. [!UICONTROL IRIS] 傳送要 `HTTP(S)` 求給合作夥伴。如上例所示，此訊息包含簽名和實際訊息。
1. 合作夥伴伺服器接收`HTTP(S)`請求。 它讀取消息正文和從[!UICONTROL IRIS]接收的簽名。
1. 夥伴伺服器根據收到的消息正文和私鑰重新計算簽名。 請參閱下方的[如何計算簽名](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature)一節，了解如何達成此目標。
1. 將在合作夥伴伺服器（接收方）上建立的簽名與從[!UICONTROL IRIS]（發送方）接收的簽名進行比較。
1. 如果簽名匹配，則&#x200B;**真實性**&#x200B;和&#x200B;**消息完整性**&#x200B;已通過驗證。 只有具有私鑰的發送者才能發送有效的簽名（真實性）。 此外，中間人無法修改消息並生成新的有效簽名，因為他們沒有私鑰（消息完整性）。

![](assets/iris-digitally-sign-http-request.png)

## 如何計算簽名{#calculate-signature}

[!DNL HMAC] （雜湊型訊息驗證程式碼）是用於訊息簽署 [!UICONTROL IRIS] 的方法。實作和程式庫基本上都可使用所有程式設計語言。 [!DNL HMAC] 沒有已知的擴充功能攻擊。請參閱下方的[!DNL Java]範例：

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

[!DNL HMAC]雜湊實作的RFC為[https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt)。 測試網站：[https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac)（請注意，您必須將十六進位編碼轉換為base64）。[](https://tomeko.net/online_tools/hex_to_base64.php?lang=en)

## 旋轉私鑰{#rotate-private-key}

若要輪換私密金鑰，合作夥伴必須將新私密金鑰傳達給其[!DNL Adobe Audience Manager]顧問。 舊密鑰從[!DNL Audience Manager]中刪除，而[!UICONTROL IRIS]只發送新簽名標頭。 已旋轉鍵。

## 用於簽名{#data-signing}的資料

對於`GET`類型目的地，用於簽署的訊息將是&#x200B;*REQUEST_PATH + QUERY STRING*(例如&#x200B;*/from-aam-s2s?sids=1,2,3*)。 IRIS未考慮主機名或`HTTP(S)`標題 — 這些標題可能沿路徑修改/配置錯誤，或報告錯誤。

對於`POST`類型目的地，用於簽署的訊息為&#x200B;*REQUEST BODY*。 同樣地，標題或其他要求參數也會遭到忽略。
