---
description: 說明如何使用區段產生器建立區段。
seo-description: 說明如何使用區段產生器建立區段。
seo-title: 區段產生器
solution: Audience Manager
title: 區段產生器
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: 區段
translation-type: tm+mt
source-git-commit: 9e0c936ba514e517bcbd7572420118293f9a791f
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 2%

---


# [!UICONTROL Segment Builder] {#segment-builder}

說明在[!UICONTROL Segment Builder]中建立區段的必要和選用步驟。

## 視訊展示

首先，觀看「在Audience Manager視訊中建立區段」影片](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)。 [視訊會逐步帶您進行區段建立程式。 請閱讀以下章節以取得詳細資訊。

## 建立 [!UICONTROL Segment] {#create-segment}

### 區段產生器區段

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 包含3個不同的部分： [!UICONTROL Basic Information]、 [!UICONTROL Traits]和 [!UICONTROL Destinations Mapping]。要建立[!UICONTROL segment]，請填寫[!UICONTROL Basic Information]和[!UICONTROL Traits]部分中的必填欄位。 [!UICONTROL Destinations Mapping] 設定為選用。請參閱以下說明以取得其他說明。

1. 在[基本資訊](../../features/segments/segment-builder.md#segment-builder-controls-basics)部分中：

   ![create-segment](assets/create-segment.png)

   * 命名[!UICONTROL segment]。 [!UICONTROL segment]名稱的最大長度為255個字元。
   * 設定[!UICONTROL segment]狀態（預設為作用中）。
   * 選擇[!UICONTROL data source]。 使用第一個下拉式選單，在Audience Manager[!UICONTROL data sources]、Adobe Analytics報表套裝或兩者之間進行篩選。 然後，使用第二個下拉式選單選擇您的[!UICONTROL data source]。 如果您未使用Adobe Analytics報表套裝，[!UICONTROL data source]類型選擇器會停用，且預設為僅Audience Manager資料來源。
   * 選擇[!UICONTROL profile merge rule]以用於[!UICONTROL segment]資格。
   * 將[!UICONTROL segment]分配給儲存資料夾。

1. 在[Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits)區段中：
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * 搜尋要新增至區段的[!UICONTROL trait]，然後按一下&#x200B;**[!UICONTROL Add Trait]**。 添加另一個[!UICONTROL trait]以建立[!UICONTROL trait]組。
   * 按一下&#x200B;**[!UICONTROL Browse All Traits]**&#x200B;開啟[!UICONTROL Advanced Search]模式。 依名稱、ID、說明或[!UICONTROL data source]搜尋[!UICONTROL traits]。 在搜索時按一下一個資料夾，將結果限制在該資料夾及其子資料夾。 您也可以依[!UICONTROL trait type]（[!UICONTROL Folder Trait]、[!UICONTROL Rule-based]、[!UICONTROL Onboarded]和[!UICONTROL Algorithmic]）或人口類型（[裝置ID](../../reference/ids-in-aam.md)和[跨裝置ID](../../reference/ids-in-aam.md)）篩選[!UICONTROL traits]。
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * 在建立[!UICONTROL segment]時取得即時[特徵建議](trait-recommendations.md)。
   * 按一下並拖曳[!UICONTROL traits]以建立個別群組。
   * 將滑鼠指標暫留在群組之間，以設定與布林值[!UICONTROL AND]、[!UICONTROL OR]、[!UICONTROL AND NOT]值的關係。
   * 將滑鼠指標暫留在時鐘圖示上，將[時近和頻率](../../features/segments/recency-and-frequency.md)規則新增至[!UICONTROL trait]。
   * 在您新增或移除[!UICONTROL traits]時檢視區段人口族群資料。 按一下&#x200B;**[!UICONTROL Calculate Estimates]**&#x200B;查看（或刷新）估計的人口數。 閱讀[!UICONTROL Segment Builder]中有關[區段人口資料](../../features/segments/segment-builder-data.md#segment-populations)的更多資訊。
   * 完成後，按一下&#x200B;**[!UICONTROL Save]**。

1. *（可選）將* 映射 [!UICONTROL segment] 到「目 [!UICONTROL destination] 標映 [射」部](../../features/segments/segment-builder.md#segment-builder-controls-destinations) 分：
   * 搜索[!UICONTROL destination]並按一下&#x200B;**[!UICONTROL Add Destination]**。 請注意，[!UICONTROL destination]必須已存在，您才能將其添加到[!UICONTROL segment]。
   * 完成後，按一下&#x200B;**[!UICONTROL Save]**。

請觀看以下影片，詳細瞭解跨裝置量度的運作方式。

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] 控制項： [!UICONTROL Basic Information] 章節  {#segment-builder-controls-basics}

在[!UICONTROL Segment Builder]中，[!UICONTROL the Basic Information]設定可讓您建立新特徵或編輯現有特徵。 要建立新的[!UICONTROL segment]，請提供名稱[!UICONTROL data source]，然後選擇儲存資料夾。 所有其他欄位皆為選用。 完成時，請移至[!UICONTROL Traits]區段。

<!-- r_segment_basic_info_section.xml -->

<!--

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Give the segment a short, logical name that describes its function or purpose. Avoid abbreviations and special characters. The maximum length of a segment name is 255 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integration Code</b> </td> 
   <td colname="col2"> <p>A field for a user-defined ID or other company-specific information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <p>Associates the segment with a specific data provider. <p>Use the first drop-down menu to filter between Audience Manager data sources, Adobe Analytics report suites, or both. Then, use the second drop-down menu to choose your data source.</p><p> If you are not using Adobe Analytics report suites, the data source type selector is disabled and defaulted to Audience Manager data sources only.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profile Merge Rule</b> </td> 
   <td colname="col2"> <p>Selects the Profile Merge Rule to use for segment qualification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Activates or deactivates the segment (active by default). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Folder Storage</b> </td> 
   <td colname="col2"> <p>Determines which storage folder the segment belongs to. </p> </td> 
  </tr> 
 </tbody> 
</table>

-->

| 欄位 | 說明 |
---------|----------
| **[!UICONTROL Name]** | 為區段指定簡短的邏輯名稱，以說明其功能或用途。 避免縮寫和特殊字元。 區段名稱的最大長度為255個字元。 |
| **[!UICONTROL Description]** | 欄位，以取得區段的其他說明性資訊。 |
| **[!UICONTROL Integration Code]** | 使用者定義ID或其他公司特定資訊的欄位。 |
| **[!UICONTROL Data Source]** | 將區段與特定資料提供者關聯。 <br> 使用第一個下拉式選單，在Audience Manager資料來源、Adobe Analytics報表套裝或兩者之間進行篩選。然後，使用第二個下拉式選單來選擇您的資料來源。 <br> 如果您未使用Adobe Analytics報表套裝，資料來源類型選擇器會停用，且預設為僅Audience Manager資料來源。 |
| **[!UICONTROL Profile Merge Rule]** | 選擇用於區段限定的描述檔合併規則。 |
| **[!UICONTROL Status]** | 啟動或停用區段（預設為活動）。 |
| **資料夾儲存** | 確定段所屬的儲存資料夾。 |

## [!UICONTROL Segment Builder] 控制項： [!UICONTROL Traits] 章節  {#segment-builder-controls-traits}

在[!UICONTROL Segment Builder]中，[!UICONTROL Traits]區段可讓您管理[!UICONTROL segment]中的[!UICONTROL traits]、建立[!UICONTROL trait]群組，並設定資格標準。 若要將[!UICONTROL trait]新增至[!UICONTROL segment]，請在搜尋欄位中輸入[!UICONTROL trait]名稱，然後按一下[!UICONTROL Add Trait]。 儲存[!UICONTROL trait]（如果完成）或移至[!UICONTROL Destinations Mapping]。

<!-- r_segment_traits_section.xml-->

**必要條件：** 完成章節中的必填 [!UICONTROL Basic Information] 欄位。

| 欄位 | 說明 |
|--- |--- |
| **[!UICONTROL Basic View]** | 本節提供視覺控制項，可讓您： <ul><li>建立新內容並管理現有的[!UICONTROL segments]。</li><li>從[!UICONTROL segment]移除[!UICONTROL traits]。</li><li>最多可將50（最大值）[!UICONTROL traits]加到[!UICONTROL segment]。</li><li>拖放[!UICONTROL traits]以建立新群組。</li><li>在[!UICONTROL segment]中查看[!UICONTROL traits]和[!UICONTROL trait]組。</li><li>使用布林運算式、比較運算子和時近／頻率設定來設定限定條件。</li></ul> |
| **[!UICONTROL Code View]** | 開啟開發環境，讓您使用程式碼來建立和管理[!UICONTROL traits]、群組和資格要求，而非使用視覺化介面。 如果您的[!UICONTROL segments]: <ul><li>在個別[!UICONTROL segment]中包含50個以上的[!UICONTROL traits]。 注意：[!UICONTROL Segments]限制為5000 [!UICONTROL traits]（最大值）。</li><li>包含許多[!UICONTROL trait]群組。</li><li>具備複雜的資格要求。</li></ul> |
| 搜尋 | 協助您找到要新增至[!UICONTROL segment]的[!UICONTROL traits]。 |
| 建議 | 從您訂閱的第一方[!UICONTROL traits]和[!UICONTROL Audience Marketplace]資料饋送，取得類似[!UICONTROL traits]的即時建議。 將這些建議新增至[!UICONTROL segment]規則，以擴充您的觀眾。 閱讀[特徵Recommendations](trait-recommendations.md)的更多資訊。 |
| **[!UICONTROL Marketplace Recommendations]** | 從您未訂閱的[!UICONTROL Audience Marketplace]資料饋送，取得類似[!UICONTROL traits]的即時建議。 閱讀[特徵Recommendations](trait-recommendations.md)的更多資訊。 |
| 實際和估計[!UICONTROL Segment]大小資料 | 請參閱[區段產生器的特徵和區段母體資料](segment-builder-data.md)。 |

## 從[!UICONTROL Segment] {#remove-traits}移除[!UICONTROL Traits]

在[!UICONTROL segments]中管理[!UICONTROL traits]是維持[!UICONTROL segments]可行性的重要部分。 如果需要從[!UICONTROL segment]中刪除[!UICONTROL traits]，請遵循下列步驟。

要從[!UICONTROL segment]中刪除[!UICONTROL traits]:

1. 前往&#x200B;**[!UICONTROL Audience Data > Segments]**。 捲動清單或使用搜尋功能尋找您要使用的[!UICONTROL segment]。
2. 按一下[!UICONTROL segment]名稱以開啟[!UICONTROL segment]詳細資訊螢幕。
3. 按一下「編輯」以開啟[!UICONTROL Segment Builder]，然後按一下「特徵」以開啟[!UICONTROL traits]面板。********
4. 將滑鼠指標暫留在您要刪除的[!UICONTROL trait]上，然後按一下X。此動作會立即從您的[!UICONTROL segment]移除[!UICONTROL trait]。

## [!UICONTROL Segment Builder] 控制項： [!UICONTROL Destinations Mappings] 章節  {#segment-builder-controls-destinations}

在[!UICONTROL Segment Builder]中，可選的[!UICONTROL Destinations Mapping]區段可讓您傳送[!UICONTROL segment]資料給第三方[!DNL cookie]、[!DNL URL]或[!UICONTROL server-to-server destination]。 若要新增[!UICONTROL destination]，請搜尋（或瀏覽）[!UICONTROL destination]，提供[!UICONTROL destination]特定資訊，然後按一下&#x200B;**[!UICONTROL Add Destination]**。

<!-- r_segment_destinations_map.xml -->

### 必要條件

填寫[!UICONTROL Basic Information]和[!UICONTROL Traits]章節中的必填欄位。 此外，目標必須已存在。

### [!UICONTROL Destination Mappings] 搜尋工具

**[!UICONTROL Destination Mappings]**&#x200B;面板包含下表所述的搜尋工具。

| 搜尋類型 | 說明 |
|---|---|
| **[!UICONTROL Search by Destination Name]** | 可讓您依名稱搜尋特定[!UICONTROL destination]。 若要搜尋，請開始輸入。 欄位將根據您的搜尋詞自動完成。 完成後，按一下&#x200B;**[!UICONTROL Add Destination]**。 |
| **[!UICONTROL Browse All Destinations]** | 瀏覽您可用的&#x200B;*all* [!UICONTROL destinations]清單。 從彈出式清單中選取並新增[!UICONTROL destinations]至[!UICONTROL segment]。 |

## [!UICONTROL Destination Mappings]快顯視窗{#fields-in-dest-mappings}中的欄位

在[!UICONTROL Segment Builder]中，選擇[!UICONTROL destination]後將顯示[!UICONTROL Add Destination]對話框。 此窗口顯示有關[!UICONTROL destination]和欄位的靜態資訊，這些欄位會根據[!UICONTROL destination]類型而有所不同。 在空白欄位中提供必要資訊以設定[!UICONTROL destination mapping]。

>[!NOTE]
>
>出版日期為選擇性。 如果為空白，則目標會變為作用中且永不過期。

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] 欄位

在[!UICONTROL Destination Mapping]欄位中，指定用於傳送資料至[!UICONTROL destination]的鍵值對。 在第一個欄位中輸入鍵，在第二個欄位中輸入值。 您的[!UICONTROL cookie destination]快顯功能看起來可能類似下列：

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] 欄位

在[!UICONTROL URL]和[!UICONTROL Secure URL]欄位中，指定用於傳送資料至[!UICONTROL destination]的完整標準或安全位址。

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] 欄位

在[!UICONTROL Destination Value]欄位中，指定用於傳送資料至[!UICONTROL destination]的值（鍵值對的一部分）。

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [建立Cookie目標](../../features/destinations/create-cookie-destination.md)
>* [建立URL目標](../../features/destinations/create-url-destination.md)

