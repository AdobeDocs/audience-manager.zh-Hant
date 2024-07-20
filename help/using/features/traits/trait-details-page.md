---
description: 個別特徵的詳細資訊頁面提供特徵名稱、ID、效能測量結果、定義特徵的運算式、其所屬區段及特徵稽核記錄檔等資訊的總覽。 若要檢視這些詳細資訊，請前往「對象資料>特徵」 ，然後按一下您要使用之特徵的名稱。
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: 特徵詳細資訊頁面
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: 身分型別劃分、身分劃分、對象身分報告、跨裝置、跨裝置ID、裝置ID
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 0%

---

# [!UICONTROL Trait]詳細資料頁面 {#trait-details-page}

個別[!UICONTROL trait]的詳細資訊頁面提供[!UICONTROL trait]詳細資訊的概觀，例如[!UICONTROL trait]名稱、ID、效能測量結果、定義[!UICONTROL trait]的運算式、它所屬的區段以及[!UICONTROL trait]稽核記錄。 若要檢視這些詳細資料，請前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Traits]**，然後按一下您要使用的[!UICONTROL trait]的名稱。

## [!UICONTROL Trait]管理工具 {#trait-management-tools}

[!UICONTROL trait]詳細資訊頁面頂端裝載了可用來管理[!UICONTROL traits]的工具：

1. **[!UICONTROL Add New]**：使用此選項來建立新的[!UICONTROL rule-based]、[!UICONTROL algorithmic]或[!UICONTROL onboarded traits]。
2. **[!UICONTROL Edit]**：使用此選項來變更目前[!UICONTROL trait]的組態。
3. **[!UICONTROL Delete]**：使用此選項從您的Audience Manager帳戶移除目前的[!UICONTROL trait]。
4. **[!UICONTROL Marketplace Recommendations]**：使用此選項可尋找與您檢視的類似[!UICONTROL traits]，來自您未訂閱的[!UICONTROL Audience Marketplace]資料費用。 請參閱資料購買者的[Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)，瞭解如何導覽[!UICONTROL Marketplace]並尋找類似特徵。

![基本特徵資訊](assets/basic-trait-information.png)

## [!UICONTROL Trait]資訊 {#basics}

[!UICONTROL Trait Information]區段顯示您在建置[!UICONTROL trait]時完成的必要和選用欄位的詳細資料。 這包括[!UICONTROL trait]型別、[!UICONTROL trait] ID、說明、[!UICONTROL data source]和其他中繼資料等內容。 這些詳細資料視[!UICONTROL trait]型別（[!UICONTROL folder]、[!UICONTROL onboarded]或[!UICONTROL rule-based]）而定。

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph]提供您選定[!UICONTROL trait]的績效量度一覽。 將游標停留在趨勢線上，即可檢視所選[!UICONTROL trait]的其他資料。

[!UICONTROL Unique Trait Realizations]代表在指定時間範圍內將此[!UICONTROL trait]新增到其設定檔的不重複使用者計數。 [!UICONTROL Total Trait Population]表示目前符合此[!UICONTROL trait]資格的不重複使用者數目。

針對[!UICONTROL rule-based traits]，[!UICONTROL trait]資格會即時進行，因為使用者在其瀏覽器中符合[!UICONTROL trait]的資格。

針對[!UICONTROL onboarded traits]，[!UICONTROL trait]資格會在處理傳入檔案之後發生，亦即傳入檔案是[饋送至Audience Manager](../../faq/faq-inbound-data-ingestion.md)，且此時會發生[!UICONTROL trait]資格。

[!UICONTROL Trait Graph]會顯示下列資訊：

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**：選取此選項可檢視[!UICONTROL traits]收集已驗證設定檔資料的結果。 當您選取此選項時，您只會在[!UICONTROL Cross-Device ID]報表上看到資料，而[!UICONTROL Device ID]報表下不會出現任何資料。
   * **[!UICONTROL Device ID]**：選取此選項可檢視[!UICONTROL traits]收集裝置設定檔資料的結果。 當您選取此選項時，您只會在[!UICONTROL Device ID]報表上看到資料，而[!UICONTROL Cross-Device ID]報表下不會出現任何資料。

     ![特徵圖](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**：在指定時間範圍內將此[!UICONTROL trait]新增到其設定檔的不重複使用者計數。
* **[!UICONTROL Total Trait Population]**：目前符合此[!UICONTROL trait]資格的不重複使用者數目。

* **[!UICONTROL Identity Type Breakdown]**：前三個專案以遞減順序顯示符合[!UICONTROL trait]資格且母體計數最高的前三個[!UICONTROL cross-device data sources]。 第四個專案顯示來自[!UICONTROL cross-device data sources]且非前三個專案之所有其他[!DNL DPUUIDs] ([!DNL CRM IDs])符合[!UICONTROL trait]資格的總和。 只有在頁面右上方的[!UICONTROL Show Results By]下拉式功能表中選取[!UICONTROL Cross-device ID]時，此報表才會出現。 預設下拉式選項為[!UICONTROL Device ID]，其中不會顯示此報表。

  ![特徵圖](assets/trait-identity.png)

  >[!NOTE]
  >
  >若您有[!UICONTROL cross-device]個ID符合[!UICONTROL trait]的資格，Audience Manager僅會顯示[!UICONTROL Identity Type Breakdown]報告。

  >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait]運算式 {#trait-expression}

[!UICONTROL Trait Expression]區段顯示使用者必須符合的條件才符合[!UICONTROL trait]。 這些規則是在您[建立或編輯特徵](../../features/traits/about-trait-builder.md)時設定。

![](assets/traitExpression.png)

## [!UICONTROL Trait] 區段 {#trait-segments}

[!UICONTROL Segments with this Trait]區段列出所選[!UICONTROL trait]所屬的所有區段。 您可以按一下區段名稱來檢視該區段的詳細資訊。

![](assets/traitSegments.png)

## [!UICONTROL Trait]稽核/記錄檔 {#trait-audit-history}

針對[!UICONTROL rule-based]與[!UICONTROL onboarded traits]，[!UICONTROL Trait Expression Change History]會顯示您對[!UICONTROL trait]運算式規則所做的最後10項變更以及這些變更的作者。 如果您的[!UICONTROL trait]有超過10個變更，請按一下&#x200B;**[!UICONTROL Export to CSV]**&#x200B;以下載整個稽核記錄。 [!UICONTROL folder]或[!UICONTROL algorithmic traits]無法使用稽核記錄。

>[!NOTE]
>
>[!UICONTROL By User]欄中的[!UICONTROL Not Available]表示該使用者的帳戶已刪除。

![](assets/traitHistory.png)
