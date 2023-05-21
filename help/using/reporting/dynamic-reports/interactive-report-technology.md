---
description: 描述為互動式報告和資料更新計畫提供電源的基礎軟體。
seo-description: Describes the underlying software that powers the interactive reports and the data update schedule.
seo-title: Report Technology
solution: Audience Manager
title: 報表技術
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: Overlap Reports
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 3%

---

# 報表技術{#report-technology}

描述為互動式報告和資料更新計畫提供電源的基礎軟體。

<!-- 

c_report_technology.xml

 -->

## 互動式報告使用Tableau技術

[!DNL Audience Manager] 使用 [塔布洛](https://www.tableausoftware.com/) 顯示互動式報表中資料的軟體。 與 [!DNL Tableau]，也請參見Wiki頁。 [!UICONTROL Delivery and Overlap] 報告使用視覺提示和符號來幫助您：

* 查找高效能和低效能特性。
* 具有低和高唯一訪問者的斑點特徵和片段重疊。
* 使用重疊資料構建目標段。
* 通過識別低重疊的相關性狀來擴大接觸範圍。

## 資料更新計畫

每週日更新報告資料。 更新將處理從星期六（前一天）到上一個星期日的資料。

## Interactive Reports中使用的形狀、顏色和大小 {#shapes-colors-sizes}

大多數互動式報告使用不同大小和顏色的形狀顯示結果。 此顯示格式旨在幫助您直觀地理解資料，而無需涉及數字的行和列。

<!-- 

r_legend.xml

 -->

### 報告圖例

下表定義了動態報告中使用的形狀、大小和顏色。

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
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">圓圈表明你自己的第一黨特徵。 </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">方塊表示第三方特徵。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>色彩</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">紅色陰影表示 <i>低</i> 重疊。 </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">綠色表示 <i>高</i> 重疊。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>大小</b> </td> 
   <td colname="col2"> 大小以達到的直接比例增加或減少（特徵或段中的點擊次數或百分比或唯一用戶）。 </td> 
  </tr> 
 </tbody> 
</table>

## Tableau文檔 {#tableau-documentation}

要瞭解有關在互動式報告中可看到的Tableau控制項的詳細資訊，請參閱官方文檔， [Linux 2018.2上的Tableau伺服器](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)
