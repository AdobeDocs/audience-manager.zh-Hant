---
description: 傳回特定特徵和整個區段之間共用的不重複使用者人數。
seo-description: Returns data on the number of unique users shared between a particular trait and an entire segment.
seo-title: Segment-to-Trait Overlap Report
solution: Audience Manager
title: 區段對特徵重疊報表
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%

---

# 區段對特徵重疊報表{#segment-to-trait-overlap-report}

傳回特定特徵和整個區段之間共用的不重複使用者人數。

>[!NOTE]
>
>Audience Manager中的重疊報表遵循RBAC原則。 您只能根據您所屬的[RBAC使用者群組](/help/using/features/administration/administration-overview.md)，從您有權存取的資料來源檢視區段和特徵。

<!-- 

c_segment_trait_overlap.xml

 -->

## 概述

作為最佳化工具，[!UICONTROL Segment to Trait Overlap]報表可協助您建立高度集中的區段或擴大區段觸及範圍。 例如，您可以建立高度重疊的重點區段和特徵，以觸及特定對象。 不過，大量重疊可能代表不重複使用者較少（觸及範圍較小）。 執行此報表可移除具有大量區段重疊的特徵，並以較少重疊的特徵取代，以協助擴大觸及範圍。

### 範例報告

下圖提供[!UICONTROL Segment-to-Trait Overlap]報表的整體概觀。

![](assets/segment-to-trait-overlap.png)

### 深入研究個別資料點

選取個別點，以在快顯視窗中檢視資料詳細資訊。 您的點按動作會自動更新報表中顯示的資料。

## 比較區段與特徵 {#comparing-segments-to-traits}

說明如何比較區段和特徵，以從結果中得出有意義的資訊。

<!-- 

c_compare_s2t.xml

 -->

### 比較特徵和區段唯一值：範例

乍一看，將區段與特徵進行比較並嘗試從結果中得出結論似乎不合邏輯。 畢竟，區段和特徵是不同的，所以從不同的專案衍生的資料如何會有意義？ 不過，在此案例中，我們並非比較特徵和區段，而是比較它們之間共用的不重複訪客數量。 共用的不重複訪客計數提供通用值，可讓區段與特徵比較。

下圖說明特徵與其所屬區段之間的關係。 在此案例中，我們有一個有10位訪客的特徵和一個有1,000位訪客的區段。 他們共用3個不重複訪客。

![](assets/s2t.png)

不重複訪客計數是這些不同物件類別之間共用的常數值。 因此，您可以依照下列方式判斷兩者之間的不重複訪客關係：

* 該特徵會與區段共用30%的不重複訪客(3/10 = 0.30)。
* 該區段與具有特徵的獨特訪客共用0.3% (3/1,000 = 0.003)

### 尋找區段中的值以進行特徵比較

檢視特徵和區段之間的重疊有助於您估計可用的訪客集區總數（預測），或找出重疊過多的低效區段。

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>預測</b> </td> 
   <td colname="col2"> <p>若要確定可用的訪客集區，請加總特徵總計（較少重疊）和區段總計（較少重疊）之間的差異。 </p> <p>此區段 — 特徵組合最多可達1004名新使用者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>尋找無效區段</b> </td> 
   <td colname="col2"> <p>如果特徵屬於區段定義中的<span class="wintitle"> AND</span>群組，則具有該特徵的不重複訪客已位於區段中，且無法新增至區段。 您可以使用此報表來尋找低重疊的相關特徵，並將其新增至區段定義，藉此擴大該區段受眾集區的觸及率。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 瞭解區段對特徵重疊報表中的資料篩選器 {#data-filters-s2t-report}

說明特徵和區段不重複重疊%滑桿如何運作。

<!-- 

r_s2t_sliders.xml

 -->

[!UICONTROL Segment-to-Trait overlap]報表可讓您使用兩個滑桿，依特徵或區段依重疊%篩選資料。

* **[!UICONTROL Filter Trait Uniques %:]**&#x200B;會依特徵和區段之間共用的不重複訪客的%來篩選資料。
* **[!UICONTROL Filter Segment Uniques Overlap %:]**&#x200B;會依%的獨特訪客在區段和特徵之間共用的比例來篩選資料。

### 範例

下圖說明特徵唯一值%與區段唯一值%之間的差異。 在這種情況下，特徵和區段會共用3個不重複訪客。 以比例顯示：

* 該特徵會與區段共用30%的不重複訪客(3/10 = 0.30)。
* 該區段與具有特徵的獨特訪客共用0.3% (3/1,000 = 0.003)

![](assets/s2t.png)

## 定義的區段對特徵資料Pop欄位 {#fields-defined}

說明當您按一下個別資料點時，快顯視窗中顯示的量度。

<!-- 

r_s2t_data_pop.xml

 -->

[!UICONTROL Segment-to-Trait Overlap]報表的快顯視窗包含下列量度。 請注意，表格中的不重複量度代表您的&#x200B;*即時使用者*。

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">區段識別碼</span></b> </td> 
   <td colname="col2"> 區段的不重複數值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">特徵資料Source </span></b> </td> 
   <td colname="col2"> 特徵擁有者的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">資料Source型別</span></b> </td> 
   <td colname="col2">定義特徵所屬的提供者型別。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方（您自己的特徵）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（來自外部資料合作夥伴/廠商）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">特徵ID</span></b> </td> 
   <td colname="col2"> 特徵的不重複數值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">特徵名稱</span></b> </td> 
   <td colname="col2"> 特徵名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">特徵不重複重疊%</span></b> </td> 
   <td colname="col2"> 特徵與此區段共用的不重複訪客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">區段不重複重疊%</span></b> </td> 
   <td colname="col2"> 某個區段共用某個特徵的不重複訪客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">個重疊不重複專案</span></b> </td> 
   <td colname="col2"> 區段和特徵之間共用的不重複訪客數量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">區段不重複</span></b> </td> 
   <td colname="col2"> 區段中的不重複訪客數量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">特徵不重複</span></b> </td> 
   <td colname="col2"> 特徵中的不重複訪客數量。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用資料滑桿篩選報表結果](../../reporting/dynamic-reports/data-sliders.md)
>* [互動式報表中使用的形狀、顏色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [報告圖示和工具說明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重疊報表：更新排程和最小區段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [所選Audience Manager報表中的資料取樣和錯誤率……](../../reporting/report-sampling.md)
>* [重疊報表的 CSV 檔案](../../reporting/dynamic-reports/overlap-csv-files.md)
