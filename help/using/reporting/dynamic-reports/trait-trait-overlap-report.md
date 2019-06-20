---
description: 傳回所有第一方和第三方特徵中共用的獨特使用者數量資料。
seo-description: 傳回所有第一方和第三方特徵中共用的獨特使用者數量資料。
seo-title: 特徵至特徵重疊報表
solution: Audience Manager
title: 特徵至特徵重疊報表
uuid: 7fb3fc9e-0e0b-492a-9a-9c3a-04356afb19c
translation-type: tm+mt
source-git-commit: 4dc8aad623198cbc24c5c76ac3818d7ee00e9a5e

---


# 特徵至特徵重疊報表{#trait-to-trait-overlap-report}

傳回所有第一方和第三方特徵中共用的獨特使用者數量資料。

>[!NOTE]
>
>Audience Manager中的「重疊」報表遵守CREAC原則。You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_overlap_reports.xml

 -->

## 概述

[!UICONTROL Trait-to-Trait Overlap] 報表會傳回在所有自己特性和第三方特徵之間共用的獨特使用者百分比資料。作為最佳化工具，此報告可協助您：

* 根據您的需求，建立高或低重疊的區段。高重疊特徵的特徵會為您指定目標對象，但不會讓獨特訪客看到。低重疊特徵可用來覆蓋較大、獨特訪客集。
* 驗證第三方特徵資料：類似第一方和第三方特徵之間的高度重疊表示資料合作夥伴的特徵是正確且值得信賴的。相反地，低重疊可能表示第三方特徵實際上可能包含與您自己類似的資訊。
* 尋找特徵之間未預期的重疊，並使用這些資訊建立創新的細分。

## 範例報表

The following illustration provides a high-level overview of elements in the [!UICONTROL Trait-to-Trait Overlap] report.

>[!NOTE]
>
>[!UICONTROL Trait-to-Trait Overlap] 當報表比較相同特徵時，報表會傳回空白欄位。

![](assets/trait-to-trait-overlap.png)

## 深入分析個別資料點

選取個別點，在彈出視窗中檢視資料詳細資料。您的點按動作會自動更新報表中顯示的資料。

## Trait-to-Trait Overlap Data Pop Fields Defined {#field-definitions}

說明當您按一下個別資料點時，彈出式視窗中顯示的度量。

<!-- 

r_t2t_data_pop.xml

 -->

[!UICONTROL Trait-to-Trait Overlap] 報表的快顯視窗包含下列度量。Note that the uniques metric in the table represents your *real-time users*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 資料提供者名稱</span></b> </td> 
   <td colname="col2"> 特徵擁有者的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 資料供應商類型</span></b> </td> 
   <td colname="col2">定義屬於特徵的提供者類型。可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方(您自己的特徵)。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方(來自外部資料合作夥伴/供應商)。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵ID</span></b> </td> 
   <td colname="col2"> 該特徵的唯一數值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵名稱</span></b> </td> 
   <td colname="col2"> 特徵的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊%</span></b> </td> 
   <td colname="col2"> 顯示比較特徵之間的獨特重疊百分比(重疊獨特訪客/特徵獨特項目)。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊獨特訪客</span></b> </td> 
   <td colname="col2"> <p>若要取得重疊的%，Audience Manager會使用下列公式：</p> <p>重疊唯一客戶數/(基本區段獨特值+重疊區段獨特值-重疊獨特客戶數)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵獨特</span></b> </td> 
   <td colname="col2"> 特徵中的獨特訪客數。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_贊_ this]
>
>* [使用資料滑桿篩選報表結果](../../reporting/dynamic-reports/data-sliders.md)
>* [動態報表中使用的形狀、顏色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [報表圖示和工具說明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重疊報表：更新排程和最小區段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [選取Audience Manager報表中的資料取樣和錯誤率…](../../reporting/report-sampling.md)
>* [重疊報表的CSV檔案](../../reporting/dynamic-reports/overlap-csv-files.md)