---
description: 「區段趨勢」報表會傳回一段時間內映射和未映射區段的印象和點進率資料。映射區段是您建立的區段，並傳送至目標以進行定位。未對應區段是您建立的區段，但未傳送至目標定位。比較您所選度量的趨勢和量，以便更好地瞭解受眾隨著時間變化的行為。
seo-description: 「區段趨勢」報表會傳回一段時間內映射和未映射區段的印象和點進率資料。映射區段是您建立的區段，並傳送至目標以進行定位。未對應區段是您建立的區段，但未傳送至目標定位。比較您所選度量的趨勢和量，以便更好地瞭解受眾隨著時間變化的行為。
seo-title: 區段趨勢報表
solution: Audience Manager
title: 區段趨勢報表
uuid: f84e8d0a-74e5-430c-b61 c-efb696 fee93
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Trend Report{#segment-trend-report}

「區段趨勢」報表會傳回一段時間內映射和未映射區段的印象和點進率資料。

映射區段是您建立的區段，並傳送至目標以進行定位。未對應區段是您建立的區段，但未傳送至目標定位。

比較您所選度量的趨勢和量，以便更好地瞭解受眾隨著時間變化的行為。

## 使用案例 {#use-cases}

Use the [!UICONTROL Segment Trend] report to validate a segment&#39;s performance over time and to pinpoint trends based on strong performance or scale.

透過此報表，您可以瞭解哪些Web屬性顯示下降或過期，以及視需要故障排除。This report is the next step after you identify your audience of interest in the [!UICONTROL Segment Performance] report, to ensure that the strong or poor performance you saw in the [!UICONTROL Segment Performance] tab is consistent over time.

## Using the Segment Trend Report {#using-the-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Adjust the look-back window with the **[!UICONTROL Date Through]** slider.

Click any of the segments under the **[!UICONTROL Date Through]** slider to bring up the option to keep only that segment in the report or exclude it.

Use the **[!UICONTROL Line Item]** drop-down box to select the properties in your portfolio for which you want to return information.

In the **[!UICONTROL Segment Data Source]** drop-down box, select the data sources containing the segments you want to see in the report.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item] IDs, as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item] ID.

## Interpreting the Results {#interpreting-results}

[!UICONTROL Segment Trend] 報表只會以14天間隔傳回折線圖中的資料。在此範例中，報表顯示一組映射和未映射區段的曝光次數和點進趨勢。

將滑鼠指標暫留在任何行上，以取得更多有關該特定區段趨勢的資訊。如需範例報表下表格中其他資訊的詳細資訊，請參閱說明。

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 區段</span> </p> </td> 
   <td colname="col2"> <p>您指派給此區段的英數名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 區段ID</span> </p> </td> 
   <td colname="col2"> <p>此區段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 行項目</span> </p> </td> 
   <td colname="col2"> <p>您看到此報表的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 點擊次數</span> </p> </td> 
   <td colname="col2"> <p>此特徵點擊您Web屬性中項目的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 曝光數</span> </p> </td> 
   <td colname="col2"> <p>此特性對您庫存的成員次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>點進率. 此度量會遵循點按後的曝光百分比。依曝光次數劃分點按次數以取得此量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 區段獨特訪客</span> </p> </td> 
   <td colname="col2"> <p>區段成員的數目，在最近30天內。 </p> </td> 
  </tr> 
 </tbody> 
</table>
