---
description: 說明支援互動式報表與資料更新排程的基礎軟體。
seo-description: Describes the underlying software that powers the interactive reports and the data update schedule.
seo-title: Report Technology
solution: Audience Manager
title: 報表技術
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: Overlap Reports
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# 報表技術{#report-technology}

說明支援互動式報表與資料更新排程的基礎軟體。

<!-- 

c_report_technology.xml

 -->

## 互動式報表使用Tableau技術

[!DNL Audience Manager]使用[Tableau](https://www.tableausoftware.com/)軟體在互動式報表中顯示資料。 透過[!DNL Tableau]，[!UICONTROL Delivery and Overlap]報告會使用視覺提示和符號來幫助您：

* 尋找高效能和低效能的特徵。
* 找出不重複訪客重疊率低和高的特徵和區段。
* 使用重疊資料來建立目標區段。
* 透過識別低重疊的相關特徵來擴大觸及率。

## 資料更新排程

報告資料每週星期日都會更新。 更新會處理從星期六（前一天）回到前一個星期日的資料。

## 互動式報表中使用的形狀、顏色和大小 {#shapes-colors-sizes}

大部分的互動式報表會使用不同大小和顏色的形狀來顯示結果。 此顯示格式的設計目的，是協助您以視覺化方式瞭解資料，而不需費力瀏覽數字列和欄。

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
   <td colname="col1"> <b>圖形</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">圓圈表示您自己的第一方特徵。 </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">方塊表示第三方特徵。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>色彩</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">紅色陰影表示<i>低</i>重疊。 </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">綠色陰影表示<i>高</i>重疊。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>大小</b> </td> 
   <td colname="col2"> 大小會以直接比例增加或減少，以達到（特徵或區段中的點按次數或點按百分比或不重複使用者）。 </td> 
  </tr> 
 </tbody> 
</table>

## Tableau檔案 {#tableau-documentation}

若要深入瞭解您可在互動式報表中看到的Tableau控制項，請參閱[Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)上Tableau伺服器的官方檔案
