---
description: 傳回在您所有第一方和第三方特徵之間共用之不重複使用者數量的資料。
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: 特徵至特徵重疊報表
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
source-git-commit: 6cc1351c3a84d4d2219f33ef6175f182b9641377
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 7%

---

# 特徵至特徵重疊報表{#trait-to-trait-overlap-report}

傳回在您所有第一方和第三方特徵之間共用之不重複使用者數量的資料。

>[!NOTE]
>
>Audience Manager中的重疊報表遵循RBAC原則。 您只能根據 [RBAC用戶組](/help/using/features/administration/administration-overview.md) 屬於你。

<!-- 

c_overlap_reports.xml

 -->

## 概述

此 [!UICONTROL Trait-to-Trait Overlap] 報表會傳回所有您自己的特徵和您第三方特徵之間共用的不重複使用者百分比資料。 此報表是最佳化工具，可協助您：

* 根據您的需求，建立高或低重疊的區段。 具有高重疊的特徵可提供目標對象，但不重複訪客較少。 重疊程度低的特徵有助於觸及較大的不重複訪客集。
* 驗證第三方特徵資料：類似的第一方和第三方特徵之間有強烈重疊，說明您資料合作夥伴的特徵正確且值得信賴。 相反地，低重疊可能表示第三方特徵實際上可能並不包含與您自己類似的第一方特徵相同的資訊。
* 找出特徵之間未預期的重疊，並使用該資訊建立創新區段。

## 範例報表

下圖提供 [!UICONTROL Trait-to-Trait Overlap] 報表。

>[!NOTE]
>
>此 [!UICONTROL Trait-to-Trait Overlap] 報表會在比較相同特徵本身時傳回空白欄位。

>[!NOTE]
>
>特徵對特徵重疊報表中無法比較資料夾特徵。 透過使用特定資料夾特徵建立區段，您可以透過 [區段對特徵重疊報表](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md).

![](assets/trait-to-trait-overlap.png)

## 深入研究個別資料點

選取個別點，以在快顯視窗中檢視資料詳細資訊。 您的點按動作會自動更新報表中顯示的資料。

## 定義的特徵對特徵重疊資料快顯欄位 {#field-definitions}

說明按一下個別資料點時，快顯視窗中顯示的量度。

<!-- 

r_t2t_data_pop.xml

 -->

的快顯視窗 [!UICONTROL Trait-to-Trait Overlap] 報表包含下列量度。 請注意，表格中的獨特值量度代表您的 *即時使用者*.

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
   <td colname="col2"> 顯示比較特徵（重疊唯一值/特徵唯一值）之間不重複重疊的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 資料來源類型</span></b> </td> 
   <td colname="col2">定義特徵所屬的資料來源類型。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方（您自己的特徵）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（來自外部資料合作夥伴/供應商）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊的特徵ID</span></b> </td> 
   <td colname="col2"> 重疊特徵的唯一數值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊的特徵名稱</span></b> </td> 
   <td colname="col2"> 重疊特徵的名稱。 </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵ID 2</span></b> </td> 
   <td colname="col2"> 基本資料來源中特徵的唯一數值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵名稱2</span></b> </td> 
   <td colname="col2"> 基本資料來源中的特徵名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊不重複值</span></b> </td> 
   <td colname="col2"> <p>若要取得重疊%,Audience Manager使用下列公式：</p> <p>重疊唯一值/（基本特徵唯一值+重疊特徵唯一值 — 重疊唯一值）</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊的特徵唯一值</span></b> </td> 
   <td colname="col2"> 來自重疊特徵的不重複訪客數。 </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 基本特徵不重複值</span></b> </td> 
   <td colname="col2"> 來自基本特徵的不重複訪客數。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用資料滑桿篩選報表結果](../../reporting/dynamic-reports/data-sliders.md)
>* [動態報表中使用的形狀、顏色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [報表圖示和工具說明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重疊報表：更新排程和最小區段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [所選 Audience Manager 報表中的資料取樣和錯誤率...](../../reporting/report-sampling.md)
>* [重疊報表的 CSV 檔案](../../reporting/dynamic-reports/overlap-csv-files.md)

