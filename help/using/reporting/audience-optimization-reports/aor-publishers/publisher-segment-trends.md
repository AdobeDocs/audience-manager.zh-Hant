---
description: 「段趨勢」報告返回一段時間內映射和未映射段的印入和點擊率資料。 映射段是您建立的段，併發送到目標進行目標。 未映射段是您建立但尚未發送到目標的段。 比較所選指標的趨勢和數量，以更好地瞭解觀眾隨時間的變化。
seo-description: The Segment Trend report returns data on impressions and click-through rates of mapped and unmapped segments over time. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Compare trends and volume for your selected metrics to get a better picture of how your audiences behave over time.
seo-title: Segment Trend Report
solution: Audience Manager
title: 區段區段報表
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 2%

---

# 區段區段報表{#segment-trend-report}

「段趨勢」報告返回一段時間內映射和未映射段的印入和點擊率資料。

映射段是您建立的段，併發送到目標進行目標。 未映射段是您建立但尚未發送到目標的段。

比較所選指標的趨勢和數量，以更好地瞭解觀眾隨時間的變化。

## 使用案例 {#use-cases}

使用 [!UICONTROL Segment Trend] 報告以驗證段的效能隨時間推移而變化，並根據強勁的效能或規模來查明趨勢。

通過此報告，您可以瞭解哪些Web屬性顯示了缺陷或缺陷增加，並根據需要進行故障排除。 此報告是您確定您對 [!UICONTROL Segment Performance] 報告，確保你在報告中看到 [!UICONTROL Segment Performance] 頁籤隨時間而一致。

## 使用段趨勢報表 {#using-the-report}

在 **[!UICONTROL Mapped]** 和 **[!UICONTROL Unmapped]** 選擇映射到目標的段。 選擇 **[!UICONTROL All]** 以在報告中包含所有段。

使用 **[!UICONTROL Date Through]** 按鈕。

按一下 **[!UICONTROL Date Through]** 滑塊，用於開啟選項以僅將該段保留在報告中或將其排除。

使用 **[!UICONTROL Line Item]** 下拉框，選擇要返回資訊的產品組合中的屬性。

在 **[!UICONTROL Segment Data Source]** 下拉框中，選擇包含要在報告中查看的段的資料源。

使用 **[!UICONTROL Segment]** 下拉框，以選擇要在報告中查看的段。

>[!IMPORTANT]
>
>啟用時 [!UICONTROL Audience Optimization for Publishers]，必須包括描述性元資料 [!UICONTROL Line Item] ID，如第3步中所述 [將GoogleAd Manager（以前叫DFP）資料檔案導入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 通過執行此操作，您可以確保報告將Web屬性的詳細資訊 [!UICONTROL Line Item] 而不是 [!UICONTROL Line Item] ID。

## 解釋結果 {#interpreting-results}

的 [!UICONTROL Segment Trend] 報表僅在14天間隔內返回線形圖中的資料。 在此示例中，報告顯示一組映射和未映射段的印象和點擊趨勢。

將滑鼠懸停在任何行上，以獲取有關該特定段趨勢的詳細資訊。 有關示例報告下表中的附加資訊，請參閱說明。

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
   <td colname="col2"> <p>分配給此段的字母數字名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 段ID</span> </p> </td> 
   <td colname="col2"> <p>此段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 行項目</span> </p> </td> 
   <td colname="col2"> <p>您正在查看此報告的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 點擊次數</span> </p> </td> 
   <td colname="col2"> <p>此特性的成員按一下Web屬性中項的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 曝光數</span> </p> </td> 
   <td colname="col2"> <p>此特性的成員接觸您的清單的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>點進率. 此度量傳遞了點擊後印象的百分比。 將點擊量除以印象以獲得此度量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 段Uniques</span> </p> </td> 
   <td colname="col2"> <p>過去30天內的段成員數。 </p> </td> 
  </tr> 
 </tbody> 
</table>
