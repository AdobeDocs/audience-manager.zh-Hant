---
description: 說明支援互動式報表和資料更新排程的基礎軟體。
seo-description: 說明支援互動式報表和資料更新排程的基礎軟體。
seo-title: 報表技術
solution: Audience Manager
title: 報表技術
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 3%

---


# 報表技術{#report-technology}

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

## Tableau檔案 {#tableau-documentation}

若要進一步瞭解您可在互動式報表中看到的Tableau控制項，請參閱Linux 2018.2上 [Tableau Server的官方檔案](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)