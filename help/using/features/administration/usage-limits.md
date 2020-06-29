---
description: Audience Manager會設定您可以為帳戶建立的特徵、區段、目的地和演算法模型數目上限。 不論是在使用者介面中建立，或是透過API方法以程式設計方式建立，限制都適用於這些項目。 使用限制有助於保護Audience Manager不受可能破壞我們API或使用者介面的自動化程式。
seo-description: Audience Manager會設定您可以為帳戶建立的特徵、區段、目的地和演算法模型數目上限。 不論是在使用者介面中建立，或是透過API方法以程式設計方式建立，限制都適用於這些項目。 使用限制有助於保護Audience Manager不受可能破壞我們API或使用者介面的自動化程式。
seo-title: 使用量限制
solution: Audience Manager
title: 使用量限制
keywords: ID mapping, ID mappings, cookie mappings
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 6%

---


# 使用量限制 {#usage-limits}

Audience Manager會設定您可以為帳戶建立的特徵、區段、目的地和演算法模型數目上限。 不論是在使用者介面中建立，或是透過程式設計方式建立，限制都適用於這些 [!DNL API] 項目。 使用限制有助於保護Audience Manager不受可能破壞我們或使用者介面的 [!DNL API]自動化程式。

## ID 對應限制 {#id-mapping-limits}

下表列出裝置 [ID的](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) ID對應限制。 一旦ID達到下列任一限制，Audience Manager會根據 [!DNL FIFO] （先入先出）邏輯新增ID對應，方法是移除最舊儲存的ID對應，然後新增新的ID對應。 如需Audience Manager [支援之ID的詳細資訊](../../reference/ids-in-aam.md) ，請參閱Audience Manager中的ID索引。

| ID對應 | 最大限制 |
|-----------|-------------- |
| 跨裝置ID([DPUUID](../../reference/ids-in-aam.md))的裝置廣告ID([DAID](../../reference/ids-in-aam.md)) | 100個裝置廣告ID([DAID](../../reference/ids-in-aam.md))至1個跨裝置ID([DPUUID](../../reference/ids-in-aam.md)) |
| 跨裝置ID([DPUUID](../../reference/ids-in-aam.md))到裝置廣告ID([DAID](../../reference/ids-in-aam.md)) | 每個DPID有10個跨裝[置ID](../../reference/ids-in-aam.md)([DPUUID](../../reference/ids-in-aam.md))至1個裝置廣告ID( [DAID)](../../reference/ids-in-aam.md) |
| Cookie/瀏覽器ID至Cookie/瀏覽器ID | 1000個Cookie/瀏覽器ID至1個Cookie/瀏覽器ID |

## 項目限制 {#item-limits}

這些表按項目類型列出當前限制。 您無法建立新特徵、區段、目的地， [!UICONTROL Algorithmic Models] 或者如果您達到其中一個項目的特定限制。 如果您達到限制，您必須先刪除舊項目，才能建立新項目。

### 特徵限制

| 特徵類型 | 最大限制 |
| -------------------------- | ------------------------------------- |
| 總特徵 | 100,000 |
| 特徵資格總計 | 150,000. 如需特徵資格的詳細資訊，請參閱特徵資格參考中的特 [徵資格限制](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)。 |
| 演算法 | 50 |
| 規則型 | 100,000 |
| 已登錄 | 100,000 |
| 資料夾特徵 | 2,000 |

### 區段限制

| 區段類型 | 最大限制 |
| -------------- | ------------- |
| 區段總計 | 20,000 |

### 目標限制

| 目標類型 | 最大限制 |
| ------------------ | ------------- |
| 目標總數 | 1,000 |
| Cookie | 1,000 |
| URL | 1,000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### 演算法模型限制

| 項目 | 最大限制 |
| -------- | ----- |
| 作用中演算法模型 | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| 演算法模型最大受眾規模 | 25,000,000.  請注意，此限制無法增加。 您可以透過為模型選取較少的資料來源或選擇較短的回顧視窗，來降低觀眾規模。 |
| 模型的已排除特徵數上限 | 500. 請參閱 [演算法模型中的特徵排除](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)。 |

### 資料夾限制

| 項目 | 最大限制 |
| ------------- | ------------------ |
| 特徵資料夾 | 2,000.  您的檔案夾結構最多可以有5層深。 |

### 衍生的信號限制

| 項目 | 最大限制 |
| --------------- | ------------- |
| 衍生訊號 | 50,000. |

### 公司使用者帳戶限制

| 項目 | 最大限制 |
| ----------- | ------------- |
| 公司的使用者帳戶數上限 | 1,000. |

## 監視器使用情況 {#monitor-usage}

您可以前往，查看帳戶的使用情形和限制 **[!UICONTROL Administration > Limits]**。 存取需要管理員權限。

![使用限制影像](assets/usage-limits.png)

## 增加項目限制 {#increase-item-limits}

此處列出的預設限制應提供足夠的容量以滿足您的業務需求。 如果貴組織一致達到這些限制，請連絡您的帳戶代表以討論增加額度。