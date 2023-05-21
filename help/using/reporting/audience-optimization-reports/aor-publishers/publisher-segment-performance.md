---
description: 「段效能」報告按印象和即時段單位比較映射和未映射的段。 映射段是您建立的段，併發送到目標進行目標。 未映射段是您建立但尚未發送到目標的段。 比較報表內和報表間的這些不同段類型有助於優化現有市場活動，並查找您可能希望發送到目標的被忽略的段。
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and Real-Time Segment Uniques. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: 發佈伺服器的段效能報告
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization Reports
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 2%

---

# 區段成效報表{#segment-performance-report}

「段效能」報告按印象和即時段單位比較映射和未映射的段。

映射段是您建立的段，併發送到目標進行目標。 未映射段是您建立但尚未發送到目標的段。

比較報表內和報表間的這些不同段類型有助於優化現有市場活動，並查找您可能希望發送到目標的被忽略的段。

## 使用個案 {#use-cases}

使用 [!UICONTROL Segment Performance] 報告：

* 識別驅動規模或效能的映射受眾段。
* 根據受眾對過去業績的貢獻確定未映射的市場細分，以在將來的市場活動中引入。

## 使用段績效報告 {#using-segment-performance-report}

在 **[!UICONTROL Mapped]** 和 **[!UICONTROL Unmapped]** 選擇映射到目標的段。 選擇 **[!UICONTROL All]** 以在報告中包含所有段。

使用 **日期範圍** 和 **日期至** 控制項來調整回顧範圍。 請注意，7天和30天回溯期間僅適用於星期日。

使用 **[!UICONTROL Line Item]** 下拉框，選擇要返回其資訊的Web屬性。

在 **[!UICONTROL Segment Data Source]** 下拉框中，選擇包含要在報告中查看的段的資料源。

使用 **[!UICONTROL Segment]** 下拉框，以選擇要在報告中查看的段。

>[!IMPORTANT]
>
>啟用時 [!UICONTROL Audience Optimization for Publishers]，必須包括描述性元資料 [!UICONTROL Line Item IDs]，如第3步中所述 [將GoogleAd Manager（以前叫DFP）資料檔案導入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 通過執行此操作，您可以確保報告將Web屬性的詳細資訊 [!UICONTROL Line Item] 而不是 [!UICONTROL Line Item ID]。

## 解釋結果 {#interpreting-results}

您 [!UICONTROL Segment Performance] 報告可能與下面的報告相似。 在報告中，按一下一個氣泡來查看基礎資料。 有關示例報告下表中的附加資訊，請參閱說明。

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
   <td colname="col2"> <p>分配給此段的字母數字名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>段ID </p> </td> 
   <td colname="col2"> <p>此段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行項目 </p> </td> 
   <td colname="col2"> <p>您正在查看此報告的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>點擊次數 </p> </td> 
   <td colname="col2"> <p>此特性的成員按一下Web屬性中項的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>曝光數 </p> </td> 
   <td colname="col2"> <p>此特性的成員接觸您的清單的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>點進率. </p> <p>此度量傳遞了點擊後印象的百分比。 按印數劃分點擊量以獲取此度量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>即時段填充 </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時看到的、當看到時符合該段條件的唯一訪問者的實際數量 <span class="keyword"> Audience Manager</span>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何讀取映射的段結果 {#read-mapped-segment}

在報表中映射的段的位置可以告訴您許多關於哪些段表現良好以及可能需要進行某些調整的資訊。

要閱讀報告，將結果分成四個部分，虛線（以紅色表示）和下面示例報告中顯示的類別。 示例中的標籤可以幫助您瞭解段效能以及如何響應這些結果。

![](assets/publisher_segment_performance_mapped.png)

## 如何讀取未映射的段結果 {#read-unmapped-segment}

查看中未映射的段 [!UICONTROL Segment Performance] 報告是查找未考慮目標的新段的極好方法。 事實上，其中某些段可能比映射的段要好。

要閱讀此報告，將結果分為四個部分，虛線（以紅色表示）和類別顯示在下面的示例報告中。

![](assets/publisher_segment_performance_unmapped.png)
