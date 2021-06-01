---
description: 即時傳入資料擷取程式會使用使用者瀏覽器的一系列HTTP要求，將資料傳入Audience Manager。
seo-description: 即時傳入資料擷取程式會使用使用者瀏覽器的一系列HTTP要求，將資料傳入Audience Manager。
seo-title: 即時傳入資料擷取
solution: Audience Manager
title: 即時傳入資料擷取
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: 傳入資料傳輸
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 8%

---

# 即時傳入資料擷取 {#real-time-inbound-data-ingestion}

即時傳入資料擷取程式會使用使用者瀏覽器的一系列`HTTP`請求，將資料傳入Audience Manager。

<!-- c_rt_inbound_real_time.xml -->

傳入資料的格式應為稱為訊號的機碼值組。 通常，每個信號都對應至透過使用者介面或[!DNL API]建立或管理的區段。

## URL字串參數和語法{#url-string-syntax}

傳入資料傳輸的[!DNL URL]應包含下述變數。 在設定即時資料傳輸之前，請記得在[!DNL Audience Manager] UI中[建立特徵](../../../features/traits/create-onboarded-rule-based-traits.md)和[資料夾結構](../../../features/traits/trait-storage.md#create-trait-storage-folder)。

>[!NOTE]
>
>將斜體內容取代為實際參數值。

| 參數 | 說明 |
|---|---|
| `<KEY>` | 機碼值組中的唯一識別碼（例如性別、顏色、價格）。 |
| `<VAL>` | 屬於索引鍵定義之資料集的變數（例如gender=male, color=green, price=100） |

### URL語法

在即時傳入資料擷取程式期間，格式正確的[!DNL URL]字串會使用下列語法：

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
