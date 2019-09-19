---
description: 即時傳入資料擷取程式使用來自使用者瀏覽器的一連串HTTP要求，將資料傳入Audience Manager。
seo-description: 即時傳入資料擷取程式使用來自使用者瀏覽器的一連串HTTP要求，將資料傳入Audience Manager。
seo-title: 即時傳入資料擷取
solution: Audience Manager
title: 即時傳入資料擷取
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 即時傳入資料擷取 {#real-time-inbound-data-ingestion}

即時傳入資料擷取程式會使用來自使用 `HTTP` 者瀏覽器的一連串請求，將資料傳入Audience Manager。

<!-- c_rt_inbound_real_time.xml -->

傳入資料應格式化為稱為訊號的鍵值對。 通常，每個信號都映射到通過用戶介面或建立或管理的段 [!DNL API]。

## URL字串參數與語法 {#url-string-syntax}

傳入 [!DNL URL] 資料傳輸的變數應包含下列所述的變數。 在設 [定即時資料](../../../features/traits/create-onboarded-rule-based-traits.md) ，請記得在UI中建 [立特徵](../../../features/traits/trait-storage.md#create-trait-storage-folder)[!DNL Audience Manager] 和資料夾結構。

>[!NOTE]
>
>以實際參數值取代斜體內容。

| 參數 | 說明 |
|---|---|
| `<KEY>` | 機碼值配對中的唯一識別碼（例如性別、色彩、價格）。 |
| `<VAL>` | 屬於由索引鍵定義之資料集的變數（例如，性別=男性、色彩=綠色、價格=100） |

### URL語法

在即時傳入資料擷取程式中，正確格式的字串 [!DNL URL] 使用下列語法：

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
