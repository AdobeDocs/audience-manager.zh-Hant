---
description: 返回有關在所有第一個和第三方特徵之間共用的唯一用戶數的資料。
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

返回有關在所有第一個和第三方特徵之間共用的唯一用戶數的資料。

>[!NOTE]
>
>Audience Manager中的Overlap報告遵循RBAC原則。 您只能從您有權訪問的資料源中根據 [RBAC用戶組](/help/using/features/administration/administration-overview.md) 屬於你。

<!-- 

c_overlap_reports.xml

 -->

## 概述

的 [!UICONTROL Trait-to-Trait Overlap] report返回所有您自己的特徵和第三方特徵之間共用的唯一用戶百分比的資料。 作為優化工具，此報告可幫助您：

* 根據您的需要建立重疊程度高或低的段。 具有高度重疊的特性可為您提供目標受眾，但獨特訪問者較少。 具有低重疊的特徵可用於訪問更大、唯一的訪問者集。
* 驗證第三方特性資料：相似的第一和第三方特徵之間的強烈重疊表明，資料夥伴的特徵是準確和可信的。 相反，低的重疊可以表明第三方特徵實際上可能並不包含與你自己相似的第一方特徵相同的資訊。
* 查找特徵之間意外的重疊，並使用該資訊構建創新片段。

## 示例報告

下圖提供了中元素的高級概述 [!UICONTROL Trait-to-Trait Overlap] 報告。

>[!NOTE]
>
>的 [!UICONTROL Trait-to-Trait Overlap] report將同一特性與自身進行比較時返回一個空欄位。

>[!NOTE]
>
>在特性與特性重疊報告中，資料夾特性不可用於比較。 通過利用特定資料夾特性建立段，可通過 [段到特徵重疊報告](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md)。

![](assets/trait-to-trait-overlap.png)

## 細化單個資料點

選擇單個點以在彈出窗口中查看資料詳細資訊。 您的按一下操作會自動更新報告中顯示的資料。

## 特性對特性重疊資料pop欄位定義 {#field-definitions}

描述按一下單個資料點時彈出窗口中顯示的度量。

<!-- 

r_t2t_data_pop.xml

 -->

的彈出窗口 [!UICONTROL Trait-to-Trait Overlap] 報告包含以下度量。 請注意，表中的單位度量表示 *即時用戶*。

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
   <td colname="col2"> 顯示比較性狀之間唯一重疊的百分比（重疊單位/特徵單位）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 資料源類型</span></b> </td> 
   <td colname="col2">定義特性所屬的資料源類型。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一次聚會（你的特質）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（來自外部資料合作夥伴/供應商）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊特徵ID</span></b> </td> 
   <td colname="col2"> 重疊特性的唯一數字ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊特徵名稱</span></b> </td> 
   <td colname="col2"> 重疊特徵的名稱。 </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 特性ID 2</span></b> </td> 
   <td colname="col2"> 基本資料源中特性的唯一數字ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 特性名稱2</span></b> </td> 
   <td colname="col2"> 基本資料源中特性的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊統一</span></b> </td> 
   <td colname="col2"> <p>要獲取重疊%,Audience Manager使用以下公式：</p> <p>重疊Uniques /（基本特徵Uniques +重疊特徵Uniques — 重疊特徵Uniques）</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> 重疊特徵Uniques</span></b> </td> 
   <td colname="col2"> 重疊特徵中唯一訪問者的數量。 </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> 基本特徵Uniques</span></b> </td> 
   <td colname="col2"> 基本特性中的唯一訪問者數。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用資料滑桿篩選報表結果](../../reporting/dynamic-reports/data-sliders.md)
>* [動態報告中使用的形狀、顏色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [報告表徵圖和說明的工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重疊報表：更新排程和最小區段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [所選 Audience Manager 報表中的資料取樣和錯誤率...](../../reporting/report-sampling.md)
>* [重疊報表的 CSV 檔案](../../reporting/dynamic-reports/overlap-csv-files.md)

