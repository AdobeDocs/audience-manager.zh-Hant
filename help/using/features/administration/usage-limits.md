---
description: Audience Manager對可為帳戶建立的特徵、段、目標和算法模型的數量設定最大限制。 無論是在用戶介面中建立的，還是通過API方法以寫程式方式建立的，限制都適用於這些項。 使用限制有助於保護Audience Manager免受可能試圖破壞我們API或用戶介面的自動化進程的影響。
seo-description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-title: Usage Limits
solution: Audience Manager
title: 使用量限制
keywords: ID映射、ID映射、Cookie映射
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 7%

---

# 使用量限制 {#usage-limits}

Audience Manager對可為帳戶建立的特徵、段、目標和算法模型的數量設定最大限制。 無論是在用戶介面中建立還是通過寫程式方式建立，限制都適用於這些項 [!DNL API] 的雙曲餘切值。 使用限制有助於保護Audience Manager免受可能試圖危害我們的自動化流程的影響 [!DNL API]或用戶介面。

## ID 對應限制 {#id-mapping-limits}

下表列出了 [ID映射](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) 設備ID的限制。 一旦ID達到以下任何限制，Audience Manager將通過刪除最舊儲存的ID映射並添加新的ID映射，根據FIFO（先入先出）邏輯添加新的ID映射。 請參閱 [ID的索引](../../reference/ids-in-aam.md) 在Audience Manager中，瞭解有關Audience Manager支援的ID的詳細資訊。

| ID映射 | 最大限制 |
|-----------|-------------- |
| 設備廣告ID([DAID](../../reference/ids-in-aam.md))到跨設備ID([DPUUID](../../reference/ids-in-aam.md)) | 100個設備廣告ID([DAID](../../reference/ids-in-aam.md))到1個跨設備ID([DPUUID](../../reference/ids-in-aam.md)) |
| 跨設備ID([DPUUID](../../reference/ids-in-aam.md))到設備廣告ID([DAID](../../reference/ids-in-aam.md)) | 10個跨設備ID([DPUUID](../../reference/ids-in-aam.md))到1個設備廣告ID([DAID](../../reference/ids-in-aam.md)) [DPID](../../reference/ids-in-aam.md) |
| Cookie/瀏覽器ID到Cookie/瀏覽器ID | 1000個cookie/瀏覽器ID到1個cookie/瀏覽器ID |

## 物料限制 {#item-limits}

這些表按項目類型列出當前限制。 無法建立新特徵、段、目標或 [!UICONTROL Algorithmic Models] 如果你對其中一項達到特定限制。 如果達到限制，則必須先刪除舊項目，然後才能建立新項目。

### 特性限制

| 特性類型 | 最大限制 |
| -------------------------- | ------------------------------------- |
| 總特徵 | 100,000 |
| 總特質資格 | 150,000. 有關特質鑑定的詳細資訊，請參閱中的特質鑑定限制 [特質資格參考](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)。 |
| 算法 | 50 |
| 基於規則 | 100,000 |
| 已掛接 | 100,000 |
| 資料夾特徵 | 2,000 |

### 段限制

| 段類型 | 最大限制 |
| -------------- | ------------- |
| 段總數 | 20,000 |

### 目標限制

| 目標類型 | 最大限制 |
| ------------------ | ------------- |
| 目標總數 | 1,000 |
| Cookie | 1,000 |
| URL | 1,000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### 算法模型極限

| 項目 | 最大限制 |
| -------- | ----- |
| 啟用 [!UICONTROL Look-Alike Models] | 20僅Audience Manager計數 *活動* 算法模型。 |
| [!UICONTROL Look-Alike Models] 最大受眾大小 | 25,000,000.  請注意，此限制不能增加。 您可以通過為模型選擇較少的資料源或選擇較短的回顧窗口來減少受眾規模。 |
| 最大排除的特徵數 [!UICONTROL Look-Alike Model] | 500。請參閱 [算法建模中的特徵排斥](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)。 |
| 最大 [!UICONTROL Predictive Audiences Models] | 10 |
| 最大基線人數 [!UICONTROL Predictive Audiences Models] | 50 |

### 資料夾限制

| 項目 | 最大限制 |
| ------------- | ------------------ |
| 特性資料夾 | 2,000.  資料夾結構最多可以有5級深。 |

### 派生的信號限制

| 項目 | 最大限制 |
| --------------- | ------------- |
| 衍生訊號 | 50,000. |

### 公司用戶帳戶限制

| 項目 | 最大限制 |
| ----------- | ------------- |
| 公司的最大用戶帳戶數 | 1,000. |

## 監視使用情況 {#monitor-usage}

通過轉到 **[!UICONTROL Administration > Limits]**。 訪問需要管理員權限。

![使用限制影像](assets/usage-limits.png)

## 增加物料限制 {#increase-item-limits}

此處列出的預設限制應為您的業務需求提供足夠的容量。 如果您的組織始終達到這些限制，請與客戶代表聯繫以討論增加額。
