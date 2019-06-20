---
description: 即時傳入資料擷取程序使用使用者瀏覽器中的一系列HTTP要求，將資料傳遞至Audience Manager。
seo-description: 即時傳入資料擷取程序使用使用者瀏覽器中的一系列HTTP要求，將資料傳遞至Audience Manager。
seo-title: 即時傳入資料擷取
solution: Audience Manager
title: 即時傳入資料擷取
uuid: 43cb0ebc-6c36-4391-bbfb-6b203 d63 c69 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Real-Time Inbound Data Ingestion {#real-time-inbound-data-ingestion}

The real-time inbound data ingestion process uses a series of `HTTP` requests from a user&#39;s browser to pass in data to Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

傳入資料的格式應為稱為「訊號」的索引鍵值配對。Typically, each signal is mapped to a segment created or managed through the user interface or [!DNL API].

## URL String Parameters and Syntax {#url-string-syntax}

The [!DNL URL] for an inbound data transfer should contain the variables described below. Remember to [create traits](../../../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../../../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI before setting up real-time data transfers.

>[!NOTE]
>
>使用實際參數值取代斜體內容。

| 參數 | 說明 |
|---|---|
| `<KEY>` | 關鍵值配對中的唯一識別碼(例如性別、顏色、價格)。 |
| `<VAL>` | 屬於由索引鍵定義之資料集的變數(例如，gender=男性，color= green，price=100) |

### URL語法

During a real-time inbound data ingestion process, a properly formatted [!DNL URL] string uses the following syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
