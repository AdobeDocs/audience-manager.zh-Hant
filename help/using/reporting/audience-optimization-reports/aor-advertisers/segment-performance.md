---
description: 「段效能」報表按印象和轉換率比較映射和未映射的段。 映射段是您建立的段，併發送到目標進行目標。 未映射段是您建立但尚未發送到目標的段。 比較報表內和報表間的這些不同段類型有助於優化現有市場活動，並查找您可能希望發送到目標的被忽略的段。
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and conversion rates. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: 區段成效報表
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization Reports
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 1%

---

# 區段成效報表{#segment-performance-report}

的 [!UICONTROL Segment Performance] 報告按印記和轉換率比較映射和未映射段。 映射段是您建立的段，併發送到目標進行目標。 未映射段是您建立但尚未發送到目標的段。 比較報表內和報表間的這些不同段類型有助於優化現有市場活動，並查找您可能希望發送到目標的被忽略的段。

## 如何讀取映射的段結果 {#read-mapped-segment-results}

已映射 [!UICONTROL Segment Performance] 報表顯示您建立併發送到目標的所有段。報表中映射段的位置可以告訴您哪些段表現良好，以及您可能需要在哪些位置進行一些調整。

要閱讀報告，它有助於將結果分成4個部分，其中虛線（以紅色表示）和下面示例報告中顯示的類別。

![](assets/mapped-segment-performance.png)

示例和下表中的標籤可幫助您瞭解段效能以及如何響應這些結果。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 放置指示 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上</b> </p> </td> 
   <td colname="col2"> <p>轉換率良好。 </p> <p>通過增加印象，您可能能夠得到更多的轉換。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下</b> </p> </td> 
   <td colname="col2"> <p>轉換率低。 </p> <p>您可能希望避免將目標鎖定在這些段上。 本節中的段非常適合與未映射的段結果中的段進行比較。 某些未映射的段可能比您已瞄準的段效能更好。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上</b> </p> </td> 
   <td colname="col2"> <p>效能強勁。 別管這些片段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下</b> </p> </td> 
   <td colname="col2"> <p>轉化率低，印象高。 </p> <p>本節中的段效能不佳。 您可能希望將預算從這些段轉移到報告左上像限的段中。 這將有助於減少印象，並有助於提高右下角部分段的轉換率。 另外，將這些映射的段與未映射的段進行比較。 某些未映射的段可能比您已瞄準的段效能更好。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 如何讀取未映射的段結果 {#read-unmapped-segment-results}

查看中未映射的段 [!UICONTROL Segment Performance] 報告是查找未考慮目標的新段的極好方法。 事實上，其中某些段可能比映射的段要好。 這是因為未映射的段必須滿足要包含在此報表中的一組資格標準。 要包括在此報表中，未映射的段必須：

* 轉換率大於所有映射段的平均值。
* 按轉換率位於前100個未映射的段中。

要閱讀此報告，它有助於將結果分成4個部分，其中虛線（以紅色表示）和類別顯示在下面的示例報告中。

![](assets/unmapped-segment-performance.png)

在此報告中，您只想關注左上部未映射的段。 這些未映射的段與其他三個段中的段相比，顯示出高的轉換率，具有低的印象。

>[!NOTE]
>
>7天和30天回望期僅在星期日提供 **[!UICONTROL Date Through]** 日期。
