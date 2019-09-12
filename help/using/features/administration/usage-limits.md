---
description: Audience Manager會設定您可以為帳戶建立的特性、區段、目的地和演算法模型數目上限。限制適用於這些項目，無論是在使用者介面中建立，還是透過API方法程式設計。使用限制可協助Audience Manager保護Audience Manager，以免嘗試破壞我們的API或使用者介面。
seo-description: Audience Manager會設定您可以為帳戶建立的特性、區段、目的地和演算法模型數目上限。限制適用於這些項目，無論是在使用者介面中建立，還是透過API方法程式設計。使用限制可協助Audience Manager保護Audience Manager，以免嘗試破壞我們的API或使用者介面。
seo-title: 使用量限制
solution: Audience Manager
title: 使用量限制
keywords: ID對應、ID映射、Cookie對應
uuid: 50ca 46477-b5 c-409c-89fa-4fa1799 b3222
translation-type: tm+mt
source-git-commit: d893998e9e59dbce64195a167e267c6f7ed16f90

---


# 使用量限制 {#usage-limits}

Audience Manager會設定您可以為帳戶建立的特性、區段、目的地和演算法模型數目上限。限制適用於這些項目，無論是在使用者介面中建立，還是透過 [!DNL API] 方法編寫。使用限制有助於保護Audience Manager，避免可能嘗試危及我們 [!DNL API]或使用者介面的自動化程序。

## ID 對應限制 {#id-mapping-limits}

下表列出裝置ID [的ID對應](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) 限制。一旦ID達到以下任何限制後，Audience Manager會根據( [!DNL FIFO] 第一個登出)邏輯新增ID映射，方法是移除最舊儲存的ID對應，並新增新的ID對應。請參閱Audience Manager中的ID [](../../reference/ids-in-aam.md) 索引，以取得Audience Manager支援之ID的詳細資訊。

| ID對應 | 上限上限 |
|-----------|-------------- |
| 裝置廣告ID(DAID)至跨裝置ID(CRM ID) | 100個裝置廣告ID(DAID)至跨裝置ID(CRM ID) |
| 跨裝置ID(CRM ID)至裝置廣告ID(DAID) | 10跨裝置ID(CRM ID)到裝置廣告ID(DAID) |
| Cookie/瀏覽器ID至Cookie/瀏覽器ID | 1000Cookie/瀏覽器ID至Cookie/瀏覽器ID |

## 項目限制 {#item-limits}

表格依項目類型列出目前限制。您無法建立新特性、區段、目的地，也 [!UICONTROL Algorithmic Models] 無法建立其中一個項目的特定限制。如果您達到限制，您必須先刪除舊項目，才能建立新的項目。

### 特徵限制

| 特徵類型 | 上限上限 |
| -------------------------- | ------------------------------------- |
| 總特徵 | 100,000 |
| 特徵總數 | 150,000. 如需特徵資格的詳細資訊，請參閱特徵資格參考中 [的特徵資格限制](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit)。 |
| 演算法 | 50 |
| 規則型 | 100,000 |
| 已登錄 | 100,000 |
| 資料夾特性 | 2,000 |

### 區段限制

| 區段類型 | 上限上限 |
| -------------- | ------------- |
| 區段總計 | 20,000 |

### 目的地限制

| 目的地類型 | 上限上限 |
| ------------------ | ------------- |
| 目的地總數 | 1,000 |
| Cookie | 1,000 |
| URL | 1,000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### 演算法模型限制

| 項目 | 上限上限 |
| -------- | ----- |
| 作用中演算法模型 | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| 演算法模型最大受眾規模 | 25,000,000.  請注意，此限制無法增加。您可以選擇較少的模型資料來源，或選擇較短的回顧視窗，來減少對象大小。 |
| 模型的排除特性上限 | 500. 請參閱 [演算法模型中的特徵排除](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)。 |

### 資料夾限制

| 項目 | 上限上限 |
| ------------- | ------------------ |
| 特徵檔案夾 | 2,000.  您的檔案夾結構最多可深至個層級。 |

### 衍生訊號限制

| 項目 | 上限上限 |
| --------------- | ------------- |
| 衍生訊號 | 50,000. |

### 公司使用者帳戶限制

| 項目 | 上限上限 |
| ----------- | ------------- |
| 公司的使用者帳戶數目上限 | 1,000. |

## 監視器使用狀況 {#monitor-usage}

您可以查看帳戶的使用情況和限制 **[!UICONTROL Administration > Limits]**。存取權限需要管理員權限。

![使用量限制影像](assets/usage-limits.png)

## 增加項目限制 {#increase-item-limits}

此處列出的預設限制應能提供您企業需求的足夠容量。如果貴組織持續達到這些限制，請聯絡您的帳戶代表討論增加。