---
description: test組報告部分返回有關test組轉換的資訊，從而可以輕鬆比較test段的功效。 許多篩選器和維可用於資料可視化。
seo-description: The test group reporting section returns information on test group conversions, allowing an easy comparison of test segment efficacy. Numerous filters and dimensions are available for data visualization.
seo-title: Test Group Reporting
solution: Audience Manager
title: 測試群組報表
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 2%

---

# 測試群組報表 {#test-group-reporting}

test組報告部分返回有關test組轉換的資訊，從而可以輕鬆比較test段的功效。 許多篩選器和維可用於資料可視化。

[!UICONTROL Audience Lab] 返回您建立的test段的詳細報告資訊，並允許您將報告資料另存為 [!DNL CSV] 的子菜單。 可以在 **[!UICONTROL Aggregate Reporting]** 和 **[!UICONTROL Trend Reporting]**。

**[!UICONTROL Aggregate Reporting]** 返回test段的絕對數。 **[!UICONTROL Trend Reporting]** 返回趨勢圖 *在特定期間*。 四個頁籤使您能夠自定義報告：

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 人口換算率</span></b> </p> </td> 
   <td colname="col2"> <p>返回屬於已轉換的特定test段的設備百分比。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 轉換器</span></b> </p> </td> 
   <td colname="col2"> <p>返回顯示在test組中選擇的轉換特性的設備數。 <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> 觀看此視頻</a> 學習如何建立轉換特性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 轉換總數</span></b> </p> </td> 
   <td colname="col2"> <p>返回由test段生成的轉換數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Test部分人口</span></b> </p> </td> 
   <td colname="col2"> <p>返回屬於test段的設備數。 在 <b><span class="uicontrol"> 總人口</span></b> 或 <b><span class="uicontrol"> 即時人口</span></b>。 差異在 <a href="../../faq/faq-reporting.md"> 報告常見問題</a> 。 </p> </td>
  </tr>
 </tbody>
</table>

您可以選擇要為其生成報告的特定轉換特性，也可以選擇所有組合的特性。 您可以定義應返回資訊的日期範圍，並將報表導出為 [!DNL CSV] 的子菜單。

>[!NOTE]
>
>* test組的報告將在其開始日期之後填充。
>* 只在test的開始日期之後和設備被添加到test段之後對設備計算轉換。 如果在為該設備分配test組之前對它進行轉換，則不會計算轉換。


返回 **[!UICONTROL Aggregate Reporting]** 圖表可能如下所示：

![](assets/aggregate-reporting.PNG)

返回 **[!UICONTROL Trend Reporting]** 圖表可能與下面的圖表相似。 選擇 **[!UICONTROL Normalized]** 框中，選擇「 CSV文本」。

![](assets/trend-reporting.PNG)
