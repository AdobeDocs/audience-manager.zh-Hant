---
description: 「區段至廣告單位重疊」報表會顯示為熱圖，顯示廣告件數與Audience Manager區段之間的高和低overlap。
seo-description: 「區段至廣告單位重疊」報表會顯示為熱圖，顯示廣告件數與Audience Manager區段之間的高和低overlap。
seo-title: 區段至廣告單位重疊
solution: Audience Manager
title: 區段至廣告單位重疊
uuid: ta20163-58aa-42c9-8f72-a1 dfb0 d20 e57
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment to Ad Unit Overlap{#segment-to-ad-unit-overlap}

「區段至廣告單位重疊」報表會顯示為熱圖，顯示廣告件數與Audience Manager區段之間的高和低overlap。

## 使用案例 {#use-cases}

With the [!UICONTROL Segment to Ad Unit Overlap] report, you can understand which audiences visit your web properties. The report displays the overlap between members of your [!DNL Audience Manager] segments and the number of visitors to your web properties. 較高的重疊表示群體的許多成員瀏覽您的Web屬性。

## Using the Segment to Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Ad Units]** and **[!UICONTROL Top N Segments]** controls to select your desired number of ad units and segments for the overlap. 您最多可以為每個項目選取100個項目。

Use the **Day Range** and **Date Through** controls to adjust your look-back range. 請注意，天和30天回顧期間僅適用於周日日期。

Use the **[!UICONTROL Segment Name]** and the **[!UICONTROL Ad Unit]** boxes to filter any of segments and ad units.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

[!UICONTROL Segment to Ad Unit Overlap] 您的報表看起來類似下方的報表。將滑鼠指標暫留在任何儲存格上，以取得更多關於特定重疊的資訊。如需範例報表下表格中其他資訊的詳細資訊，請參閱說明。

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 廣告單位 </span> </p> </td> 
   <td colname="col2"> <p>庫存項目的名稱。例如，這可以是您的一個網站或網站上的文章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 區段即時獨特計數計數</span> </p> </td> 
   <td colname="col2"> <p>The number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 廣告單元獨特計數計數</span> </p> </td> 
   <td colname="col2"> <p>此特定廣告單位的訪客人數。此資訊會從DFP記錄檔中擷取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊獨特計數計數</span> </p> </td> 
   <td colname="col2"> <p>對廣告單元項目公開的區段成員。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊百分比</span> </p> </td> 
   <td colname="col2"> <p>廣告單位與區段人口族群之間的重疊。This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Segment Real Time Uniques</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

