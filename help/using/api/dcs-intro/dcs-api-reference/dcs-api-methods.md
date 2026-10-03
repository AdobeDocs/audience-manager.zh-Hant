---
description: 使用GET或POST方法將資料傳送至DCS API。
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: DCS API方法
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
TQID: 'https://experienceleague.adobe.com/dERIW4EM4-oMg8p33N2dtDy5BBw3jF1BCQJstW2cZTY'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
    internal-label: Data Collection Server
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 0%
---
# [!DNL DCS] [!DNL API]方法 {#dcs-api-methods}

使用`GET`或`POST`方法將資料傳送至[!DNL DCS] [!DNL API]。

您可以使用`GET`或`POST`方法之一將資料傳送至[!DNL DCS]。 使用[curl](https://curl.haxx.se/)，檢視下列範例呼叫。 在所有三個範例呼叫中，我們將訊號`c_likes = famous popstar`和`c_loves = famous actress`新增至裝置設定檔`12345678901234567890123456789012345678`。

## 透過[!DNL GET]傳送資料 {#send-data-via-get}

請注意，`GET`個呼叫允許的大小上限為8K。

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## 透過[!DNL POST]傳送資料 {#send-data-via-post}

注意使用`POST`方法傳送資料的需求：

* 允許的大小上限為32K。
* 將內容型別設定為`application/x-www-form-urlencoded`。

### 呼叫範例

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
