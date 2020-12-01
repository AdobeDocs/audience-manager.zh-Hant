---
description: Audience Manager要求HTTP(S)伺服器對伺服器要求必須進行數位簽署，以取得有效性。 本檔案說明如何使用私密金鑰簽署HTTP要求。
seo-description: Audience Manager要求HTTP(S)伺服器對伺服器要求必須進行數位簽署，以取得有效性。 本檔案說明如何使用私密金鑰簽署HTTP(S)要求。
seo-title: 數位簽署的HTTP(S)要求
solution: Audience Manager
title: 數位簽署的HTTP(S)要求
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: 4877aa5391193ee2187609fdc9cb3740c91feb96
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---


# 數位簽署`HTTP(S)`請求{#digitally-signed-http-requests}

Audience Manager要求`HTTP(S)`伺服器對伺服器要求必須進行數位簽署，以取得有效性。 本檔案說明如何使用私密金鑰簽署`HTTP(S)`要求。

## 概述 {#overview}

<!-- digitally_signed_http_requests.xml -->

使用您提供並與[!DNL Audience Manager]共用的私密金鑰，我們可以數位簽署在[IRIS](../../../reference/system-components/components-data-action.md#iris)和HTTP(S)伺服器之間傳送的`HTTP(S)`要求。 這可確保：

* **真實性**:只有具有私密金鑰的傳送者([!UICONTROL IRIS])才能傳送有 `HTTP(S)` 效訊息給合作夥伴。
* **消息完整性**:使用這種方法，即使是 `HTTP`這樣，您也會受到保護，不受中間人攻擊，而資訊會被扭曲。

[!UICONTROL IRIS] 已內建支援在無停機情況下旋轉密鑰，如下方的旋 [轉專用密鑰](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) 部分所示。

## 提供{#info-to-provide}所需資訊

對於`HTTP(S)`即時伺服器到伺服器目標，請聯繫您的[!DNL Audience Manager]顧問並指定：

* 用來簽署請求的金鑰。
* 將保存生成簽名的`HTTP(S)`標題的名稱（下面示例標題中的X-Signature）。
* 可選：用於簽名的雜湊類型(md5、sha1、sha256)。

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

1. [!UICONTROL IRIS] 建立要 `HTTP(S)` 發送給合作夥伴的消息。
1. [!UICONTROL IRIS] 根據該訊息和該合 `HTTP(S)` 作夥伴所傳送的私密金鑰建立簽名。
1. [!UICONTROL IRIS] 將請求 `HTTP(S)` 發送給合作夥伴。此消息包含簽名和實際消息，如上例所示。
1. 合作夥伴伺服器接收`HTTP(S)`請求。 它讀取消息正文和從[!UICONTROL IRIS]接收的簽名。
1. 合作夥伴伺服器根據收到的消息正文和私鑰重新計算簽名。 請參閱下面的[如何計算簽名](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature)一節，瞭解如何實現此目標。
1. 比較在合作夥伴伺服器（接收方）上建立的簽名與從[!UICONTROL IRIS]（發送方）接收的簽名。
1. 如果簽名匹配，則&#x200B;**真實性**&#x200B;和&#x200B;**消息完整性**&#x200B;已經過驗證。 只有擁有私密金鑰的傳送者才能傳送有效的簽名（真實性）。 此外，中間人無法修改消息並生成新的有效簽名，因為他們沒有私鑰（消息完整性）。

![](assets/iris-digitally-sign-http-request.png)

## 如何計算簽名{#calculate-signature}

[!DNL HMAC] （基於散列的消息驗證代碼）是消息簽名 [!UICONTROL IRIS] 的方法。基本上每個程式設計語言都提供實作和程式庫。 [!DNL HMAC] 沒有已知的分機攻擊。請參閱以下[!DNL Java]中的範例：

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

用於[!DNL HMAC]散列實現的RFC是[https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt)。 測試網站：[https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac)（請注意，您必須將十六進位編碼轉換為base64）。[](https://tomeko.net/online_tools/hex_to_base64.php?lang=en)

## 旋轉私密金鑰{#rotate-private-key}

若要輪換私密金鑰，合作夥伴必須將新的私密金鑰傳達給其[!DNL Adobe Audience Manager]顧問。 舊密鑰從[!DNL Audience Manager]中刪除，而[!UICONTROL IRIS]只發送新簽名標題。 鍵已旋轉。

## 用於簽署{#data-signing}的資料

對於`GET`類型目標，用於簽名的消息將是&#x200B;*REQUEST_PATH + QUERY STRING*(例如，*/from-aam-s2s?sids=1,2,3*)。 IRIS未考慮主機名或`HTTP(S)`標題——這些標題可沿路徑修改／配置錯誤或報告錯誤。

對於`POST`類型目標，用於簽名的消息是&#x200B;*REQUEST BODY*。 同樣地，標題或其他請求參數也會被忽略。
