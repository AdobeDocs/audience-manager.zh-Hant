---
description: 使用GET或POST方法將資料發送到DCS API。
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: DCS API 方法
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 4%

---

# [!DNL DCS] [!DNL API] 方法 {#dcs-api-methods}

將資料發送到 [!DNL DCS] [!DNL API] 使用 `GET` 或 `POST` 的雙曲餘切值。

您可以將資料發送到 [!DNL DCS] 使用 `GET` 或 `POST` 的雙曲餘切值。 查看下面的示例調用，使用 [捲曲](https://curl.haxx.se/)。 在所有的三個調用樣本中，我們 `c_likes = famous popstar` 和 `c_loves = famous actress` 到設備配置檔案 `12345678901234567890123456789012345678`。

## 通過 [!DNL GET] {#send-data-via-get}

請注意， `GET` 呼叫是8K

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## 通過 [!DNL POST] {#send-data-via-post}

請注意使用 `POST` 方法：

* 允許的最大大小為32K。
* 將內容類型設定為 `application/x-www-form-urlencoded`。

### 示例調用

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
