---
description: 說明支援互動式報表和資料更新排程的基礎軟體。
seo-description: 說明支援互動式報表和資料更新排程的基礎軟體。
seo-title: 報告技術
solution: Audience Manager
title: 報告技術
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# 報告技術{#report-technology}

說明支援互動式報表和資料更新排程的基礎軟體。

<!-- 

c_report_technology.xml

 -->

## 互動式報表使用Tableau技術

[!DNL Audience Manager] 使用 [Tableau軟體](https://www.tableausoftware.com/) ，在互動式報表中顯示資料。 有了 [!DNL Tableau]，報 [!UICONTROL Delivery and Overlap] 表會使用視覺提示和符號來協助您：

* 尋找高效能與低效能特性。
* 找出具有低獨特訪客與高獨特訪客重疊的特徵與區段。
* 使用重疊資料建立目標區段。
* 透過識別低重疊的相關特性來擴展觸及面。

## 資料更新排程

每個星期日每週更新報告資料。 此更新會處理星期六（前一天）至上個星期日的資料。

## 互動式報表中使用的形狀、顏色和大小 {#shapes-colors-sizes}

大部分的互動式報表都使用不同大小和顏色的形狀來顯示結果。 此顯示格式可協助您以視覺化方式瞭解資料，而不需涉及行和列數。

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
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">社交圈會指出您自己的第一方特徵。 </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">方塊表示協力廠商特徵。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>色彩</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">紅色陰影表 <i>示低</i> 重疊。 </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">綠色表示高 <i>重疊</i> 。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>大小</b> </td> 
   <td colname="col2"> 大小會隨著觸及率（特徵或區段中的點按次數或獨特使用者的百分比）而增加或減少。 </td> 
  </tr> 
 </tbody> 
</table>

## 說明的報表圖示和工具 {#icons-tools-explained}

說明如何搜尋和使用動態報表中使用的各種圖示工具。

<!-- 

r_icons.xml

 -->

### 資料圖示和工具

每個動態報表視窗的底部提供下列圖示工具。 下圖提供這些工具的詳細資訊。

![](assets/tools_icons90.png)

### 匯出資料

此工具可讓您以4種不同格式匯出報表中的資料。

| 匯出選項 | 匯出資料 |
|---|---|
| **[!UICONTROL Image]** | 以影像(.png)檔案的形式。 當您想要以原始的圖形格式下載並共用報表資料時，此功能十分有用。 |
| **[!UICONTROL PDF]** | 以PDF檔案的形式。 |
| **[!UICONTROL Data]** | 在新的瀏覽器視窗中，以欄和列的數值資料顯示。 |
| **[!UICONTROL Crosstab]** | 以。csv檔案形式。 |

### 還原更改

選取此工具可還原您對報表所執行的任何互動式點按變更。

### 自動更新

和報 [!UICONTROL Delivery-Performance] 表 [!UICONTROL Trait-to-Trait Overlap] 是動態報表，會根據使用者點按動作來回應和變更。

例如，假設您想在報表中選取數個廣告商 [!UICONTROL Overlap] 。 啟用後，自動更新會在您選取核取方塊後立即開始傳回資料。 此動態行為可能會中斷您的工作流程，因為您必須等到報表處理完成後，再選取其他廣告商。 請視需要使用此工具來關閉該功能（並再次開啟）。

### 重新整理資料

按一下重新整理圖示以執行報表或重新載入資料集。 關閉自動更新時，按一下重新整理以執行或更新報表。

### 搜尋工具

搜尋由一般放大鏡圖示（未顯示）表示。 搜尋欄位會隱藏，直到您按一下畫面左側的選取範圍標籤為止。 下表說明每個報表的搜尋工具位置。

| 報告 | 若要尋找搜尋，請將滑鼠暫留在 |
|---|---|
| [!UICONTROL Delivery and Performance] 報告 | 「廣告商名稱」標籤。 |
| [!UICONTROL Overlap] 報表 | 「SID名稱」標籤。 |
