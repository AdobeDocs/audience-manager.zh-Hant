---
description: 說明如何使用區段產生器建立區段。
seo-description: 說明如何使用區段產生器建立區段。
seo-title: 區段產生器
solution: Audience Manager
title: 區段產生器
uuid: 5ca924a5-2b29-4802-ab02-e292 d77 a aae
translation-type: tm+mt
source-git-commit: b346dbe500f1e662c7b121a18c6cc0704ef3cfac

---


# 區段產生器 {#segment-builder}

Describes the required and optional steps that create a segment in [!UICONTROL Segment Builder].

## 建立區段 {#create-segment}

### 區段產生器區段

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 共個區段： [!UICONTROL Basic Information][!UICONTROL Traits]和 [!UICONTROL Destinations Mapping]。To create a segment, complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. [!UICONTROL Destinations Mapping] 設定為選用。請參閱下列指示以取得更多說明。

1. In the [Basic Information](../../features/segments/segment-builder.md#segment-builder-controls-basics) section:
   * 為區段命名。區段名稱的長度上限為255個字元。
   * 設定區段狀態(預設為作用中)。
   * 選擇資料來源。
   * 選取要用於區段資格的設定檔合併規則。
   * 將區段指派給儲存資料夾。
1. In the [Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits) section:
   * Search for the trait you want to add to a segment and click **[!UICONTROL Add Trait]**. 新增其他特徵以建立特徵群組。
   * Bring up the Advanced Search modal by clicking **[!UICONTROL Browse All Traits]**. 依名稱、ID、說明或資料來源搜尋特徵。在搜尋時按一下資料夾，將結果限制在該資料夾及其子檔案夾。您也可以依特徵類型篩選特徵。
   * Get live [trait recommendations](trait-recommendations.md) as you build your segment.
   * 按一下並拖曳特徵以建立個別群組。
   * Hover between groups to set relationships with Boolean [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] values.
   * Hover over the clock icon to add [recency and frequency](../../features/segments/recency-and-frequency.md) rules to the trait.
   * 在新增或移除特徵時檢視區段人口族群資料。Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers. Read more about [segment population data](../../features/segments/segment-builder-data.md#segment-populations) in the Segment Builder.
   * Click **[!UICONTROL Save]** when done.
1. *(可選)* 將區段對應 [至「目的地對應](../../features/segments/segment-builder.md#segment-builder-controls-destinations) 」區段中的目的地：
   * Search for the destination and click **[!UICONTROL Add Destination]**. 注意，您必須先存在目的地，才能將其新增至區段。
   * Click **[!UICONTROL Save]** when done.

## Segment Builder Controls: Basic Information Section {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] settings let you create new, or edit existing traits. 若要建立新區段，請提供名稱、資料來源，並選取儲存資料夾。所有其他欄位皆為選用欄位。Move on to the [!UICONTROL Traits] section when done.

<!-- r_segment_basic_info_section.xml -->

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>名稱</b> </td> 
   <td colname="col2"> <p>為區段提供描述其函數或用途的簡短邏輯名稱。避免縮寫和特殊字元。區段名稱的長度上限為255個字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>說明</b> </td> 
   <td colname="col2"> <p>欄位，以瞭解區段的其他描述性資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>整合代碼</b> </td> 
   <td colname="col2"> <p>使用者定義之ID或其他公司特定資訊的欄位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>資料來源</b> </td> 
   <td colname="col2"> <p>將區段與特定資料提供者關聯。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>描述檔合併規則</b> </td> 
   <td colname="col2"> <p>選取要用於區段資格的設定檔合併規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>狀態</b> </td> 
   <td colname="col2"> <p>啓用或停用區段(預設為作用中)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>資料夾儲存</b> </td> 
   <td colname="col2"> <p>判斷區段所屬的儲存資料夾。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment Builder Controls: Traits Section {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], the [!UICONTROL Traits] section lets you manage traits in a segment, create trait groups, and set qualification criteria. To add a trait to a segment, type the trait name in the search field and click [!UICONTROL Add Trait]. Save the trait (if finished) or move on to [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**必要條件：** 填寫 [!UICONTROL Basic Information] 區段中的必填欄位。

| 欄位 | 說明 |
|--- |--- |
| 基本檢視 | 本節提供視覺控制功能，可讓您： <ul><li>建立新區段並管理現有區段。</li><li>移除區段中的特徵。</li><li>新增高達50(最大)特徵至區段。</li><li>拖放特徵以建立新群組。</li><li>在區段中檢視特徵和特徵群組。</li><li>使用布林運算式、比較運算子和最近/頻率設定來設定資格標準。</li></ul> |
| 程式碼檢視 | 開啓開發環境，可讓您使用程式碼而非視覺化介面來建立和管理特徵、群組和資格需求。如果您的區段有下列情況，程式碼檢視很有用： <ul><li>在個別區段中包含超過50個特徵。注意：區段的限制為5000個特性(最大)。</li><li>包含許多特徵群組。</li><li>擁有複雜的資格需求。</li></ul> |
| 搜尋 | 協助您尋找要新增至區段的特性。 |
| 建議 | 取得類似特徵的即時建議，以新增至區段規則。Read more in [Trait Recommendations](trait-recommendations.md). |
| Real and Predicated Segment Size Data | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Remove Traits from a Segment {#remove-traits}

管理區段中的特徵是保持區段可行的重要部分。如果您需要從區段移除特徵，請遵循這些步驟。

從區段移除特徵：

1. Go to **Audience Data &gt; Segments**. 捲動清單或使用搜尋功能尋找您要使用的區段。
2. 按一下區段名稱以開啓區段詳細資訊畫面。
3. Click **Edit** to open Segment Builder and then click **Traits** to open the traits panel.
4. 將滑鼠指標暫留在您要刪除的特徵上，然後按一下X。此動作會立即從您的區段移除特徵。

## Segment Builder Controls: Destinations Mappings Section {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], the optional [!UICONTROL Destinations Mapping] section lets you send segment data to a third-party [!DNL cookie], [!DNL URL], or server-to-server destination. To add a destination, search (or browse) for a destination, provide destination specific information, and click **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### 必備條件

Complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. 此外，目的地必須已存在。

### 目的地對應搜尋工具

**[!UICONTROL Destination Mappings]** 面板包含搜尋工具，如下表所述。

| 搜尋類型 | 說明 |
|---|---|
| **依目的地名稱搜尋** | 可讓您依名稱搜尋特定目的地。若要搜尋，請開始輸入。欄位會根據您的搜尋詞自動完成。Click **[!UICONTROL Add Destination]** when done. |
| **瀏覽所有目的地** | Browse a list of *all* destinations available to you. 從快顯清單中選取並新增目的地至您的區段。 |

## Fields in the Destination Mappings Pop-up Windows {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], the [!UICONTROL Add Destination] dialog appears after you select a destination. 此視窗會顯示目標和欄位相關的靜態資訊，視目標類型而定。在空白欄位中提供必要的資訊，以設定目的地對應。

>[!NOTE]
>
>出版物日期為選擇性。當空白時，目的地會變成作用中，而永不過期。

<!-- r_add_mappings_pop.xml -->

### Cookie目的地欄位

In the [!UICONTROL Destination Mapping] fields, specify the key-value pairs used to send data to the destination. 在第一個欄位中輸入索引鍵，然後在第二個欄位中輸入值。您的Cookie目的地彈出式視窗看起來類似於：

![](assets/cookie_modal.PNG)

### URL目標欄位

In the [!UICONTROL URL] and [!UICONTROL Secure URL] fields, specify the complete standard or secure address used to send data to the destination.

![](assets/url_modal.PNG)

### 伺服器至伺服器目的地欄位

[!UICONTROL Destination Value] 在欄位中指定用來傳送資料至目的地的值(關鍵值配對的一部分)。

![](assets/s2s_modal.PNG)

>[!MORE_贊_ this]
>
>* [建立Cookie目的地](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [建立URL目的地](../../features/destinations/manage-destinations.md#configure-url-destination)

