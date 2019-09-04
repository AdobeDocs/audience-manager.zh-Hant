---
description: 使用GET或POST方法將資料傳送至DCS API。
seo-description: 使用GET或POST方法將資料傳送至DCS API。
seo-title: DCS API方法
solution: Audience Manager
title: DCS API方法
uuid: 6e407458-11d4-4342-a84 a-512afa5 fc183
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# DCS API方法 {#dcs-api-methods}

傳送資料至 [!UICONTROL DCS][!DNL API] 使用 `GET` 或 `POST` 方法。

您可以使用其中 [!UICONTROL DCS] 一個 `GET` 或 `POST` 方法來傳送資料。檢視下面的範例呼叫，使用 [捲動](https://curl.haxx.se/)。在這三個範例呼叫中，我們新增了訊號 `c_likes = famous popstar` 和 `c_loves = famous actress` 裝置描述檔 `12345678901234567890123456789012345678`。

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 使用此方法傳送資料時，取代預留位置的 [!UICONTROL DCS] 實際值。

## 透過GET傳送資料 {#send-data-via-get}

請注意 `GET` ，允許的呼叫大小上限為8K。

<pre><code>curr -i「<i>yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&amp;d_rtbd=jsonc_likes=famous%20popstar&amp;c_loves=famous%20actress</i><i></i><i></i><i></i>」</code></pre>

## 透過POST傳送資料 {#send-data-via-post}

請注意使用 `POST` 此方法傳送資料的需求：

* 允許的大小上限為32K。
* 將內容類型設 `application/x-www-form-urlencoded`為。

### 範例呼叫

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
