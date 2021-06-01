---
description: 傳回特定特徵和整個區段之間共用之不重複使用者數量的資料。
seo-description: 傳回特定特徵和整個區段之間共用之不重複使用者數量的資料。
seo-title: 區段至特徵重疊報表
solution: Audience Manager
title: 區段至特徵重疊報表
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: 重疊報表
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 5%

---

# 區段至特徵重疊報表{#segment-to-trait-overlap-report}

傳回特定特徵和整個區段之間共用之不重複使用者數量的資料。

>[!NOTE]
>
>Audience Manager中的重疊報表遵循RBAC原則。 您只能根據您所屬的[RBAC使用者群組](/help/using/features/administration/administration-overview.md)，從您有權存取的資料來源查看區段和特徵。

<!-- 

c_segment_trait_overlap.xml

 -->

## 概述

[!UICONTROL Segment to Trait Overlap]報表作為最佳化工具，可協助您建立高度聚焦的區段或擴展區段觸及範圍。 例如，您可以建立重疊度高的重點區段和特徵，以觸及特定對象。 不過，大量重疊可能表示不重複使用者減少（觸及較少）。 執行此報表可移除具有大量區段重疊的特徵，並以重疊較少的特徵取代，以協助擴展觸及範圍。

### 範例報表

下圖提供[!UICONTROL Segment-to-Trait Overlap]報表的高階概觀。

![](assets/segment-to-trait-overlap.png)

### 深入研究個別資料點

選取個別點，以在快顯視窗中檢視資料詳細資訊。 您的點按動作會自動更新報表中顯示的資料。

## 比較區段與特徵{#comparing-segments-to-traits}

說明如何比較區段和特徵，從結果中衍生出有意義的資訊。

<!-- 

c_compare_s2t.xml

 -->

### 比較特徵和區段唯一值：範例

乍一看，比較區段與特徵並嘗試從結果中得出結論，可能有些不合邏輯。 畢竟，區段和特徵不同，因此從不同項目衍生的資料有何意義？ 但在此情況下，我們不會比較特徵和區段，而是會比較它們之間共用的不重複訪客數量。 共用的不重複訪客計數提供的通用值，可讓區段與特徵比較成為可能。

下圖說明特徵與其所屬區段之間的關係。 在此案例中，我們有一個特徵有10位訪客，而一個區段有1,000位訪客。 他們共用3個不重複訪客。

![](assets/s2t.png)

不重複訪客計數是這些不同物件類別之間共用的常數值。 因此，您可以依下列方式判斷兩者之間的不重複訪客關係：

* 特徵會與區段共用其不重複訪客的30%(3/10 = 0.30)。
* 區段會與特徵共用0.3%的不重複訪客(3/1,000 = 0.003)

### 找出區段中的值以比較特徵

查看特徵和區段之間的重疊，可協助您估計可用的訪客池總數（預測），或找出重疊過多的低效區段。

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
   <td colname="col2"> <p>若要判斷可用訪客池，請加總特徵總計（較少重疊）與區段總計（較少重疊）之間的差異。 </p> <p>此區段 — 特徵組合最多可吸引1004名新使用者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>找出效率低下的區段</b> </td> 
   <td colname="col2"> <p>如果特徵屬於區段定義中的<span class="wintitle"> AND</span>群組，則具有該特徵的不重複訪客已位於區段中，無法新增至區段。 您可以使用此報表來尋找低重疊的相關特徵，並將其新增至區段定義，以增加該區段對象庫的觸及率。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 了解區段對特徵重疊報表{#data-filters-s2t-report}中的資料篩選

說明特徵和區段不重複重疊%滑桿的運作方式。

<!-- 

r_s2t_sliders.xml

 -->

[!UICONTROL Segment-to-Trait overlap]報表可讓您使用兩個滑桿，依特徵或區段依重疊%篩選資料。

* **[!UICONTROL Filter Trait Uniques %:]** 依在特徵和區段之間共用的不重複訪客百分比篩選資料。
* **[!UICONTROL Filter Segment Uniques Overlap %:]** 依區段與特徵之間共用的不重複訪客%來篩選資料。

### 範例

下圖說明特徵唯一值%與區段唯一值%之間的差異。 在此情況下，特徵和區段會共用3個不重複訪客。 比例：

* 特徵會與區段共用其不重複訪客的30%(3/10 = 0.30)。
* 區段會與特徵共用0.3%的不重複訪客(3/1,000 = 0.003)

![](assets/s2t.png)

## 定義的區段對特徵資料快顯欄位{#fields-defined}

說明按一下個別資料點時，快顯視窗中顯示的量度。

<!-- 

r_s2t_data_pop.xml

 -->

[!UICONTROL Segment-to-Trait Overlap]報表的快顯功能表包含下列量度。 請注意，表格中的唯一值量度代表您的&#x200B;*即時使用者*。

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 區段ID</span></b> </td> 
   <td colname="col2"> 區段的唯一數值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵資料來源  </span></b> </td> 
   <td colname="col2"> 特徵擁有者的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 資料來源類型</span></b> </td> 
   <td colname="col2">定義特徵所屬的提供者類型。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方（您自己的特徵）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（來自外部資料合作夥伴/供應商）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵ID</span></b> </td> 
   <td colname="col2"> 特徵的唯一數值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵名稱</span></b> </td> 
   <td colname="col2"> 特徵名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵不重複值重疊%</span></b> </td> 
   <td colname="col2"> 特徵與區段共用的獨特訪客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 區段唯一客戶重疊%</span></b> </td> 
   <td colname="col2"> 區段與特徵共用的不重複訪客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊不重複值</span></b> </td> 
   <td colname="col2"> 區段與特徵之間共用的不重複訪客數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 區段不重複值</span></b> </td> 
   <td colname="col2"> 區段中的不重複訪客數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵不重複值</span></b> </td> 
   <td colname="col2"> 特徵中的不重複訪客數。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用資料滑桿篩選報表結果](../../reporting/dynamic-reports/data-sliders.md)
* [互動式報表中使用的形狀、顏色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
* [報表圖示和工具說明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
* [重疊報表：更新排程和最小區段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
* [所選 Audience Manager 報表中的資料取樣和錯誤率...](../../reporting/report-sampling.md)
* [重疊報表的 CSV 檔案](../../reporting/dynamic-reports/overlap-csv-files.md)

