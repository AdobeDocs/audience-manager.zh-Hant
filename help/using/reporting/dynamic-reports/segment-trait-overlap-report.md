---
description: 返回特定特性和整個段之間共用的唯一用戶數的資料。
seo-description: Returns data on the number of unique users shared between a particular trait and an entire segment.
seo-title: Segment-to-Trait Overlap Report
solution: Audience Manager
title: 區段至特徵重疊報表
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 5%

---

# 區段至特徵重疊報表{#segment-to-trait-overlap-report}

返回特定特性和整個段之間共用的唯一用戶數的資料。

>[!NOTE]
>
>Audience Manager中的Overlap報告遵循RBAC原則。 您只能從資料源中查看段和特徵，您可以根據 [RBAC用戶組](/help/using/features/administration/administration-overview.md) 屬於你。

<!-- 

c_segment_trait_overlap.xml

 -->

## 概述

作為優化工具， [!UICONTROL Segment to Trait Overlap] 報告可幫助您構建高度集中的細分市場或擴大細分市場。 例如，您可以建立重疊度高的聚焦段和特徵，以接觸特定的受眾。 但是，大量重疊可能意味著唯一用戶減少（訪問範圍減小）。 運行此報告有助於擴展覆蓋範圍，方法是刪除具有大量段重疊的特徵，並用重疊較少的特徵替換這些特徵。

### 示例報告

下圖提供了對 [!UICONTROL Segment-to-Trait Overlap] 報告。

![](assets/segment-to-trait-overlap.png)

### 細化單個資料點

選擇單個點以在彈出窗口中查看資料詳細資訊。 您的按一下操作會自動更新報告中顯示的資料。

## 將段與特徵進行比較 {#comparing-segments-to-traits}

描述如何比較段和特徵以從結果中獲取有意義的資訊。

<!-- 

c_compare_s2t.xml

 -->

### 比較特性和段統一性：一個例子

乍一看，將資料段與特徵進行比較並試圖從結果中得出結論似乎不合邏輯。 畢竟，資料段和特徵是不同的，那麼從不同項目中得出的資料又有什麼意義呢？ 但是，在本例中，我們不是比較特徵和片段，而是比較它們之間共用的獨特訪問者的數量。 共用的唯一訪問者計數提供了使段與特徵比較成為可能的公共值。

下圖說明了特徵與其所屬段之間的關係。 在這個例子中，我們有10個訪客和1000個訪問者。 他們共有3個獨特的訪問者。

![](assets/s2t.png)

唯一訪問者計數是這些不同對象類之間共用的常數值。 因此，您可以確定它們之間的唯一訪問者關係，如下所示：

* 30%的獨有訪客與此段(3/10 = 0.30)相同。
* 該部門擁有0.3%的獨有訪問者具有這一特點(3/1,000 = 0.003)

### 在段中查找值以比較特徵

查看特徵和段之間的重疊有助於您估計可用訪問者總庫（預測）或查找重疊過多的低效段。

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
   <td colname="col2"> <p>要確定可用訪問者池，請總和特徵總數（較少重疊）與段總數（較少重疊）之間的差。 </p> <p>這種片段特徵組合可以達到1004個新用戶。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>查找低效段</b> </td> 
   <td colname="col2"> <p>如果一個特質是 <span class="wintitle"> 和</span> 段定義中的「組」，具有該特性的唯一訪問者已在段中，且不可用於添加到段。 您可以使用此報告查找重疊度低的相關特徵，並將其添加到段定義中，從而增加該段受眾池的覆蓋範圍。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 瞭解段到特徵重疊報告中的資料篩選器 {#data-filters-s2t-report}

描述特性和段唯一重疊%滑塊的工作方式。

<!-- 

r_s2t_sliders.xml

 -->

的 [!UICONTROL Segment-to-Trait overlap] report允許您使用兩個滑塊按重疊%按特性或段過濾資料。

* **[!UICONTROL Filter Trait Uniques %:]** 按特性和段之間共用的唯一訪問者百分比篩選資料。
* **[!UICONTROL Filter Segment Uniques Overlap %:]** 按段和特徵之間唯一訪問者共用的百分比篩選資料。

### 範例

下圖說明了特徵單位%與段單位%之間的差異。 在這種情況下，特徵和片段共有3個獨特訪問者。 比例：

* 30%的獨有訪客與此段(3/10 = 0.30)相同。
* 該部門擁有0.3%的獨有訪問者具有這一特點(3/1,000 = 0.003)

![](assets/s2t.png)

## 定義段到特徵資料彈出欄位 {#fields-defined}

描述按一下單個資料點時彈出窗口中顯示的度量。

<!-- 

r_s2t_data_pop.xml

 -->

的彈出窗口 [!UICONTROL Segment-to-Trait Overlap] 報告包含以下度量。 請注意，表中的單位度量表示 *即時用戶*。

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 段ID</span></b> </td> 
   <td colname="col2"> 段的唯一數字ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特性資料源 </span></b> </td> 
   <td colname="col2"> 特徵所有者的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 資料源類型</span></b> </td> 
   <td colname="col2">定義特徵所屬的提供程式類型。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一次聚會（你的特質）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（來自外部資料合作夥伴/供應商）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特性ID</span></b> </td> 
   <td colname="col2"> 特性的唯一數字ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特性名稱</span></b> </td> 
   <td colname="col2"> 特徵的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特徵單位重疊%</span></b> </td> 
   <td colname="col2"> 與段具有特徵的獨特訪問者百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 段單位重疊%</span></b> </td> 
   <td colname="col2"> 具有特點的段中唯一訪問者的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊統一</span></b> </td> 
   <td colname="col2"> 段和特徵之間共用的唯一訪問者數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 段Uniques</span></b> </td> 
   <td colname="col2"> 段中的唯一訪問者數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特萊烏尼克斯</span></b> </td> 
   <td colname="col2"> 特徵中的獨特訪問者數。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用資料滑桿篩選報表結果](../../reporting/dynamic-reports/data-sliders.md)
>* [Interactive Reports中使用的形狀、顏色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [報告表徵圖和說明的工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重疊報表：更新排程和最小區段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [所選 Audience Manager 報表中的資料取樣和錯誤率...](../../reporting/report-sampling.md)
>* [重疊報表的 CSV 檔案](../../reporting/dynamic-reports/overlap-csv-files.md)

