---
description: 說明如何使用區段產生器建立區段。
seo-description: 說明如何使用區段產生器建立區段。
seo-title: 區段產生器
solution: Audience Manager
title: 區段產生器
uuid: 5ca924a5-2b29-4802-ab02-e292 d77 a aae
translation-type: tm+mt
source-git-commit: 0d0806ef2c84b4770adc29d668351ac3f2d8cc5f

---


# 區段產生器 {#segment-builder}

說明建立區段的必要和選擇性步驟 [!UICONTROL Segment Builder]。

## 影片展示

首先，請觀看Audience Manager視訊 [中的建立區段](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)。影片會逐步帶您完成區段建立程序。請閱讀以下章節以瞭解更多資訊。

## 建立區段 {#create-segment}

### 區段產生器區段

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] 共個區段： [!UICONTROL Basic Information][!UICONTROL Traits]和 [!UICONTROL Destinations Mapping]。若要建立區段，請完成 [!UICONTROL Basic Information] 和 [!UICONTROL Traits] 區段中的必填欄位。[!UICONTROL Destinations Mapping] 設定為選用。請參閱下列指示以取得更多說明。

1. 在 [「基本資訊](../../features/segments/segment-builder.md#segment-builder-controls-basics) 」區段中：
   * 為區段命名。區段名稱的長度上限為255個字元。
   * 設定區段狀態(預設為作用中)。
   * 選擇資料來源。
   * 選取要用於區段資格的設定檔合併規則。
   * 將區段指派給儲存資料夾。
1. 在 [「特徵](../../features/segments/segment-builder.md#segment-builder-controls-traits) 」區段中：
   * 搜尋您要新增至區段並按一下 **[!UICONTROL Add Trait]**&#x200B;的特徵。新增其他特徵以建立特徵群組。
   * 按一下 **[!UICONTROL Browse All Traits]**，即可啓動進階搜尋模式。依名稱、ID、說明或資料來源搜尋特徵。在搜尋時按一下資料夾，將結果限制在該資料夾及其子檔案夾。您也可以依特徵類型篩選特徵。
   * 建立區段時，獲取即時 [特徵建議](trait-recommendations.md) 。
   * 按一下並拖曳特徵以建立個別群組。
   * 將群組暫留在群組之間，以設定與布林 [!UICONTROL AND]值、 [!UICONTROL OR][!UICONTROL AND NOT] 值的關係。
   * 將滑鼠指標暫留在時鐘圖示上，可在特徵中加入 [最近的頻率和頻率](../../features/segments/recency-and-frequency.md) 規則。
   * 在新增或移除特徵時檢視區段人口族群資料。按一下 **[!UICONTROL Calculate Estimates]** 以查看(或重新整理)預計的人口數目。詳細瞭解區段產生器中 [區段人口族群資料](../../features/segments/segment-builder-data.md#segment-populations) 。
   * Click **[!UICONTROL Save]** when done.
1. *(可選)* 將區段對應 [至「目的地對應](../../features/segments/segment-builder.md#segment-builder-controls-destinations) 」區段中的目的地：
   * 搜尋目的地並按一下 **[!UICONTROL Add Destination]**。注意，您必須先存在目的地，才能將其新增至區段。
   * Click **[!UICONTROL Save]** when done.

## 區段產生器控制項：基本資訊區段 {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder]、 [!UICONTROL the Basic Information] settings callets you create new，or editing existing features.若要建立新區段，請提供名稱、資料來源，並選取儲存資料夾。所有其他欄位皆為選用欄位。完成時，請移至 [!UICONTROL Traits] 區段。

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

## 區段產生器控制項：特徵區段 {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder]，the [!UICONTROL Traits] section可讓您管理區段中的特徵、建立特徵群組，以及設定符合條件。若要將特徵新增至區段，請在搜尋欄位中輸入特徵名稱，然後按一下 [!UICONTROL Add Trait]。儲存特徵(如果已完成)或移至 [!UICONTROL Destinations Mapping]。

<!-- r_segment_traits_section.xml -->

**必要條件：** 填寫 [!UICONTROL Basic Information] 區段中的必填欄位。

| 欄位 | 說明 |
|--- |--- |
| 基本檢視 | 本節提供視覺控制功能，可讓您： <ul><li>建立新區段並管理現有區段。</li><li>移除區段中的特徵。</li><li>新增高達50(最大)特徵至區段。</li><li>拖放特徵以建立新群組。</li><li>在區段中檢視特徵和特徵群組。</li><li>使用布林運算式、比較運算子和最近/頻率設定來設定資格標準。</li></ul> |
| 程式碼檢視 | 開啓開發環境，可讓您使用程式碼而非視覺化介面來建立和管理特徵、群組和資格需求。如果您的區段有下列情況，程式碼檢視很有用： <ul><li>在個別區段中包含超過50個特徵。注意：區段的限制為5000個特性(最大)。</li><li>包含許多特徵群組。</li><li>擁有複雜的資格需求。</li></ul> |
| 搜尋 | 協助您尋找要新增至區段的特性。 |
| 建議 | 取得類似特徵的即時建議，以新增至區段規則。深入瞭解 [特徵Recommendations](trait-recommendations.md)。 |
| Real and Predicated Segment Size Data | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## 從區段移除特徵 {#remove-traits}

管理區段中的特徵是保持區段可行的重要部分。如果您需要從區段移除特徵，請遵循這些步驟。

從區段移除特徵：

1. 前往 **「對象資料&gt;區段**」。捲動清單或使用搜尋功能尋找您要使用的區段。
2. 按一下區段名稱以開啓區段詳細資訊畫面。
3. 按一下 **「編輯** 」開啓區段產生器，然後按一下 **「特徵** 」以開啓特徵面板。
4. 將滑鼠指標暫留在您要刪除的特徵上，然後按一下X。此動作會立即從您的區段移除特徵。

## 區段產生器控制項：目標對應區段 {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder]，the optional [!UICONTROL Destinations Mapping] section可讓您將區段資料傳送至第三方 [!DNL cookie]、 [!DNL URL]伺服器或伺服器至伺服器目的地。若要新增目的地、搜尋(或瀏覽)目的地、提供目的地特定資訊，然後按一下。**[!UICONTROL Add Destination]**

<!-- r_segment_destinations_map.xml -->

### 必備條件

填寫 [!UICONTROL Basic Information] 和 [!UICONTROL Traits] 區段中的必填欄位。此外，目的地必須已存在。

### 目的地對應搜尋工具

**[!UICONTROL Destination Mappings]** 面板包含搜尋工具，如下表所述。

| 搜尋類型 | 說明 |
|---|---|
| **依目的地名稱搜尋** | 可讓您依名稱搜尋特定目的地。若要搜尋，請開始輸入。欄位會根據您的搜尋詞自動完成。Click **[!UICONTROL Add Destination]** when done. |
| **瀏覽所有目的地** | 瀏覽所有 ** 目的地的清單。從快顯清單中選取並新增目的地至您的區段。 |

## 目的地映射彈出式視窗中的欄位 {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder]，the [!UICONTROL Add Destination] dialog display after you select a target.此視窗會顯示目標和欄位相關的靜態資訊，視目標類型而定。在空白欄位中提供必要的資訊，以設定目的地對應。

>[!NOTE]
>
>出版物日期為選擇性。當空白時，目的地會變成作用中，而永不過期。

<!-- r_add_mappings_pop.xml -->

### Cookie目的地欄位

在 [!UICONTROL Destination Mapping] 欄位中，指定用來傳送資料至目的地的索引鍵值配對。在第一個欄位中輸入索引鍵，然後在第二個欄位中輸入值。您的Cookie目的地彈出式視窗看起來類似於：

![](assets/cookie_modal.PNG)

### URL目標欄位

在 [!UICONTROL URL] 和 [!UICONTROL Secure URL] 欄位中，指定用來傳送資料至目的地的完整標準或安全地址。

![](assets/url_modal.PNG)

### 伺服器至伺服器目的地欄位

[!UICONTROL Destination Value] 在欄位中指定用來傳送資料至目的地的值(關鍵值配對的一部分)。

![](assets/s2s_modal.PNG)

>[!MORE_贊_ this]
>
>* [建立Cookie目的地](../../features/destinations/create-cookie-destination.md)
>* [建立URL目的地](../../features/destinations/create-url-destination.md)

