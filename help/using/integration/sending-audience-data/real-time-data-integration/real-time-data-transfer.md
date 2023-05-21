---
description: 即時入站資料接收過程使用用戶瀏覽器的一系列HTTP請求將資料傳遞到Audience Manager。
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: 即時傳入資料擷取
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 5%

---

# 即時傳入資料擷取 {#real-time-inbound-data-ingestion}

即時入站資料接收過程使用一系列 `HTTP` 從用戶瀏覽器向Audience Manager傳遞資料的請求。

<!-- c_rt_inbound_real_time.xml -->

入站資料應格式化為稱為信號的鍵值對。 通常，每個信號被映射到通過用戶介面建立或管理的段，或 [!DNL API]。

## URL字串參數和語法 {#url-string-syntax}

的 [!DNL URL] 對於入站資料傳輸，應包含下面描述的變數。 記住 [創造性狀](../../../features/traits/create-onboarded-rule-based-traits.md) 和 [資料夾結構](../../../features/traits/trait-storage.md#create-trait-storage-folder) 的 [!DNL Audience Manager] 設定即時資料傳輸前的UI。

>[!NOTE]
>
>用實際參數值替換斜體內容。

| 參數 | 說明 |
|---|---|
| `<KEY>` | 鍵值對（例如性別、顏色、價格）中的唯一標識符。 |
| `<VAL>` | 屬於由鍵定義的資料集的變數（例如，性別=男性，顏色=綠色，價格=100） |

### URL語法

在即時入站資料接收過程中， [!DNL URL] string使用以下語法：

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
