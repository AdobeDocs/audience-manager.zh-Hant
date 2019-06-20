---
description: 使用GET或POST方法將資料傳送至DCS API。
seo-description: 使用GET或POST方法將資料傳送至DCS API。
seo-title: DCS API方法
solution: Audience Manager
title: DCS API方法
uuid: 6e407458-11d4-4342-a84 a-512afa5 fc183
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS API Methods {#dcs-api-methods}

Send data to the [!UICONTROL DCS] [!DNL API] using `GET` or `POST` methods.

You can send data to the [!UICONTROL DCS] using either one of the `GET` or `POST` methods. Take a look at the sample calls below, using [curl](https://curl.haxx.se/). In all three sample calls, we are adding the signals `c_likes = famous popstar` and `c_loves = famous actress` to the device profile `12345678901234567890123456789012345678`.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitute a real value for the placeholder when you send data to the [!UICONTROL DCS] with this method.

## Send Data via GET {#send-data-via-get}

Note that the maximum allowed size for `GET` calls is 8K.

<pre><code>curr -i「<i>yourcompany.demdex.net/event</i>？
d_uuid=<i>12345678901234567890123456789012345678</i>&amp;d_rtbd=json&amp;<i>c_likes=famous%20popstar</i>&amp;<i>c_loves=famous%20actress</i>"
</code></pre>

## Send Data via POST {#send-data-via-post}

Note the requirements for sending data using the `POST` method:

* 允許的大小上限為32K。
* Set the content type to `application/x-www-form-urlencoded`.

### 範例呼叫

<pre><code>curr -X POST\
https://yourcompany.demdex.net/event<i></i>\
-H'content-type：application/x-www-form-urlcoded'\\'5 c
-d'<i>c_ likes=著名的%20popstore</i>&amp;<i>c_ loves=著名的%20actress</i>&amp;<i>d_ uuid=12345678891234567801212345678</i>'</code>
</pre>

<pre><code>curr -X POST\
https://yourcompany.demdex.net/event<i></i>\
-H'content-type：application/x-www-form-urlcoded'\\'5 c
-d'<i>c_ likes=著名的%20popstore</i>&amp; <i>c_ loves=著名的%20actress</i>&amp;<i>d_ uuid=12345678891234567801212345678</i>'</code>
</pre>
