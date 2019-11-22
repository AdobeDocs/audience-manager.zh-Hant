---
description: 傳回您所有第一方和第三方特徵之間共用的獨特使用者人數資料。
seo-description: 傳回您所有第一方和第三方特徵之間共用的獨特使用者人數資料。
seo-title: 特徵至特徵重疊報表
solution: Audience Manager
title: 特徵至特徵重疊報表
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
translation-type: tm+mt
source-git-commit: c05541df2d0dfc8753b06eaa8f2baee9bc6c2a16

---


# 特徵至特徵重疊報表{#trait-to-trait-overlap-report}

傳回您所有第一方和第三方特徵之間共用的獨特使用者人數資料。

>[!NOTE]
>
>Audience manager中的「重疊」報表符合RBAC原則。 您只能根據您所屬的 [RBAC使用者群組，從您有權存取的資料來源看到特徵](/help/using/features/administration/administration-overview.md) 。

<!-- 

c_overlap_reports.xml

 -->

## 概述

報 [!UICONTROL Trait-to-Trait Overlap] 表會傳回所有您自己特徵和第三方特徵之間共用的獨特使用者百分比資料。 作為最佳化工具，此報告可協助您：

* 根據您的需求，建立高重疊或低重疊的區段。 具有高度重疊的特性可讓您鎖定目標受眾，但獨特訪客較少。 重疊率低的特徵有助於觸及更大的獨特訪客集。
* 驗證第三方特徵資料：相似的第一方和第三方特徵之間的強烈重疊表明，您資料合作夥伴的特徵是正確且值得信賴的。 相反地，低重疊可能表示第三方特徵實際上可能不包含與您自己的類似第一方特徵相同的資訊。
* 尋找特徵之間意外的重疊，並使用該資訊建立創新細分。

## 範例報表

下圖提供報表元素的高階概 [!UICONTROL Trait-to-Trait Overlap] 觀。

>[!NOTE]
>
>當報 [!UICONTROL Trait-to-Trait Overlap] 表比較相同的特徵與自身時，會傳回空白欄位。

![](assets/trait-to-trait-overlap.png)

## 深入探究個別資料點

選取個別點，以在快顯視窗中檢視資料詳細資訊。 您的點按動作會自動更新顯示在報表中的資料。

## 特徵對特徵重疊資料快顯欄位已定義 {#field-definitions}

說明當您按一下個別資料點時，在快顯視窗中顯示的量度。

<!-- 

r_t2t_data_pop.xml

 -->

報表的快顯功 [!UICONTROL Trait-to-Trait Overlap] 能包含下列量度。 請注意，表格中的獨特度量代表 *您的即時使用者*。

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊%</span></b> </td> 
   <td colname="col2"> 顯示比較特徵（重疊唯一值／特徵唯一值）之間獨特重疊的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 資料來源類型</span></b> </td> 
   <td colname="col2">定義特徵所屬的資料來源類型。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方（您自己的特徵）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（來自外部資料合作夥伴／供應商）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊特徵ID</span></b> </td> 
   <td colname="col2"> 重疊特徵的唯一數值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊特徵名稱</span></b> </td> 
   <td colname="col2"> 重疊特徵的名稱。 </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵ID 2</span></b> </td> 
   <td colname="col2"> 基本資料來源中特徵的唯一數值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵名稱2</span></b> </td> 
   <td colname="col2"> 基本資料來源中特徵的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊獨特值</span></b> </td> 
   <td colname="col2"> <p>若要取得重疊百分比，Audience manager使用下列公式：</p> <p>重疊獨特值/（基本特徵獨特值+重疊特徵獨特值——重疊獨特值）</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊特徵唯一值</span></b> </td> 
   <td colname="col2"> 重疊特徵的獨特訪客數。 </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 基本特徵唯一值</span></b> </td> 
   <td colname="col2"> 來自基本特徵的獨特訪客數。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用資料滑桿篩選報表結果](../../reporting/dynamic-reports/data-sliders.md)
>* [動態報表中使用的形狀、顏色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [說明的報表圖示和工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重疊報表：更新排程和最小區段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [選取的Audience manager報表中的資料取樣和錯誤率……](../../reporting/report-sampling.md)
>* [重疊報表的CSV檔案](../../reporting/dynamic-reports/overlap-csv-files.md)