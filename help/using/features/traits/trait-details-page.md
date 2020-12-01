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


# [!UICONTROL Trait] 詳細資訊頁面  {#trait-details-page}

個別[!UICONTROL trait]的詳細資料頁面提供[!UICONTROL trait]詳細資料的概述，例如[!UICONTROL trait]名稱、ID、效能度量、定義[!UICONTROL trait]的運算式、其所屬的區段和[!UICONTROL trait]稽核記錄。 若要檢視這些詳細資訊，請前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Traits]**，然後按一下您要使用的[!UICONTROL trait]名稱。

## [!UICONTROL Trait] 管理工具  {#trait-management-tools}

[!UICONTROL trait]詳細資料頁面的頂端會裝載您可用來管理[!UICONTROL traits]的工具：

1. **[!UICONTROL Add New]**:使用此選項可建立 [!UICONTROL rule-based]新 [!UICONTROL algorithmic]、或 [!UICONTROL onboarded traits]。
2. **[!UICONTROL Edit]**:使用此選項可更改當前配置 [!UICONTROL trait]。
3. **[!UICONTROL Delete]**:使用這個選項可移除Audience Manager [!UICONTROL trait] 帳戶中的目前項目。
4. **[!UICONTROL Marketplace Recommendations]**:使用這個選項可 [!UICONTROL traits] 以從您未訂閱的資料 [!UICONTROL Audience Marketplace] 費用中，找到與您正在檢視的類似。請參閱[資料購買者的觀眾市場](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)，瞭解如何導覽[!UICONTROL Marketplace]並尋找類似特性。

![基本特徵資訊](assets/basic-trait-information.png)

## [!UICONTROL Trait] 資訊 {#basics}

[!UICONTROL Trait Information]區段顯示有關您在建立[!UICONTROL trait]時完成的必填和選填欄位的詳細資訊。 這包括[!UICONTROL trait]類型、[!UICONTROL trait] ID、說明、[!UICONTROL data source]和其他中繼資料。 這些詳細資訊會視[!UICONTROL trait]類型（[!UICONTROL folder]、[!UICONTROL onboarded]或[!UICONTROL rule-based]）而異。

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph]提供您所選[!UICONTROL trait]的一覽效能度量。 將游標停留在趨勢線上，即可查看所選[!UICONTROL trait]的其他資料。

[!UICONTROL Unique Trait Realizations] 代表在指定時間範圍內將此新增 [!UICONTROL trait] 至其描述檔的獨特使用者計數。[!UICONTROL Total Trait Population]表示當前符合此[!UICONTROL trait]條件的獨特用戶數。

對於[!UICONTROL rule-based traits]，當使用者符合其瀏覽器中[!UICONTROL trait]的資格時，即時進行[!UICONTROL trait]資格設定。

對於[!UICONTROL onboarded traits]，在處理傳入檔案後會進行[!UICONTROL trait]資格設定，亦即傳入檔案是[饋送至Audience Manager](../../faq/faq-inbound-data-ingestion.md)，也就是[!UICONTROL trait]資格設定發生時。

[!UICONTROL Trait Graph]會顯示下列資訊：

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**:選取此選項可查看收集已驗 [!UICONTROL traits] 證設定檔資料的結果。當您選取此選項時，您只會在[!UICONTROL Cross-Device ID]報表上看到資料，而且[!UICONTROL Device ID]報表下不會顯示任何資料。
   * **[!UICONTROL Device ID]**:選取此選項可查看收集裝 [!UICONTROL traits] 置設定檔資料的結果。當您選取此選項時，您只會在[!UICONTROL Device ID]報表上看到資料，而且[!UICONTROL Cross-Device ID]報表下不會顯示任何資料。

      ![特徵圖](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**:在特定時間範圍內，將此新增至其 [!UICONTROL trait] 描述檔的獨特使用者計數。
* **[!UICONTROL Total Trait Population]**:目前符合此條件的獨特使用者人數 [!UICONTROL trait]。

* **[!UICONTROL Identity Type Breakdown]**:前三個條目以遞減順序顯 [!UICONTROL cross-device data sources] 示具有最高人口計數的前三 [!UICONTROL trait]個條目。第四個條目顯示符合[!UICONTROL trait]條件的所有其它[!DNL DPUUIDs]([!DNL CRM IDs])的總和，該值來自[!UICONTROL cross-device data sources]，但不在前三個條目中。 只有在頁面右上方的[!UICONTROL Show Results By]下拉式選單中選取[!UICONTROL Cross-device ID]時，才會顯示此報表。 預設下拉式選項為[!UICONTROL Device ID]，其中不會顯示此報表。

   ![特徵圖](assets/trait-identity.png)

   >[!NOTE]
   >
   >如果您有符合[!UICONTROL trait]資格的[!UICONTROL cross-device] ID,Audience Manager只會顯示[!UICONTROL Identity Type Breakdown]報表。

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] 運算式 {#trait-expression}

[!UICONTROL Trait Expression]區段顯示使用者必須符合的條件才能符合[!UICONTROL trait]的資格。 當您[建立或編輯特徵](../../features/traits/about-trait-builder.md)時，會設定這些規則。

![](assets/traitExpression.png)

## [!UICONTROL Trait] 區段 {#trait-segments}

[!UICONTROL Segments with this Trait]部分列出選定[!UICONTROL trait]所屬的所有段。 您可以按一下區段名稱，以檢視該區段的詳細資訊。

![](assets/traitSegments.png)

## [!UICONTROL Trait] 審計／歷史記錄  {#trait-audit-history}

對於[!UICONTROL rule-based]和[!UICONTROL onboarded traits],[!UICONTROL Trait Expression Change History]會顯示對[!UICONTROL trait]運算式規則所做的最後10項變更，以及變更的對象。 如果您的[!UICONTROL trait]有10個以上的變更，請按一下&#x200B;**[!UICONTROL Export to CSV]**&#x200B;下載整個稽核記錄。 [!UICONTROL folder]或[!UICONTROL algorithmic traits]無法使用審核日誌。

>[!NOTE]
>
>[!UICONTROL Not Available] in  [!UICONTROL By User] column表示該使用者的帳戶已刪除。

![](assets/traitHistory.png)