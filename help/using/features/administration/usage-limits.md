---
description: Audience Manager會針對您可為帳戶建立的特徵、區段、目的地和演算法模型數量設定上限。 無論是在使用者介面中建立，還是透過API方法以程式設計方式建立，上限都適用於這些項目。 使用量限制有助於保護Audience Manager，使其免受可能會嘗試損害我們API或使用者介面的自動化程式之害。
seo-description: Audience Manager會針對您可為帳戶建立的特徵、區段、目的地和演算法模型數量設定上限。 無論是在使用者介面中建立，還是透過API方法以程式設計方式建立，上限都適用於這些項目。 使用量限制有助於保護Audience Manager，使其免受可能會嘗試損害我們API或使用者介面的自動化程式之害。
seo-title: 使用量限制
solution: Audience Manager
title: 使用量限制
keywords: ID對應， ID對應， Cookie對應
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: 使用與帳單
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 6%

---

# 使用量限制 {#usage-limits}

Audience Manager會針對您可為帳戶建立的特徵、區段、目的地和演算法模型數量設定上限。 無論是在使用者介面中建立，還是透過[!DNL API]方法以程式設計方式建立，上限都適用於這些項目。 使用限制有助於保護Audience Manager，使其免受可能試圖破壞我們[!DNL API]s或用戶介面的自動化進程的影響。

## ID 對應限制 {#id-mapping-limits}

下表列出裝置ID的[ID對應](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)限制。 一旦ID達到以下任何限制，Audience Manager會移除最舊儲存的ID對應，並新增新的ID對應，以根據FIFO（先入先出）邏輯新增ID對應。 如需Audience Manager支援之ID的詳細資訊，請參閱Audience Manager中的[ ID索引](../../reference/ids-in-aam.md)。

| ID對應 | 上限 |
|-----------|-------------- |
| 裝置廣告ID([DAID](../../reference/ids-in-aam.md))至跨裝置ID([DPUUID](../../reference/ids-in-aam.md)) | 100個裝置廣告ID([DAID](../../reference/ids-in-aam.md))至1個跨裝置ID([DPUUID](../../reference/ids-in-aam.md)) |
| 跨裝置ID([DPUUID](../../reference/ids-in-aam.md))至裝置廣告ID([DAID](../../reference/ids-in-aam.md)) | 10個跨裝置ID([DPUUID](../../reference/ids-in-aam.md))至1個裝置廣告ID([DAID](../../reference/ids-in-aam.md))，每個[DPID](../../reference/ids-in-aam.md) |
| Cookie/瀏覽器ID至Cookie/瀏覽器ID | 1000個Cookie/瀏覽器ID改為1個Cookie/瀏覽器ID |

## 項目限制{#item-limits}

表按項目類型列出當前限制。 如果您達到這些項目之一的特定限制，便無法建立新特徵、區段、目的地或[!UICONTROL Algorithmic Models]。 如果達到限制，則必須刪除舊項目，才能建立新項目。

### 特徵限制

| 特徵類型 | 上限 |
| -------------------------- | ------------------------------------- |
| 特徵總數 | 十萬 |
| 特徵資格總計 | 15萬。 如需特徵資格的詳細資訊，請參閱[特徵資格參考](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)中的特徵資格限制。 |
| 演算法 | 50 |
| 規則型 | 十萬 |
| 已上線 | 十萬 |
| 資料夾特徵 | 零點二萬 |

### 區段限制

| 區段類型 | 上限 |
| -------------- | ------------- |
| 總區段 | 兩萬 |

### 目的地限制

| 目的地類型 | 上限 |
| ------------------ | ------------- |
| 總目的地 | 1,000 |
| Cookie | 零點一萬 |
| URL | 零點一萬 |
| S2S | 100 |
| Adobe Analytics | 10 |

### 演算法模型限制

| 項目 | 上限 |
| -------- | ----- |
| 啟用 [!UICONTROL Look-Alike Models] | 20.Audience Manager只會計算&#x200B;*active*&#x200B;演算法模型數量超過上限。 |
| [!UICONTROL Look-Alike Models] 最大受眾大小 | 2500萬。  請注意，此限制無法提高。 您可以為模型選取較少的資料來源，或選取較短的回顧期間，借此減少對象大小。 |
| [!UICONTROL Look-Alike Model]的已排除特徵數上限 | 500.請參閱演算法模型](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)中的[特徵排除。 |
| 最大[!UICONTROL Predictive Audiences Models] | 10 |
| [!UICONTROL Predictive Audiences Models]的基線角色的最大數量 | 50 |

### 資料夾限制

| 項目 | 上限 |
| ------------- | ------------------ |
| 特徵資料夾 | 2000。  您的資料夾結構最多可深5層。 |

### 衍生訊號限制

| 項目 | 上限 |
| --------------- | ------------- |
| 衍生訊號 | 50,000. |

### 公司使用者帳戶限制

| 項目 | 上限 |
| ----------- | ------------- |
| 公司的最大用戶帳戶數 | 1,000. |

## 監視器使用情況{#monitor-usage}

前往&#x200B;**[!UICONTROL Administration > Limits]**&#x200B;即可查看您帳戶的使用量和限制。 存取需要管理員權限。

![使用限制影像](assets/usage-limits.png)

## 增加項目限制{#increase-item-limits}

此處列出的預設限制應為您的業務需求提供足夠的容量。 如果貴組織持續達到這些限制，請連絡客戶代表討論增加額度。
