---
description: Audience Manager需要使用HTTP伺服器對伺服器要求，以進行有效性的數位簽署。本文件說明如何使用私密金鑰簽署HTTP請求。
seo-description: Audience Manager需要使用HTTP伺服器對伺服器要求，以進行有效性的數位簽署。本文件說明如何使用私密金鑰簽署HTTP請求。
seo-title: 數位簽署HTTP要求
solution: Audience Manager
title: 數位簽署HTTP要求
uuid: 1183a70f-0c96-42cf-a4 f5-37a83 ffa1286
translation-type: tm+mt
source-git-commit: 9bf1f3771b6a4b9bb9a52149e812b37d1c8e27f8

---


# Digitally Signed `HTTP` Requests {#digitally-signed-http-requests}

Audience Manager requires the `HTTP` server-to-server requests to be digitally signed for validity. This document describes how you can sign `HTTP` requests with private keys.

## 概述 {#overview}

<!-- digitally_signed_http_requests.xml -->

Using a private key provided by you and shared with [!DNL Audience Manager], we can digitally sign the `HTTP` requests that are sent between [IRIS](../../../reference/system-components/components-data-action.md#iris) and your HTTP server. 如此可確保：

* **真實性**：只有具有私密金鑰([!UICONTROL IRIS])的傳送者才能傳送有效 `HTTP(S)` 訊息給合作夥伴。
* **訊息完整性**：使用此方法，即使在 `HTTP`訊息被扭曲的中間攻擊中，您仍能保護您的安全。

[!UICONTROL IRIS] 具有內建支援，可將按鍵旋轉為零， [如旋轉私密金鑰](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) 區段中所示。

## Information you need to provide {#info-to-provide}

For an `HTTP` real-time server-to-server destination, contact your [!DNL Audience Manager] consultant and specify:

* 用來簽署請求的索引鍵。
* `HTTP` 將在下方標題標題中放置產生簽名(X-Signature)的標題名稱。
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

## How it works {#how-it-works}

1. [!UICONTROL IRIS] 建立要傳送 `HTTP` 給合作夥伴的訊息。
1. [!UICONTROL IRIS] 根據 `HTTP` 訊息和合作夥伴傳達的私密金鑰建立簽名。
1. [!UICONTROL IRIS] 將 `HTTP(S)` 請求傳送給合作夥伴。此訊息包含簽名和實際訊息，如上述範例所示。
1. The partner server receives the `HTTP(S)` request. It reads the message body and the signature received from [!UICONTROL IRIS].
1. 合作夥伴伺服器會根據接收的訊息內文和私密金鑰重新計算簽名。See the [How to calculate the signature](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) section just below on how to achieve this.
1. Compare the signature created on the partner server (receiver) with the one received from [!UICONTROL IRIS] (sender).
1. If the signatures match, then the **authenticity** and **message integrity** have been validated. 只有具有私密金鑰的傳送者才能傳送有效的簽名(真實性)。此外，中間的男性無法修改訊息並產生新的有效簽名，因為他們沒有私密金鑰(訊息完整性)。

![](assets/iris-digitally-sign-http-request.png)

## How to calculate the signature {#calculate-signature}

[!DNL HMAC] (雜湊訊息驗證碼)是用於訊息簽署 [!UICONTROL IRIS] 的方法。建置和程式庫基本上都以每種程式設計語言提供。[!DNL HMAC] 沒有已知的擴充功能攻擊。See an example in [!DNL Java] below:

```
// Message to be signed.
// For GET type HTTP destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP destinations, the message used for signing will be the REQUEST_BODY.
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

[!DNL HMAC] 雜湊實作的RFC是 [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt)的。A test site: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (note that you have to [convert](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) the hex encoding to base64).

## Rotating the private key {#rotate-private-key}

基於安全理由，建議定期旋轉私密金鑰。您需要決定私密金鑰和旋轉期間。In order to achieve the key rotation with zero downtime, [!UICONTROL IRIS] supports adding multiple signature headers. 一個標題包含使用舊金鑰產生的簽名，另一個標題將包含使用新私密金鑰產生的簽名。詳細檢視下列步驟：

1. Partner communicates the new private key to [!DNL Adobe Audience Manager].
1. [!UICONTROL IRIS] 會開始傳送兩個簽名標題(一個使用舊金鑰，另一個使用新金鑰)。
1. 當您開始接收兩個標題後，您可以選擇捨棄舊金鑰，只看得到新簽名。
1. The old key is removed from [!DNL Audience Manager] and [!UICONTROL IRIS] only sends the new signature header. 按鍵已旋轉。

## Data used for signing {#data-signing}

`GET` 對於類型目的地，用於簽署的訊息將是 *REQUEST_ PATH+ QUERY StrING* (例如 */from-aam-s2s？sids=1,2，*3)。IRIS does not take into account the hostname or `HTTP` headers - these can be modified / misconfigured along the path or reported incorrectly.

`POST` 對於類型目的地，用於簽署的訊息是 *請求主體*。同樣地，會忽略標題或其他請求參數。
