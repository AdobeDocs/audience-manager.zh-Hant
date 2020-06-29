---
description: 個別特徵的詳細資料頁面提供資訊的概述，例如特徵名稱、ID、效能度量、定義特徵的運算式、其所屬的區段以及特徵稽核記錄。 若要檢視這些詳細資訊，請前往「對象資料>特徵」，然後按一下您要使用之特徵的名稱。
seo-description: 個別特徵的詳細資料頁面提供資訊的概述，例如特徵名稱、ID、效能度量、定義特徵的運算式、其所屬的區段以及特徵稽核記錄。 若要檢視這些詳細資訊，請前往「對象資料>特徵」，然後按一下您要使用之特徵的名稱。
seo-title: 特徵詳細資料頁面
solution: Audience Manager
title: 特徵詳細資料頁面
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 1%

---


# [!UICONTROL Trait] 詳細資訊頁面 {#trait-details-page}

個人的詳細資訊頁 [!UICONTROL trait] 面提供詳細資訊的概觀 [!UICONTROL trait] ，例如 [!UICONTROL trait] 名稱、ID、效能量度、定義運算式 [!UICONTROL trait]、其所屬區段和稽核記錄 [!UICONTROL trait] 檔。 若要檢視這些詳細資訊，請 **[!UICONTROL Audience Data]** 前往> **[!UICONTROL Traits]** 並按一下您要 [!UICONTROL trait] 使用的名稱。

## [!UICONTROL Trait] 管理工具 {#trait-management-tools}

詳細資料頁 [!UICONTROL trait] 面頂端會裝載您可用來管理的工具 [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: 使用此選項可建立 [!UICONTROL rule-based]新 [!UICONTROL algorithmic]、或 [!UICONTROL onboarded traits]。
2. **[!UICONTROL Edit]**: 使用此選項可更改當前配置 [!UICONTROL trait]。
3. **[!UICONTROL Delete]**: 使用這個選項可從您的Audience Manager帳 [!UICONTROL trait] 戶移除目前的帳戶。
4. **[!UICONTROL Marketplace Recommendations]**: 使用這個選項， [!UICONTROL traits] 從您未訂閱的資料費 [!UICONTROL Audience Marketplace] 用中，找出與您正在檢視的類似的選項。 請參 [閱Audience Marketplace for Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) ，以瞭解如何導覽及 [!UICONTROL Marketplace] 尋找類似特徵。

![基本特徵資訊](assets/basic-trait-information.png)

## [!UICONTROL Trait] 資訊 {#basics}

本節 [!UICONTROL Trait Information] 將顯示有關在構建時完成的必填和選填欄位的詳細資訊 [!UICONTROL trait]。 這包括類型、 [!UICONTROL trait] ID、 [!UICONTROL trait] 說明、 [!UICONTROL data source]和其他中繼資料。 這些詳細資訊會依 [!UICONTROL trait] 類型([!UICONTROL folder]、 [!UICONTROL onboarded]或 [!UICONTROL rule-based])而異。

## [!UICONTROL Trait Graph] {#trait-graph}

本 [!UICONTROL Trait Graph] 產品提供您所選取之效能量度總覽 [!UICONTROL trait]。 將游標停留在趨勢線上，即可查看所選項目的其他資料 [!UICONTROL trait]。

[!UICONTROL Unique Trait Realizations] 代表在特定時間範圍內將此新增至個人 [!UICONTROL trait] 檔案的獨特使用者計數。 指 [!UICONTROL Total Trait Population] 出目前符合此條件的獨特使用者人數 [!UICONTROL trait]。

對於 [!UICONTROL rule-based traits], [!UICONTROL trait] 只要使用者符合瀏覽器的資格，就可即時 [!UICONTROL trait] 進行資格設定。

對於 [!UICONTROL onboarded traits], [!UICONTROL trait] 在處理傳入檔案後會進行資格設定，即傳入檔案 [饋送至Audience Manager](../../faq/faq-inbound-data-ingestion.md) ，也就是進行 [!UICONTROL trait] 資格設定。

顯 [!UICONTROL Trait Graph] 示下列資訊：

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: 選取此選項可查看收集已驗證 [!UICONTROL traits] 描述檔資料的結果。 選取此選項時，您只會在報表上看到資 [!UICONTROL Cross-Device ID] 料，且報表下不會顯示任何資 [!UICONTROL Device ID] 料。
   * **[!UICONTROL Device ID]**: 選取此選項可查看收集裝 [!UICONTROL traits] 置設定檔資料的結果。 選取此選項時，您只會在報表上看到資 [!UICONTROL Device ID] 料，且報表下不會顯示任何資 [!UICONTROL Cross-Device ID] 料。

      ![特徵圖](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: 在特定時間範圍內，將此新增至其 [!UICONTROL trait] 描述檔的獨特使用者計數。
* **[!UICONTROL Total Trait Population]**: 目前符合此條件的獨特使用者人數 [!UICONTROL trait]。

* **[!UICONTROL Identity Type Breakdown]**: 前三個條目以遞減順序顯 [!UICONTROL cross-device data sources] 示具有符合該條件的最高人口計數 [!UICONTROL trait]的前三個條目。 第四個項目顯示其他( [!DNL DPUUIDs][!DNL CRM IDs])符合該條 [!UICONTROL trait]件的總和， [!UICONTROL cross-device data sources] 即非前三名的項目。 只有在頁面右上方的下 [!UICONTROL Cross-device ID] 拉式功 [!UICONTROL Show Results By] 能表中選取時，才會顯示此報表。 預設下拉式選項為 [!UICONTROL Device ID]，不會顯示此報表。

   ![特徵圖](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager僅在您有符 [!UICONTROL Identity Type Breakdown] 合的ID時 [!UICONTROL cross-device] 才顯示報表 [!UICONTROL trait]。

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] 運算式 {#trait-expression}

本節 [!UICONTROL Trait Expression] 將顯示使用者必須符合的條件，才能符合 [!UICONTROL trait]。 這些規則是在您建立或編 [輯特徵時設定](../../features/traits/about-trait-builder.md)。

![](assets/traitExpression.png)

## [!UICONTROL Trait] 區段 {#trait-segments}

該 [!UICONTROL Segments with this Trait] 部分列出選定的所有 [!UICONTROL trait] 段。 您可以按一下區段名稱，以檢視該區段的詳細資訊。

![](assets/traitSegments.png)

## [!UICONTROL Trait] 審計／歷史記錄 {#trait-audit-history}

對於 [!UICONTROL rule-based] 和 [!UICONTROL onboarded traits]，顯 [!UICONTROL Trait Expression Change History] 示對運算式規則所做的最後10 [!UICONTROL trait] 項變更，以及變更的對象。 如果您 [!UICONTROL trait] 有10項以上的變更，請按一 **[!UICONTROL Export to CSV]** 下以下載整個稽核記錄。 審核日誌不可用於 [!UICONTROL folder] 或 [!UICONTROL algorithmic traits]。

>[!NOTE]
>
>[!UICONTROL Not Available] in [!UICONTROL By User] column表示該使用者的帳戶已刪除。

![](assets/traitHistory.png)