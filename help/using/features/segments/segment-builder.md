---
description: 說明如何使用區段產生器建立區段。
seo-description: 說明如何使用區段產生器建立區段。
seo-title: 區段產生器
solution: Audience Manager
title: 區段產生器
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
translation-type: tm+mt
source-git-commit: 9326b61f27f6c529567ab9b26694998f0b5dafb3
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 2%

---


# [!UICONTROL Segment Builder] {#segment-builder}

說明在中建立區段的必要和選用步驟 [!UICONTROL Segment Builder]。

## 視訊展示

首先，在Audience Manager影片 [中觀看「建立區段」](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)。 視訊會逐步帶您進行區段建立程式。 請閱讀以下章節以取得詳細資訊。

## 建立 [!UICONTROL Segment] {#create-segment}

### 區段產生器區段

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 包含3個不同的部分： [!UICONTROL Basic Information]、 [!UICONTROL Traits]和 [!UICONTROL Destinations Mapping]。 若要建立 [!UICONTROL segment]，請填妥和區段中的必 [!UICONTROL Basic Information] 填 [!UICONTROL Traits] 欄位。 [!UICONTROL Destinations Mapping] 設定為選用。 請參閱以下說明以取得其他說明。

1. 在「基 [本資訊](../../features/segments/segment-builder.md#segment-builder-controls-basics) 」部分：

   ![create-segment](assets/create-segment.png)

   * 命名 [!UICONTROL segment]。 名稱的最大長 [!UICONTROL segment] 度為255個字元。
   * 設定狀 [!UICONTROL segment] 態（預設為作用中）。
   * 選擇 [!UICONTROL data source]。 使用第一個下拉式選單，在Audience Manager、Adobe Analytics報表套 [!UICONTROL data sources]裝之間或兩者之間進行篩選。 然後，使用第二個下拉式選單來選擇您的 [!UICONTROL data source]。 如果您未使用Adobe Analytics報表套裝，則會停 [!UICONTROL data source] 用類型選擇器，並預設為僅限Audience Manager資料來源。
   * 選擇要 [!UICONTROL profile merge rule] 用於限定的 [!UICONTROL segment] 項目。
   * 將檔案 [!UICONTROL segment] 分配到儲存資料夾。

1. 在「特 [徵](../../features/segments/segment-builder.md#segment-builder-controls-traits) 」區段：
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * 搜尋要 [!UICONTROL trait] 新增至區段的區段，然後按一下 **[!UICONTROL Add Trait]**。 新增另 [!UICONTROL trait] 一個以建立 [!UICONTROL trait] 群組。
   * 按一下以 [!UICONTROL Advanced Search] 開啟模型 **[!UICONTROL Browse All Traits]**。 依名 [!UICONTROL traits] 稱、ID、說明或搜尋 [!UICONTROL data source]。 在搜索時按一下一個資料夾，將結果限制在該資料夾及其子資料夾。 您也可以通過(、、 [!UICONTROL traits] 和 [!UICONTROL trait type] )群體類型([!UICONTROL Folder Trait]I Device ID Cross-Cross-I Device [!UICONTROL Rule-based][!UICONTROL Onboarded][!UICONTROL Algorithmic][](../../reference/ids-in-aam.md)[](../../reference/ids-in-aam.md)ID和I D過濾器)來過濾(I Device ID Cross-I D)。
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * 在您建立 [時取得即時特](trait-recommendations.md) 徵建議 [!UICONTROL segment]。
   * 按一下並拖 [!UICONTROL traits] 曳以建立個別群組。
   * 將滑鼠指標暫留在群組之間，以設定與布 [!UICONTROL AND]爾值、 [!UICONTROL OR]值的 [!UICONTROL AND NOT] 關係。
   * 將滑鼠指標暫留在時鐘圖示上 [，將時近和頻率](../../features/segments/recency-and-frequency.md) 規則新增至 [!UICONTROL trait]。
   * 在您新增或移除時檢視區段人口族群資料 [!UICONTROL traits]。 按一下 **[!UICONTROL Calculate Estimates]** 查看（或刷新）估計的人口數。 請參閱中 [的區段人口](../../features/segments/segment-builder-data.md#segment-populations) 資料 [!UICONTROL Segment Builder]。
   * 完成時 **[!UICONTROL Save]** 按一下。

1. *（可選）* 「目標映 [!UICONTROL segment] 射」部 [!UICONTROL destination] 分中的 [映射](../../features/segments/segment-builder.md#segment-builder-controls-destinations) :
   * 搜索並 [!UICONTROL destination] 按一下 **[!UICONTROL Add Destination]**。 請注意， [!UICONTROL destination] 必須已存在，才能將其添加到 [!UICONTROL segment]。
   * 完成時 **[!UICONTROL Save]** 按一下。

請觀看以下影片，詳細瞭解跨裝置量度的運作方式。

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## [!UICONTROL Segment Builder] 控制項： [!UICONTROL Basic Information] 章節 {#segment-builder-controls-basics}

在中 [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] 設定可讓您建立新特徵或編輯現有特徵。 要建立新 [!UICONTROL segment]資料夾，請提供名 [!UICONTROL data source]稱，並選擇儲存資料夾。 所有其他欄位皆為選用。 完成時，請移 [!UICONTROL Traits] 至區段。

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
| **[!UICONTROL Data Source]** | 將區段與特定資料提供者關聯。 <br> 使用第一個下拉式選單，在Audience Manager資料來源、Adobe Analytics報表套裝或兩者之間進行篩選。 然後，使用第二個下拉式選單來選擇您的資料來源。 <br> 如果您未使用Adobe Analytics報表套裝，資料來源類型選擇器會停用，並預設為僅限Audience Manager資料來源。 |
| **[!UICONTROL Profile Merge Rule]** | 選擇用於區段限定的描述檔合併規則。 |
| **[!UICONTROL Status]** | 啟動或停用區段（預設為活動）。 |
| **資料夾儲存** | 確定段所屬的儲存資料夾。 |

## [!UICONTROL Segment Builder] 控制項： [!UICONTROL Traits] 章節 {#segment-builder-controls-traits}

在中 [!UICONTROL Segment Builder]，此 [!UICONTROL Traits] 區段可讓您在中 [!UICONTROL traits] 管理、建立 [!UICONTROL segment]群組 [!UICONTROL trait] 及設定資格標準。 若要新增 [!UICONTROL trait] 至 [!UICONTROL segment]，請在搜尋欄 [!UICONTROL trait] 位中輸入名稱，然後按一下 [!UICONTROL Add Trait]。 儲存( [!UICONTROL trait] 如果完成)或移至 [!UICONTROL Destinations Mapping]。

<!-- r_segment_traits_section.xml-->

**必要條件：** 填寫章節中的必填 [!UICONTROL Basic Information] 欄位。

| 欄位 | 說明 |
|--- |--- |
| **[!UICONTROL Basic View]** | 本節提供視覺控制項，可讓您： <ul><li>建立新內容並管理現有 [!UICONTROL segments]。</li><li>從 [!UICONTROL traits] 移除 [!UICONTROL segment]。</li><li>最多可增加50(最多 [!UICONTROL traits] )個 [!UICONTROL segment]。</li><li>拖放以 [!UICONTROL traits] 建立新群組。</li><li>在 [!UICONTROL traits] 中 [!UICONTROL trait] 檢視和群組 [!UICONTROL segment]。</li><li>使用布林運算式、比較運算子和時近／頻率設定來設定限定條件。</li></ul> |
| **[!UICONTROL Code View]** | 開啟開發環境，讓您使用程式碼來建立和管理 [!UICONTROL traits]、群組，以及限定需求，而非使用視覺化介面。 如果您符合下列條件，程式碼檢視會很有用 [!UICONTROL segments]: <ul><li>個人包含50 [!UICONTROL traits] 個以上 [!UICONTROL segment]。 注意： [!UICONTROL Segments] 限制為5000(最 [!UICONTROL traits] 大值)。</li><li>包含許多 [!UICONTROL trait] 群組。</li><li>具備複雜的資格要求。</li></ul> |
| 搜尋 | 協助您 [!UICONTROL traits] 尋找新增至 [!UICONTROL segment]。 |
| 建議 | 從您所訂閱的第 [!UICONTROL traits]一方和資料饋送， [!UICONTROL traits] 取得 [!UICONTROL Audience Marketplace] 類似的即時建議。 將這些建議新增至 [!UICONTROL segment] 規則，以擴大您的觀眾群。 閱讀更多有關特徵 [建議的資訊](trait-recommendations.md)。 |
| **[!UICONTROL Marketplace Recommendations]** | 從您未訂閱的資 [!UICONTROL traits]料饋送 [!UICONTROL Audience Marketplace] 中，取得類似的即時建議。 閱讀更多有關特徵 [建議的資訊](trait-recommendations.md)。 |
| 實際和估計 [!UICONTROL Segment] 大小資料 | 請參閱[區段產生器的特徵和區段母體資料](segment-builder-data.md)。 |

## 從 [!UICONTROL Traits] 中移除 [!UICONTROL Segment] {#remove-traits}

管理您 [!UICONTROL traits] 的內 [!UICONTROL segments] 容是維持生存的重要 [!UICONTROL segments] 部分。 如果您需要從中移除，請遵循 [!UICONTROL traits] 下列步驟 [!UICONTROL segment]。

要從 [!UICONTROL traits] 中刪除 [!UICONTROL segment]:

1. 前往 **[!UICONTROL Audience Data > Segments]**。 捲動清單或使用搜尋功能來尋找 [!UICONTROL segment] 您要使用的項目。
2. 按一下 [!UICONTROL segment] 名稱以開啟詳細 [!UICONTROL segment] 資訊畫面。
3. 按一 **下「編輯** 」以開 [!UICONTROL Segment Builder] 啟，然後按一下「 **特徵** 」以開啟面 [!UICONTROL traits] 板。
4. 將滑鼠指標暫留在 [!UICONTROL trait] 您要刪除的位置，然後按一下X。 此動作會立即從您的 [!UICONTROL trait] 裝置移除 [!UICONTROL segment]。

## [!UICONTROL Segment Builder] 控制項： [!UICONTROL Destinations Mappings] 章節 {#segment-builder-controls-destinations}

在 [!UICONTROL Segment Builder]中，選 [!UICONTROL Destinations Mapping] 用區段可讓您 [!UICONTROL segment] 傳送資料至協力廠商 [!DNL cookie]、 [!DNL URL]或 [!UICONTROL server-to-server destination]。 若要新增 [!UICONTROL destination]、搜尋（或瀏覽） [!UICONTROL destination]、提供 [!UICONTROL destination] 特定資訊，然後按一下 **[!UICONTROL Add Destination]**。

<!-- r_segment_destinations_map.xml -->

### 必要條件

填寫和區段中的必 [!UICONTROL Basic Information] 填 [!UICONTROL Traits] 欄位。 此外，目標必須已存在。

### [!UICONTROL Destination Mappings] 搜尋工具

面 **[!UICONTROL Destination Mappings]** 板包含下表所述的搜尋工具。

| 搜尋類型 | 說明 |
|---|---|
| **[!UICONTROL Search by Destination Name]** | 可讓您依名稱搜尋 [!UICONTROL destination] 特定。 若要搜尋，請開始輸入。 欄位將根據您的搜尋詞自動完成。 完成時 **[!UICONTROL Add Destination]** 按一下。 |
| **[!UICONTROL Browse All Destinations]** | 瀏覽您可 *用的*[!UICONTROL destinations] 所有清單。 從快顯清 [!UICONTROL destinations] 單中選 [!UICONTROL segment] 取並新增至您。 |

## 快顯視窗 [!UICONTROL Destination Mappings] 中的欄位 {#fields-in-dest-mappings}

在中 [!UICONTROL Segment Builder]，選 [!UICONTROL Add Destination] 擇後將顯示對話框 [!UICONTROL destination]。 此視窗會顯示與各欄位相關 [!UICONTROL destination] 的靜態資訊，這些欄位會依類型 [!UICONTROL destination] 而異。 在空白欄位中提供必要資訊以設定 [!UICONTROL destination mapping]。

>[!NOTE]
>
>出版日期為選擇性。 如果為空白，則目標會變為作用中且永不過期。

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] 欄位

在欄位 [!UICONTROL Destination Mapping] 中，指定用於傳送資料至的索引鍵值配對 [!UICONTROL destination]。 在第一個欄位中輸入鍵，在第二個欄位中輸入值。 您的 [!UICONTROL cookie destination] POP看起來可能類似以下：

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] 欄位

在和字 [!UICONTROL URL] 段中 [!UICONTROL Secure URL] ，指定用於向發送資料的完整標準或安全地址 [!UICONTROL destination]。

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] 欄位

在欄位 [!UICONTROL Destination Value] 中指定用於傳送資料至的值（鍵值對的一部分） [!UICONTROL destination]。

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [建立Cookie目標](../../features/destinations/create-cookie-destination.md)
>* [建立URL目標](../../features/destinations/create-url-destination.md)

