---
description: 「廣告單位重疊」報表會顯示為熱圖，顯示廣告件數之間的高和低overlap。
seo-description: 「廣告單位重疊」報表會顯示為熱圖，顯示廣告件數之間的高和低overlap。
seo-title: 廣告單元重疊
solution: Audience Manager
title: 廣告單元重疊
uuid: e4467e81-accf-474e-b501-89d57395651 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ad Unit Overlap{#ad-unit-overlap}

**[!UICONTROL Ad Unit Overlap]** 報表會顯示為熱圖，強調您的廣告件數之間的高和低overlap。

## 使用案例 {#use-cases}

**[!UICONTROL Ad Unit Overlap]** 透過此報表，您可以深入瞭解網路屬性中受眾的位置。報表會考量您的100個主要相關屬性，並顯示它們之間的重疊。

## Using the Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Base Ad Units]** and **[!UICONTROL Top N Overlapping Ad Units]** controls to select your desired number of ad units for the overlap. 您最多可以為每個項目選取100個項目。

Use the **Day Range** and **Date Through** controls to adjust your look-back range. 請注意，天和30天回顧期間僅適用於周日日期。

Use the **[!UICONTROL Base Ad Unit]** and the **[!UICONTROL Overlap Ad Unit]** controls to select which of your ad units you want to display in the overlap report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

[!UICONTROL Ad Unit Overlap] 您的報表看起來類似下方的報表。將滑鼠指標暫留在任何儲存格上，以取得更多關於特定重疊的資訊。如需範例報表下表格中其他資訊的詳細資訊，請參閱說明。

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊廣告單位</span> </p> </td> 
   <td colname="col2"> <p>庫存項目的名稱。例如，這可以是您的一個網站或網站上的文章。在上述影像中，基本廣告單位為文章-18。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 基本廣告單位</span> </p> </td> 
   <td colname="col2"> <p>庫存項目的名稱。例如，這可以是您的一個網站或網站上的文章。在上述影像中，基本廣告單位為文章-8。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊廣告單元獨特計數計數</span> </p> </td> 
   <td colname="col2"> <p>已造訪廣告單位項目-18的使用者人數。此資訊會從DFP記錄檔中擷取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 基本廣告單位獨特計數計數</span> </p> </td> 
   <td colname="col2"> <p>已造訪廣告單元項目-8的使用者人數。此資訊會從DFP記錄檔中擷取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊獨特計數計數</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊百分比</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Base Ad Unit</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
