---
description: 使用GET或POST方法將資料傳送至DCS API。
seo-description: 使用GET或POST方法將資料傳送至DCS API。
seo-title: DCS API 方法
solution: Audience Manager
title: DCS API 方法
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 7%

---


# DCS API 方法 {#dcs-api-methods}

使用或方法 [!DNL DCS] 將資 [!DNL API] 料傳 `GET``POST` 送至。

您可以使用其中一 [!DNL DCS] 種或方法將資料 `GET` 傳送 `POST` 至。 請使用捲曲功能來檢視下面的範例 [呼叫](https://curl.haxx.se/)。 在這3個樣本呼叫中，我們會新增訊號 `c_likes = famous popstar` 並 `c_loves = famous actress` 加入裝置描述檔 `12345678901234567890123456789012345678`。


## 透過GET傳送資料 {#send-data-via-get}

請注意，呼叫的最大允 `GET` 許大小為8K。

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## 透過POST傳送資料 {#send-data-via-post}

請注意使用以下方法傳送資料的 `POST` 要求：

* 允許的最大大小為32K。
* 將內容類型設定為 `application/x-www-form-urlencoded`。

### 範例呼叫

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
