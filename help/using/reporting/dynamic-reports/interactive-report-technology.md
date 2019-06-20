---
description: 說明支援互動式報表和資料更新排程的基礎軟體。
seo-description: 說明支援互動式報表和資料更新排程的基礎軟體。
seo-title: Report Technology
solution: Audience Manager
title: Report Technology
uuid: 5f3d815b-e1 e6-42f2-b848-ac035 a5 aa77 d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# Report Technology{#report-technology}

說明支援互動式報表和資料更新排程的基礎軟體。

<!-- 

c_report_technology.xml

 -->

## 互動式報表使用Tableau技術

[!DNL Audience Manager] 使用 [Tableau](https://www.tableausoftware.com/) 軟體在互動式報表中顯示資料。With [!DNL Tableau], the [!UICONTROL Delivery and Overlap] reports use visual cues and symbols that help you:

* 尋找高和低效能的特性。
* 區分低和高獨特訪客重疊的特徵特徵和區段。
* 使用重疊資料建立目標群體。
* 識別低重疊的相關特徵，以擴大覆蓋範圍。

## 資料更新排程

報告資料每周會每周更新。更新會處理從週六(前一天)到上一周日的資料。

## Shapes, Colors, and Sizes Used in Interactive Reports {#shapes-colors-sizes}

大部分的互動報表都會使用不同尺寸和顏色的形狀顯示結果。此顯示格式可協助您以視覺化方式呈現資料，而不需透過行數和行數來浪費。

<!-- 

r_legend.xml

 -->

### 報表圖例

下表定義動態報表中使用的形狀、大小和顏色。

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 資料元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>形狀</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">社交圈表示您自己的第一方特徵。 </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">方形表示第三方特徵。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>色彩</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Red shades indicate <i>low</i> overlap. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Green shades indicate <i>high</i> overlap. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>大小</b> </td> 
   <td colname="col2"> 大小會以直接比例增加或減少(特徵或區段中的點按次數或獨特使用者的百分比或百分比)。 </td> 
  </tr> 
 </tbody> 
</table>

## Report Icons and Tools Explained {#icons-tools-explained}

說明如何搜尋和使用動態報表中使用的各種圖示工具。

<!-- 

r_icons.xml

 -->

### 資料圖示和工具

每個動態報表視窗底部提供下列圖示工具。下圖提供這些工具的更多資訊。

![](assets/tools_icons90.png)

### 匯出資料

此工具可讓您從報表匯出種不同格式的資料。

| 匯出選項 | 匯出資料 |
|---|---|
| **[!UICONTROL Image]** | 做為影像(. png)檔案。當您想要下載並共用其原始格式的報表資料時有用。 |
| **[!UICONTROL PDF]** | 做為PDF檔案。 |
| **[!UICONTROL Data]** | 在新的瀏覽器視窗中，為欄和列的數值資料。 |
| **[!UICONTROL Crosstab]** | 為. csv檔案。 |

### 回復變更

選取此工具可還原您在報表上執行的任何互動式點擊變更。

### 自動更新

The [!UICONTROL Delivery-Performance] and [!UICONTROL Trait-to-Trait Overlap] reports are dynamic reports that respond and change based on user click actions.

For example, say you want to select several advertisers in the [!UICONTROL Overlap] report. 啓用後，自動更新會在您選取核取方塊時立即開始傳回資料。此動態行為可能會中斷您的工作流程，因為您必須等候報表完成處理，才能選擇其他廣告商。使用此工具可視需要將該功能關閉(及再次開啓)。

### 重新整理資料

按一下重新整理圖示以執行報表或重新載入資料集。自動更新關閉時，按一下重新整理以執行或更新報表。

### 搜尋工具

搜尋由一般放大鏡圖示(未顯示)表示。搜尋欄位會隱藏，直到您按一下畫面左側的選取標籤。下表說明每個報表的搜尋工具位置。

| 報告 | 若要尋找搜尋，請將滑鼠指標暫留在 |
|---|---|
| [!UICONTROL Delivery and Performance] 報告 | 「廣告商名稱」標籤。 |
| [!UICONTROL Overlap] reports | 「SID Name」標籤。 |
