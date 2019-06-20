---
description: Audience Manager會設定您可以為帳戶建立的特性、區段、目的地和演算法模型數目上限。限制適用於這些項目，無論是在使用者介面中建立，還是透過API方法程式設計。使用限制可協助Audience Manager保護Audience Manager，以免嘗試破壞我們的API或使用者介面。
seo-description: Audience Manager會設定您可以為帳戶建立的特性、區段、目的地和演算法模型數目上限。限制適用於這些項目，無論是在使用者介面中建立，還是透過API方法程式設計。使用限制可協助Audience Manager保護Audience Manager，以免嘗試破壞我們的API或使用者介面。
seo-title: 使用量限制
solution: Audience Manager
title: 使用量限制
topic: DIL API
uuid: 50ca 46477-b5 c-409c-89fa-4fa1799 b3222
translation-type: tm+mt
source-git-commit: a9550d71bbc6adf939539df05cd38a9d22ef261b

---


# Usage Limits {#usage-limits}

Audience Manager會設定您可以為帳戶建立的特性、區段、目的地和演算法模型數目上限。Limits apply to these items whether created in the user interface or programmatically through [!DNL API] methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our [!DNL API]s or user interface.

## ID 對應限制 {#id-mapping-limits}

The table below lists the [ID mapping](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) limits for device IDs. Once an ID reaches any of the limits below, Audience Manager adds new ID mappings based on a [!DNL FIFO] (first in, first out) logic, by removing the oldest stored ID mapping, and adds the new one. Refer to [Index of IDs](../../reference/ids-in-aam.md) in Audience Manager for details on the IDs supported by Audience Manager.

| ID對應 | 上限上限 |
|-----------|-------------- |
| 裝置廣告ID(DAID)至跨裝置ID(CRM ID) | 100個裝置廣告ID(DAID)至跨裝置ID(CRM ID) |
| 跨裝置ID(CRM ID)至裝置廣告ID(DAID) | 10跨裝置ID(CRM ID)到裝置廣告ID(DAID) |
| Cookie/瀏覽器ID至Cookie/瀏覽器ID | 1000Cookie/瀏覽器ID至Cookie/瀏覽器ID |

## Item Limits {#item-limits}

表格依項目類型列出目前限制。You cannot create new traits, segments, destinations, or [!UICONTROL Algorithmic Models] if you reach a specific limit for one of these items. 如果您達到限制，您必須先刪除舊項目，才能建立新的項目。

### 特徵限制

| 特徵類型 | 上限上限 |
| -------------------------- | ------------------------------------- |
| 總特徵 | 100,000 |
| 特徵總數 | 150,000. For more information on trait qualification, see Trait Qualification Limit in [Trait Qualifications Reference](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit). |
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
| 模型的排除特性上限 | 500. See [Trait Exclusion in Algorithmic Modeling](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |

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

## Monitor Usage {#monitor-usage}

You can see usage and limits for your account by going to **[!UICONTROL Administration > Limits]**. 存取權限需要管理員權限。

![使用量限制影像](assets/usage-limits.png)

## Increase Item Limits {#increase-item-limits}

此處列出的預設限制應能提供您企業需求的足夠容量。如果貴組織持續達到這些限制，請聯絡您的帳戶代表討論增加。