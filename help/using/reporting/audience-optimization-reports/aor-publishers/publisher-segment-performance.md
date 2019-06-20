---
description: 「區段績效」報表會依印象和即時區段唯一客戶數比較映射和未映射的區段。映射區段是您建立的區段，並傳送至目標以進行定位。未對應區段是您建立的區段，但未傳送至目標定位。在報表內和之間比較這些不同的區段類型，可協助您最佳化現有促銷活動，尋找您可能想要傳送至目標目標的群體。
seo-description: 「區段績效」報表會依印象和即時區段唯一客戶數比較映射和未映射的區段。映射區段是您建立的區段，並傳送至目標以進行定位。未對應區段是您建立的區段，但未傳送至目標定位。在報表內和之間比較這些不同的區段類型，可協助您最佳化現有促銷活動，尋找您可能想要傳送至目標目標的群體。
seo-title: 區段績效報表
solution: Audience Manager
title: 區段績效報表
uuid: c9a1e9ad-4f3f-4334-a3 ff-3f2301 c7303 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Performance Report{#segment-performance-report}

「區段績效」報表會依印象和即時區段唯一客戶數比較映射和未映射的區段。

映射區段是您建立的區段，並傳送至目標以進行定位。未對應區段是您建立的區段，但未傳送至目標定位。

在報表內和之間比較這些不同的區段類型，可協助您最佳化現有促銷活動，尋找您可能想要傳送至目標目標的群體。

## 使用個案 {#use-cases}

With the [!UICONTROL Segment Performance] report, you can:

* 識別驅動規模或效能的對應對象區段。
* 根據受眾對過去效能的貢獻，識別未對應區段以便在未來促銷活動中引入。

## Using the Segment Performance Report {#using-segment-performance-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. 請注意，天和30天回顧期間僅適用於周日日期。

Use the **[!UICONTROL Line Item]** drop-down box to select the web properties for which you want to return information.

In the **[!UICONTROL Segment Data Source]** drop-down box, select the data sources containing the segments you want to see in the report.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item ID].

## Interpreting the Results {#interpreting-results}

[!UICONTROL Segment Performance] 您的報表看起來類似下方的報表。在報表中，按一下泡泡以檢視基礎資料。如需範例報表下表格中其他資訊的詳細資訊，請參閱說明。

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>區段 </p> </td> 
   <td colname="col2"> <p>您指派給此區段的英數名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>區段ID </p> </td> 
   <td colname="col2"> <p>此區段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行項目 </p> </td> 
   <td colname="col2"> <p>您看到此報表的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>點擊次數 </p> </td> 
   <td colname="col2"> <p>此特徵點擊您Web屬性中項目的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>曝光數 </p> </td> 
   <td colname="col2"> <p>此特性對您庫存的成員次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>點進率. </p> <p>此度量會遵循點按後的曝光百分比。依曝光次數劃分點按次數以取得此量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>即時區段人口 </p> </td> 
   <td colname="col2"> <p>The actual number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## How to Read Your Mapped Segment Results {#read-mapped-segment}

您的對應區段在報表中的位置可告訴您哪些區段表現良好，以及您可能需要做些調整。

若要讀取報表，可以將結果分為四個區段，並使用虛線(紅色)和下方範例報表中顯示的類別來劃分結果。範例中的標籤可幫助您瞭解區段效能，以及如何回應這些結果。

![](assets/publisher_segment_performance_mapped.png)

## How to Read Your Unmapped Segment Results {#read-unmapped-segment}

Looking at unmapped segments in a [!UICONTROL Segment Performance] report is a great way to find new segments you haven&#39;t considered for targeting. 事實上，部分區段可能優於您對應的區段。

若要閱讀此報告，可將結果分為四個區段(紅色)和以下範例報表中顯示的類別。

![](assets/publisher_segment_performance_unmapped.png)
