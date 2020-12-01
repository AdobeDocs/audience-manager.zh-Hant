---
description: 使用GET或POST方法將資料傳送至DCS API。
seo-description: 使用GET或POST方法將資料傳送至DCS API。
seo-title: DCS API 方法
solution: Audience Manager
title: DCS API 方法
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 6%

---


# [!DNL DCS] [!DNL API] 方法 {#dcs-api-methods}

使用`GET`或`POST`方法將資料傳送至[!DNL DCS] [!DNL API]。

您可以使用`GET`或`POST`方法之一，將資料傳送至[!DNL DCS]。 請使用[curl](https://curl.haxx.se/)查看以下範例呼叫。 在這三個示例調用中，我們將信號`c_likes = famous popstar`和`c_loves = famous actress`添加到設備配置檔案`12345678901234567890123456789012345678`中。

## 透過[!DNL GET] {#send-data-via-get}傳送資料

請注意，`GET`呼叫的最大允許大小為8K。

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## 透過[!DNL POST] {#send-data-via-post}傳送資料

請注意使用`POST`方法傳送資料的需求：

* 允許的最大大小為32K。
* 將內容類型設為`application/x-www-form-urlencoded`。

### 範例呼叫

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
