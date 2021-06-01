---
description: 說明提供互動式報表和資料更新排程的基礎軟體。
seo-description: 說明提供互動式報表和資料更新排程的基礎軟體。
seo-title: 報表技術
solution: Audience Manager
title: 報表技術
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: 重疊報表
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 3%

---

# 報表技術{#report-technology}

說明提供互動式報表和資料更新排程的基礎軟體。

<!-- 

c_report_technology.xml

 -->

## 互動式報表使用Tableau技術

[!DNL Audience Manager] 使 [](https://www.tableausoftware.com/) 用Table軟體在互動式報表中顯示資料。對於[!DNL Tableau],[!UICONTROL Delivery and Overlap]報表使用視覺提示和符號，可幫助您：

* 找出高效能和低效能特徵。
* 找出具有低和高不重複訪客重疊的特徵和區段。
* 使用重疊資料建立目標區段。
* 識別低重疊的相關特徵，以擴大觸及範圍。

## 資料更新排程

報告資料每週每週日更新。 更新會處理從星期六（前一天）到上個星期日的資料。

## 互動式報表{#shapes-colors-sizes}中使用的形狀、顏色和大小

大多數互動式報表都使用不同大小和顏色的形狀來顯示結果。 此顯示格式旨在幫助您直觀地理解資料，而不需要遍歷行和列數字。

<!-- 

r_legend.xml

 -->

### 報表圖例

下表定義動態報告中使用的形狀、大小和顏色。

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
     <li id="li_371331AE984A4A999CE0596EA13987E0">方塊表示第三方特徵。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>色彩</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">紅色陰影表示<i>low</i>重疊。 </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">綠色陰影表示<i>高</i>重疊。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>大小</b> </td> 
   <td colname="col2"> 大小以觸及的直接比例增加或減少（特徵或區段中的點按次數或百分比，或不重複使用者）。 </td> 
  </tr> 
 </tbody> 
</table>

## Tableau檔案{#tableau-documentation}

若要深入了解您可在互動式報表中看到的Tableau控制項，請參閱Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)上[Tableau伺服器的官方檔案
