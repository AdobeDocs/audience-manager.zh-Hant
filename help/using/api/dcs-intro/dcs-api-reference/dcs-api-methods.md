---
description: 使用GET或POST方法將資料傳送至DCS API。
seo-description: 使用GET或POST方法將資料傳送至DCS API。
seo-title: DCS API 方法
solution: Audience Manager
title: DCS API 方法
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 6%

---

# [!DNL DCS] [!DNL API] 方法 {#dcs-api-methods}

使用`GET`或`POST`方法將資料傳送至[!DNL DCS] [!DNL API]。

您可以使用`GET`或`POST`方法之一，將資料傳送至[!DNL DCS]。 請使用[curl](https://curl.haxx.se/)查看下方的範例呼叫。 在所有三個範例呼叫中，我們會將訊號`c_likes = famous popstar`和`c_loves = famous actress`新增至裝置設定檔`12345678901234567890123456789012345678`。

## 透過[!DNL GET] {#send-data-via-get}傳送資料

請注意，`GET`呼叫的允許大小上限為8K。

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## 透過[!DNL POST] {#send-data-via-post}傳送資料

請注意使用`POST`方法傳送資料的需求：

* 允許的最大大小為32K。
* 將內容類型設定為`application/x-www-form-urlencoded`。

### 呼叫範例

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
