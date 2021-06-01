---
description: 個別特徵的詳細資訊頁面提供特徵名稱、ID、效能量度、定義特徵的運算式、其所屬區段及特徵稽核記錄等資訊的概觀。 若要檢視這些詳細資料，請前往「對象資料>特徵」 ，然後按一下您要使用之特徵的名稱。
seo-description: 個別特徵的詳細資訊頁面提供特徵名稱、ID、效能量度、定義特徵的運算式、其所屬區段及特徵稽核記錄等資訊的概觀。 若要檢視這些詳細資料，請前往「對象資料>特徵」 ，然後按一下您要使用之特徵的名稱。
seo-title: 特徵詳細資料頁面
solution: Audience Manager
title: 特徵詳細資料頁面
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: 身分類型劃分，身分劃分，對象身分報表，跨裝置，跨裝置ID，裝置ID
feature: 特徵
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 1%

---

# [!UICONTROL Trait] 詳細資料頁面  {#trait-details-page}

個別[!UICONTROL trait]的詳細資訊頁面提供[!UICONTROL trait]詳細資訊的概觀，例如[!UICONTROL trait]名稱、ID、效能量度、定義[!UICONTROL trait]、其所屬區段及[!UICONTROL trait]稽核記錄的運算式。 要查看這些詳細資訊，請轉至&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Traits]**，然後按一下要使用的[!UICONTROL trait]的名稱。

## [!UICONTROL Trait] 管理工具  {#trait-management-tools}

[!UICONTROL trait]詳細資訊頁面頂端會包含您可用來管理[!UICONTROL traits]的工具：

1. **[!UICONTROL Add New]**:使用此選項可建 [!UICONTROL rule-based]立新 [!UICONTROL algorithmic]、或 [!UICONTROL onboarded traits]。
2. **[!UICONTROL Edit]**:使用此選項可更改當前配置的 [!UICONTROL trait]值。
3. **[!UICONTROL Delete]**:使用此選項可從您的Audience Manager [!UICONTROL trait] 帳戶中移除目前帳戶。
4. **[!UICONTROL Marketplace Recommendations]**:使用此選項可 [!UICONTROL traits] 找到與您正在檢視的類似項目，從您未 [!UICONTROL Audience Marketplace] 訂閱的資料費用中找出。請參閱資料購買者的[Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) ，了解如何導覽[!UICONTROL Marketplace]並尋找類似特徵。

![基本特徵資訊](assets/basic-trait-information.png)

## [!UICONTROL Trait] 資訊 {#basics}

[!UICONTROL Trait Information]區段顯示您在建立[!UICONTROL trait]時填入的必填和選填欄位的詳細資訊。 這包括[!UICONTROL trait]類型、[!UICONTROL trait] ID、說明、[!UICONTROL data source]和其他中繼資料。 這些詳細資訊會依[!UICONTROL trait]類型（[!UICONTROL folder]、[!UICONTROL onboarded]或[!UICONTROL rule-based]）而異。

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph]提供您所選[!UICONTROL trait]的簡單效能量度。 將游標停留在趨勢線上，查看所選[!UICONTROL trait]的其他資料。

[!UICONTROL Unique Trait Realizations] 代表在指定時間範圍內，將此項新增 [!UICONTROL trait] 至其設定檔的不重複使用者計數。[!UICONTROL Total Trait Population]表示當前符合此[!UICONTROL trait]資格的不重複用戶數。

若為[!UICONTROL rule-based traits]，當使用者符合瀏覽器中[!UICONTROL trait]的資格時，會即時進行[!UICONTROL trait]資格確認。

對於[!UICONTROL onboarded traits],[!UICONTROL trait]資格會在處理入站檔案後發生，亦即，入站檔案為[饋入至Audience Manager](../../faq/faq-inbound-data-ingestion.md)，即[!UICONTROL trait]資格發生時。

[!UICONTROL Trait Graph]顯示以下資訊：

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**:選取此選項可查看收集已驗 [!UICONTROL traits] 證設定檔資料的結果。選取此選項時，您只會在[!UICONTROL Cross-Device ID]報表上看到資料，且[!UICONTROL Device ID]報表下不會出現任何資料。
   * **[!UICONTROL Device ID]**:選取此選項可查看收集 [!UICONTROL traits] 裝置設定檔資料的結果。選取此選項時，您只會在[!UICONTROL Device ID]報表上看到資料，且[!UICONTROL Cross-Device ID]報表下不會出現任何資料。

      ![特徵圖](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**:在指定時間範圍內將此新增至 [!UICONTROL trait] 其設定檔的不重複使用者計數。
* **[!UICONTROL Total Trait Population]**:目前符合此資格的不重複使用者數 [!UICONTROL trait]量。

* **[!UICONTROL Identity Type Breakdown]**:前三個項目會以遞減順 [!UICONTROL cross-device data sources] 序顯示具有符合資格之最高母 [!UICONTROL trait]體計數的前三個。第四個條目顯示符合[!UICONTROL trait]資格的所有其它[!DNL DPUUIDs]([!DNL CRM IDs])的總和，它來自不在前三個條目中的[!UICONTROL cross-device data sources]。 只有在頁面右上方的[!UICONTROL Show Results By]下拉式功能表中選取[!UICONTROL Cross-device ID]時，才會顯示此報表。 預設的下拉式選項為[!UICONTROL Device ID]，不會顯示此報表。

   ![特徵圖](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager只會在您有[!UICONTROL cross-device]符合[!UICONTROL trait]資格的ID時顯示[!UICONTROL Identity Type Breakdown]報表。

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] 運算式 {#trait-expression}

[!UICONTROL Trait Expression]區段顯示使用者必須符合才能符合[!UICONTROL trait]的條件。 當您[建立或編輯特徵](../../features/traits/about-trait-builder.md)時，會設定這些規則。

![](assets/traitExpression.png)

## [!UICONTROL Trait] 區段 {#trait-segments}

[!UICONTROL Segments with this Trait]部分列出選定[!UICONTROL trait]所屬的所有段。 您可以按一下區段名稱，以查看該區段的詳細資訊。

![](assets/traitSegments.png)

## [!UICONTROL Trait] 審核/歷史記錄日誌  {#trait-audit-history}

對於[!UICONTROL rule-based]和[!UICONTROL onboarded traits], [!UICONTROL Trait Expression Change History]會顯示對[!UICONTROL trait]運算式規則進行的最後10項變更，以及這些變更的執行者。 如果您的[!UICONTROL trait]有10個以上的更改，請按一下&#x200B;**[!UICONTROL Export to CSV]**&#x200B;下載整個審核日誌。 審核日誌不適用於[!UICONTROL folder]或[!UICONTROL algorithmic traits]。

>[!NOTE]
>
>[!UICONTROL Not Available] 欄中 [!UICONTROL By User] 表示該使用者的帳戶已刪除。

![](assets/traitHistory.png)
