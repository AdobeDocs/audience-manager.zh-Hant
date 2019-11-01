---
description: 說明如何使用區段產生器建立區段。
seo-description: 說明如何使用區段產生器建立區段。
seo-title: 區段產生器
solution: Audience Manager
title: 區段產生器
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0ae
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 區段產生器 {#segment-builder}

說明在中建立區段的必要和選用步驟 [!UICONTROL Segment Builder]。

## 視訊展示

首先，在Audience manager影片 [中觀看「建立區段」](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)。 視訊會逐步帶您進行區段建立程式。 請閱讀以下章節以取得詳細資訊。

## 建立區段 {#create-segment}

### 區段產生器區段

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 包含3個不同的部分： [!UICONTROL Basic Information]、 [!UICONTROL Traits]和 [!UICONTROL Destinations Mapping]。 若要建立區段，請填妥和區段中的必 [!UICONTROL Basic Information] 填欄 [!UICONTROL Traits] 位。 [!UICONTROL Destinations Mapping] 設定為選用。 請參閱以下說明以取得其他說明。

![create-segment](assets/create-segment.png)

1. 在「基 [本資訊](../../features/segments/segment-builder.md#segment-builder-controls-basics) 」部分：
   * 命名區段。 區段名稱的最大長度為255個字元。
   * 設定區段狀態（預設為作用中）。
   * 選擇資料來源。 使用第一個下拉式選單，在Audience manager資料來源、Adobe Analytics報表套裝或兩者之間進行篩選。 然後，使用第二個下拉式選單來選擇您的資料來源。 如果您未使用Adobe Analytics報表套裝，資料來源類型選擇器會停用，並預設為僅限Audience manager資料來源。
   * 選擇用於區段限定的描述檔合併規則。
   * 將區段指派至儲存資料夾。
2. 在「特 [徵](../../features/segments/segment-builder.md#segment-builder-controls-traits) 」區段：
   * 搜尋您要新增至區段的特徵，然後按一下 **[!UICONTROL Add Trait]**。 新增另一個特徵以建立特徵群組。
   * 按一下以開啟「進階搜尋」模式 **[!UICONTROL Browse All Traits]**。 依名稱、ID、說明或資料來源搜尋特徵。 在搜索時按一下一個資料夾，將結果限制在該資料夾及其子資料夾。 您也可以依特徵類型篩選特徵。
   * 建立區 [段時取得](trait-recommendations.md) 「即時特徵」建議。
   * 按一下並拖曳特徵以建立個別群組。
   * 將滑鼠指標暫留在群組之間，以設定與布 [!UICONTROL AND]爾值、 [!UICONTROL OR]值的 [!UICONTROL AND NOT] 關係。
   * 將滑鼠指標暫留在時鐘圖示上 [，將時近和頻率](../../features/segments/recency-and-frequency.md) 規則新增至特徵。
   * 在您新增或移除特徵時檢視區段人口資料。 按一下 **[!UICONTROL Calculate Estimates]** 查看（或刷新）估計的人口數。 在「區段產生 [器」中，閱讀](../../features/segments/segment-builder-data.md#segment-populations) 「區段人口資料」的更多資訊。
   * Click **[!UICONTROL Save]** when done.
3. *（可選）* 「目標對應」區段中的目標對 [應區段](../../features/segments/segment-builder.md#segment-builder-controls-destinations) :
   * 搜索目標並按一下 **[!UICONTROL Add Destination]**。 請注意，目標必須已存在，您才能將其新增至區段。
   * Click **[!UICONTROL Save]** when done.

## 區段產生器控制：基本資訊部分 {#segment-builder-controls-basics}

在中 [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] 設定可讓您建立新特徵或編輯現有特徵。 若要建立新區段，請提供名稱、資料來源，並選取儲存資料夾。 所有其他欄位皆為選用。 完成時，請移 [!UICONTROL Traits] 至區段。

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
   <td colname="col2"> <p>為區段指定簡短的邏輯名稱，以說明其功能或用途。 避免縮寫和特殊字元。 區段名稱的最大長度為255個字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>說明</b> </td> 
   <td colname="col2"> <p>欄位，以取得區段的其他說明性資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>整合代碼</b> </td> 
   <td colname="col2"> <p>使用者定義ID或其他公司特定資訊的欄位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>資料來源</b> </td> 
   <td colname="col2"> <p>將區段與特定資料提供者關聯。 <p>使用第一個下拉式選單，在Audience manager資料來源、Adobe Analytics報表套裝或兩者之間進行篩選。 然後，使用第二個下拉式選單來選擇您的資料來源。</p><p> 如果您未使用Adobe Analytics報表套裝，資料來源類型選擇器會停用，並預設為僅限Audience manager資料來源。</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>描述檔合併規則</b> </td> 
   <td colname="col2"> <p>選擇用於區段限定的描述檔合併規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>狀態</b> </td> 
   <td colname="col2"> <p>啟動或停用區段（預設為活動）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>資料夾儲存</b> </td> 
   <td colname="col2"> <p>確定段所屬的儲存資料夾。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 區段產生器控制：特徵區段 {#segment-builder-controls-traits}

在中 [!UICONTROL Segment Builder]，此 [!UICONTROL Traits] 區段可讓您管理區段中的特徵、建立特徵群組，以及設定限定條件。 若要新增特徵至區段，請在搜尋欄位中輸入特徵名稱，然後按一下 [!UICONTROL Add Trait]。 儲存特徵（如果完成）或移至 [!UICONTROL Destinations Mapping]。

<!-- r_segment_traits_section.xml -->

**** 必要條件：填寫章節中的必填 [!UICONTROL Basic Information] 欄位。

| 欄位 | 說明 |
|--- |--- |
| 基本檢視 | 本節提供視覺控制項，可讓您： <ul><li>建立新區段並管理現有區段。</li><li>從區段移除特徵。</li><li>將最多50個（最多）特徵加入群體。</li><li>拖放特徵以建立新群組。</li><li>在區段中檢視特徵和特徵群組。</li><li>使用布林運算式、比較運算子和時近／頻率設定來設定限定條件。</li></ul> |
| 程式碼檢視 | 開啟開發環境，可讓您使用程式碼來建立和管理特徵、群組和資格要求，而非使用視覺化介面。 如果您的區段： <ul><li>在個別區段中包含50個以上的特徵。 注意：區段限制為5000個特徵（最大值）。</li><li>包含許多特徵群組。</li><li>具備複雜的資格要求。</li></ul> |
| 搜尋 | 協助您尋找要新增至群體的特徵。 |
| 建議 | 取得要新增至區段規則之類似特徵的即時建議。 閱讀更多有關特徵 [建議的資訊](trait-recommendations.md)。 |
| 實際和估計的區段大小資料 | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## 從區段移除特徵 {#remove-traits}

管理區段中的特徵是維持區段可行性的重要部分。 如果您需要從區段移除特徵，請依照下列步驟進行。

若要從區段移除特徵：

1. 前往「 **讀者資料&gt;區段」**。 捲動清單或使用搜尋功能來尋找您要使用的區段。
2. 按一下區段名稱以開啟區段詳細資訊畫面。
3. 按一 **下「編輯** 」以開啟「區段產生器」，然後按一下「 **特徵** 」以開啟特徵面板。
4. 將滑鼠指標暫留在您要刪除的特徵上，然後按一下X。此動作會立即從您的區段中移除特徵。

## 區段產生器控制：「目標映射」部分 {#segment-builder-controls-destinations}

在中 [!UICONTROL Segment Builder]，選 [!UICONTROL Destinations Mapping] 用區段可讓您傳送區段資料至協力廠商、 [!DNL cookie][!DNL URL]或伺服器對伺服器目的地。 若要新增目標，請搜尋（或瀏覽）目標、提供目標特定資訊，然後按一下 **[!UICONTROL Add Destination]**。

<!-- r_segment_destinations_map.xml -->

### 必備條件

填寫和區段中的必 [!UICONTROL Basic Information] 填 [!UICONTROL Traits] 欄位。 此外，目標必須已存在。

### 目標映射搜索工具

面 **[!UICONTROL Destination Mappings]** 板包含下表所述的搜尋工具。

| 搜尋類型 | 說明 |
|---|---|
| **依目標名稱搜尋** | 可讓您依名稱搜尋特定目的地。 若要搜尋，請開始輸入。 欄位將根據您的搜尋詞自動完成。 Click **[!UICONTROL Add Destination]** when done. |
| **瀏覽所有目標** | 瀏覽所有可 *用目* 標的清單。 從快顯清單中選取目標並新增至您的區段。 |

## 「目標映射」彈出式窗口中的欄位 {#fields-in-dest-mappings}

在中 [!UICONTROL Segment Builder]，選 [!UICONTROL Add Destination] 擇目標後將顯示該對話框。 此窗口顯示有關目標和欄位的靜態資訊，這些欄位會根據目標類型而有所不同。 在空白欄位中提供必要資訊以設定目標對應。

>[!NOTE]
>
>出版日期為選擇性。 如果為空白，則目標會變為作用中且永不過期。

<!-- r_add_mappings_pop.xml -->

### Cookie目標欄位

在欄位 [!UICONTROL Destination Mapping] 中，指定用於傳送資料至目的地的索引鍵值配對。 在第一個欄位中輸入鍵，在第二個欄位中輸入值。 您的Cookie目標快顯視窗看起來可能類似下列：

![](assets/cookie_modal.PNG)

### URL目標欄位

在和字 [!UICONTROL URL] 段中 [!UICONTROL Secure URL] ，指定用於將資料發送到目標的完整標準或安全地址。

![](assets/url_modal.PNG)

### 伺服器對伺服器目標欄位

在欄位 [!UICONTROL Destination Value] 中指定用來傳送資料至目的地的值（鍵值對的一部分）。

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [建立Cookie目標](../../features/destinations/create-cookie-destination.md)
>* [建立URL目標](../../features/destinations/create-url-destination.md)

