---
description: 介紹如何使用段生成器建立段。
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: 區段產生器
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

描述在中建立段所需和可選的步驟 [!UICONTROL Segment Builder]。

## 視頻演示

從監視 [在Audience Manager視頻中建立段](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)。 視頻將引導您完成段建立過程。 有關詳細資訊，請閱讀以下各節。

## 建立 [!UICONTROL Segment] {#create-segment}

### 段生成器節

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 由3個不同部分組成： [!UICONTROL Basic Information]。 [!UICONTROL Traits], [!UICONTROL Destinations Mapping]。 建立 [!UICONTROL segment]，完成 [!UICONTROL Basic Information] 和 [!UICONTROL Traits] 的下界。 [!UICONTROL Destinations Mapping] 設定為可選。 有關其他幫助，請參閱下面的說明。

1. 在 [基本資訊](../../features/segments/segment-builder.md#segment-builder-controls-basics) 部分：

   ![建立段](assets/create-segment.png)

   * 命名 [!UICONTROL segment]。 最大長度 [!UICONTROL segment] 名稱為255個字元。
   * 設定 [!UICONTROL segment] 狀態（預設為活動）。
   * 選擇 [!UICONTROL data source]。 使用第一個下拉菜單在Audience Manager之間進行篩選 [!UICONTROL data sources]、Adobe Analytics報告套件或兩者。 然後，使用第二個下拉菜單來選擇 [!UICONTROL data source]。 如果您不使用Adobe Analytics報告套件， [!UICONTROL data source] 類型選擇器被禁用，且僅預設為Audience Manager資料源。
   * 選擇 [!UICONTROL profile merge rule] 用於 [!UICONTROL segment] 資格。
   * 分配 [!UICONTROL segment] 到儲存資料夾。

1. 在 [性狀](../../features/segments/segment-builder.md#segment-builder-controls-traits) 部分：
   ![段構建器特徵](assets/segment-builder-traits.png)
   * 搜索 [!UICONTROL trait] 要添加到段，然後按一下 **[!UICONTROL Add Trait]**。 添加其他 [!UICONTROL trait] 建立 [!UICONTROL trait] 組。
   * 將 [!UICONTROL Advanced Search] 按一下 **[!UICONTROL Browse All Traits]**。 搜索 [!UICONTROL traits] 按名稱、ID、說明或 [!UICONTROL data source]。 在搜索時按一下資料夾，將結果限制到該資料夾及其子資料夾。 也可以篩選 [!UICONTROL traits] 按 [!UICONTROL trait type] ([!UICONTROL Folder Trait]。 [!UICONTROL Rule-based]。 [!UICONTROL Onboarded], [!UICONTROL Algorithmic])或人口類型([設備ID](../../reference/ids-in-aam.md) 和 [跨設備ID](../../reference/ids-in-aam.md))。
      ![段構建器 — 瀏覽器特徵](assets/segment-builder-browse-traits.png)
   * 即時 [特性建議](trait-recommendations.md) 當你 [!UICONTROL segment]。
   * 按一下並拖動 [!UICONTROL traits] 建立單獨的組。
   * 在組之間懸停以設定與布爾型的關係 [!UICONTROL AND]。 [!UICONTROL OR]。 [!UICONTROL AND NOT] 值。
   * 懸停在要添加的時鐘錶徵圖上 [頻率](../../features/segments/recency-and-frequency.md) 規則 [!UICONTROL trait]。
   * 在添加或刪除段填充資料時查看段填充資料 [!UICONTROL traits]。 按一下 **[!UICONTROL Calculate Estimates]** 查看（或刷新）估計的人口數。 閱讀有關 [段填充資料](../../features/segments/segment-builder-data.md#segment-populations) 的 [!UICONTROL Segment Builder]。
   * 按一下 **[!UICONTROL Save]** 完成。

1. *（可選）* 映射 [!UICONTROL segment] 到 [!UICONTROL destination] 的 [目標映射](../../features/segments/segment-builder.md#segment-builder-controls-destinations) 部分：
   * 搜索 [!UICONTROL destination] 按一下 **[!UICONTROL Add Destination]**。 注意， [!UICONTROL destination] 必須已存在，然後才能將其添加到 [!UICONTROL segment]。
   * 按一下 **[!UICONTROL Save]** 完成。

觀看下面的視頻，詳細瞭解跨設備指標的工作原理。

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] 控制項： [!UICONTROL Basic Information] 節 {#segment-builder-controls-basics}

在 [!UICONTROL Segment Builder]。 [!UICONTROL the Basic Information] 設定允許您建立新特徵或編輯現有特徵。 建立新 [!UICONTROL segment]，提供名稱， [!UICONTROL data source]，然後選擇儲存資料夾。 所有其它欄位都是可選的。 轉到 [!UICONTROL Traits] 的子菜單。

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
| **[!UICONTROL Name]** | 為段提供一個簡短的邏輯名稱，用於描述其功能或用途。 避免縮寫和特殊字元。 段名稱的最大長度為255個字元。 |
| **[!UICONTROL Description]** | 有關段的附加說明性資訊的欄位。 |
| **[!UICONTROL Integration Code]** | 用戶定義的ID或其他公司特定資訊的欄位。 |
| **[!UICONTROL Data Source]** | 將段與特定資料提供程式關聯。 <br> 使用第一個下拉菜單在Audience Manager資料源、Adobe Analytics報告套件或兩者之間進行篩選。 然後，使用第二個下拉菜單選擇資料源。 <br> 如果未使用Adobe Analytics報表套件，則資料源類型選擇器將被禁用，並且預設為僅Audience Manager資料源。 |
| **[!UICONTROL Profile Merge Rule]** | 選擇要用於段限定的配置檔案合併規則。 |
| **[!UICONTROL Status]** | 激活或停用段（預設情況下為活動）。 |
| **資料夾儲存** | 確定段所屬的儲存資料夾。 |

## [!UICONTROL Segment Builder] 控制項： [!UICONTROL Traits] 節 {#segment-builder-controls-traits}

在 [!UICONTROL Segment Builder]，也請參見Wiki頁。 [!UICONTROL Traits] 部分用於管理 [!UICONTROL traits] 在 [!UICONTROL segment]建立 [!UICONTROL trait] 組和設定資格標準。 添加 [!UICONTROL trait] 到 [!UICONTROL segment]的子菜單。 [!UICONTROL trait] 在搜索欄位中輸入名稱，然後按一下 [!UICONTROL Add Trait]。 保存 [!UICONTROL trait] （如果完成）或移到 [!UICONTROL Destinations Mapping]。

<!-- r_segment_traits_section.xml-->

**先決條件：** 完成 [!UICONTROL Basic Information] 的子菜單。

| 欄位 | 說明 |
|--- |--- |
| **[!UICONTROL Basic View]** | 本部分提供可視控制項，讓您： <ul><li>新建並管理現有 [!UICONTROL segments]。</li><li>刪除 [!UICONTROL traits] 從 [!UICONTROL segment]。</li><li>最多50（最大值） [!UICONTROL traits] 到 [!UICONTROL segment]。</li><li>拖放 [!UICONTROL traits] 的子菜單。</li><li>視圖 [!UICONTROL traits] 和 [!UICONTROL trait] 組 [!UICONTROL segment]。</li><li>使用布爾表達式、比較運算子和頻率/頻率設定設定限定條件。</li></ul> |
| **[!UICONTROL Code View]** | 開啟一個開發環境，該環境允許您建立和管理 [!UICONTROL traits]、組和資格要求，使用代碼而不是可視介面。 如果您 [!UICONTROL segments]: <ul><li>包含50個以上 [!UICONTROL traits] 在 [!UICONTROL segment]。 注： [!UICONTROL Segments] 限於5000 [!UICONTROL traits] （最大值）。</li><li>包含許多 [!UICONTROL trait] 組。</li><li>具有複雜的資格要求。</li></ul> |
| 搜尋 | 幫助您查找 [!UICONTROL traits] 添加到 [!UICONTROL segment]。 |
| 建議 | 獲取類似項的即時建議 [!UICONTROL traits]，來自你的第一黨 [!UICONTROL traits] 和 [!UICONTROL Audience Marketplace] 您訂閱的資料源。 將這些建議添加到 [!UICONTROL segment] 規則以擴大受眾。 更多內容 [特萊Recommendations](trait-recommendations.md)。 |
| **[!UICONTROL Marketplace Recommendations]** | 獲取類似項的即時建議 [!UICONTROL traits]從 [!UICONTROL Audience Marketplace] 您未訂閱的資料源。 更多內容 [特萊Recommendations](trait-recommendations.md)。 |
| 實數和估計 [!UICONTROL Segment] 大小資料 | 請參閱[區段產生器的特徵和區段母體資料](segment-builder-data.md)。 |

## 刪除 [!UICONTROL Traits] 從 [!UICONTROL Segment] {#remove-traits}

管理 [!UICONTROL traits] 在 [!UICONTROL segments] 是保持 [!UICONTROL segments] 可行。 如果需要刪除，請執行以下步驟 [!UICONTROL traits] 從 [!UICONTROL segment]。

刪除 [!UICONTROL traits] 從 [!UICONTROL segment]:

1. 轉到 **[!UICONTROL Audience Data > Segments]**。 瀏覽清單或使用搜索功能查找 [!UICONTROL segment] 你想一起工作。
2. 按一下 [!UICONTROL segment] 開啟的名稱 [!UICONTROL segment] 詳細資訊螢幕。
3. 按一下 **編輯** 開啟 [!UICONTROL Segment Builder] 然後按一下 **性狀** 開啟 [!UICONTROL traits] 的子菜單。
4. 懸停在 [!UICONTROL trait] 刪除，然後按一下X。此操作將立即刪除 [!UICONTROL trait] 從 [!UICONTROL segment]。

## [!UICONTROL Segment Builder] 控制項： [!UICONTROL Destinations Mappings] 節 {#segment-builder-controls-destinations}

在 [!UICONTROL Segment Builder]，可選 [!UICONTROL Destinations Mapping] 部分，用於發送 [!UICONTROL segment] 資料到第三方 [!DNL cookie]。 [!DNL URL]或 [!UICONTROL server-to-server destination]。 添加 [!UICONTROL destination]，搜索（或瀏覽） [!UICONTROL destination]提供 [!UICONTROL destination] 特定資訊，然後按一下 **[!UICONTROL Add Destination]**。

<!-- r_segment_destinations_map.xml -->

### 必要條件

完成 [!UICONTROL Basic Information] 和 [!UICONTROL Traits] 的下界。 此外，目標必須已存在。

### [!UICONTROL Destination Mappings] 搜索工具

的 **[!UICONTROL Destination Mappings]** 面板包含下表中所述的搜索工具。

| 搜尋類型 | 說明 |
|---|---|
| **[!UICONTROL Search by Destination Name]** | 用於搜索特定 [!UICONTROL destination] 姓名。 要搜索，請開始鍵入。 該欄位將根據您的搜索詞自動完成。 按一下 **[!UICONTROL Add Destination]** 完成。 |
| **[!UICONTROL Browse All Destinations]** | 瀏覽清單 *全部* [!UICONTROL destinations] 的下界。 選擇並添加 [!UICONTROL destinations] 到 [!UICONTROL segment] 的子菜單。 |

## 中的欄位 [!UICONTROL Destination Mappings] 彈出窗口 {#fields-in-dest-mappings}

在 [!UICONTROL Segment Builder]，也請參見Wiki頁。 [!UICONTROL Add Destination] 在您選擇 [!UICONTROL destination]。 此窗口顯示有關 [!UICONTROL destination] 以及根據不同 [!UICONTROL destination] 的雙曲餘切值。 在空欄位中提供所需資訊以設定 [!UICONTROL destination mapping]。

>[!NOTE]
>
>發佈日期是可選的。 如果為空，則目標將變為活動狀態且永不過期。

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] 欄位

在 [!UICONTROL Destination Mapping] 欄位中，指定用於向 [!UICONTROL destination]。 在第一個欄位中輸入鍵，在第二個欄位中輸入值。 您 [!UICONTROL cookie destination] pop可能看起來類似：

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] 欄位

在 [!UICONTROL URL] 和 [!UICONTROL Secure URL] 欄位中，指定用於向 [!UICONTROL destination]。

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] 欄位

在 [!UICONTROL Destination Value] 欄位指定用於向 [!UICONTROL destination]。

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [建立Cookie目標](../../features/destinations/create-cookie-destination.md)
>* [建立URL目標](../../features/destinations/create-url-destination.md)

