---
description: Audience Manager要求對HTTP(S)伺服器到伺服器請求進行數字簽名以獲得有效性。 本文檔介紹如何使用私鑰對HTTP請求進行簽名。
seo-description: Audience Manager requires the HTTP(S) server-to-server requests to be digitally signed for validity. This document describes how you can sign HTTP(S) requests with private keys.
seo-title: Digitally Signed HTTP(S) Requests
solution: Audience Manager
title: 數字簽名的HTTP請求
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 0%

---

# 數字簽名 `HTTP(S)` 請求 {#digitally-signed-http-requests}

Audience Manager要求 `HTTP(S)` 要對伺服器到伺服器請求進行數字簽名以獲得有效性。 本文檔介紹如何簽名 `HTTP(S)` 使用私鑰的請求。

## 概述 {#overview}

<!-- digitally_signed_http_requests.xml -->

使用由您提供並與共用的私鑰 [!DNL Audience Manager]我們可以用數字簽名 `HTTP(S)` 在以下時間間發送的請求 [虹膜](../../../reference/system-components/components-data-action.md#iris) 和HTTP伺服器。 這確保：

* **真實性**:僅具有私鑰的發件人([!UICONTROL IRIS]可以發送有效 `HTTP(S)` 給合作夥伴的消息。
* **消息完整性**:用這種方法，甚至 `HTTP`但是，在消息被扭曲的中間攻擊中，您受到保護。

[!UICONTROL IRIS] 內置支援，可在零停機時旋轉密鑰，如 [旋轉私鑰](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) 的下界。

## 您需要提供的資訊 {#info-to-provide}

對於 `HTTP(S)` 即時伺服器到伺服器目標，請與 [!DNL Audience Manager] 顧問並指定：

* 用於簽名請求的密鑰。
* 名稱 `HTTP(S)` 將保存生成的簽名的標頭（下面示例標頭中的X-Signature）。
* 可選：用於簽名的散列類型(md5、sha1、sha256)。

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

## 它的工作原理 {#how-it-works}

1. [!UICONTROL IRIS] 建立 `HTTP(S)` 要發送給合作夥伴的消息。
1. [!UICONTROL IRIS] 建立簽名 `HTTP(S)` 消息和合作夥伴傳遞的私鑰。
1. [!UICONTROL IRIS] 發送 `HTTP(S)` 請求合作夥伴。 此消息包含簽名和實際消息，如上例所示。
1. 夥伴伺服器接收 `HTTP(S)` 請求。 它讀取消息正文和從 [!UICONTROL IRIS]。
1. 夥伴伺服器基於接收到的消息正文和私鑰重新計算簽名。 查看 [如何計算簽名](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) 下面部分介紹如何實現此目標。
1. 將在夥伴伺服器（接收方）上建立的簽名與從 [!UICONTROL IRIS] （發件人）。
1. 如果簽名匹配，則 **真實性** 和 **消息完整性** 已驗證。 只有具有私鑰的發件人才能發送有效簽名（真實性）。 此外，中間人無法修改消息並生成新的有效簽名，因為他們沒有私鑰（消息完整性）。

![](assets/iris-digitally-sign-http-request.png)

## 如何計算簽名 {#calculate-signature}

[!DNL HMAC] （基於哈希的消息驗證代碼）是 [!UICONTROL IRIS] 為消息簽名。 實現和庫基本上在每種寫程式語言中都可用。 [!DNL HMAC] 沒有已知的分機攻擊。 請參閱中的示例 [!DNL Java] 以下：

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

RFC [!DNL HMAC] 哈希實現 [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt)。 test站點： [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (請注意，您必須 [轉換](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) 十六進位編碼到base64)。

## 旋轉私鑰 {#rotate-private-key}

要輪替私鑰，合作夥伴必須將新私鑰與其 [!DNL Adobe Audience Manager] 顧問。 舊密鑰已從 [!DNL Audience Manager] 和 [!UICONTROL IRIS] 只發送新簽名標頭。 鑰匙已旋轉。

## 用於簽名的資料 {#data-signing}

對於 `GET` 類型目標，用於簽名的消息將 *REQUEST_PATH +查詢字串* (例如 */from aam-s2s?sids=1,2,3*)。 IRIS未考慮主機名或 `HTTP(S)` 標頭 — 這些標頭可以沿路徑修改/配置錯誤或報告錯誤。

對於 `POST` 類型目標，用於簽名的消息是 *請求正文*。 同樣，忽略標頭或其他請求參數。
