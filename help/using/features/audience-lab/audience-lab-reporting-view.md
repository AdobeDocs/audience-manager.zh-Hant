---
description: 測試群組報告區域傳回測試群組轉換的相關資訊，以便輕鬆比較測試區段有效性。有許多濾鏡和維度可用於資料視覺化。
seo-description: 測試群組報告區域傳回測試群組轉換的相關資訊，以便輕鬆比較測試區段有效性。有許多濾鏡和維度可用於資料視覺化。
seo-title: 測試群組報表
solution: Audience Manager
title: 測試群組報表
topic: DIL API
uuid: 21303c3e-4c05-4728-a759-96c2 a1 d99 b69
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Test Group Reporting {#test-group-reporting}

測試群組報告區域傳回測試群組轉換的相關資訊，以便輕鬆比較測試區段有效性。有許多濾鏡和維度可用於資料視覺化。

[!UICONTROL Audience Lab] 傳回您建立之測試區段的詳細報表資訊，並讓您將報告資料儲存為 [!DNL CSV] 檔案。You can select between **[!UICONTROL Aggregate Reporting]** and **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** 傳回測試區段的絕對數字。**[!UICONTROL Trend Reporting]** 傳回特定時段趨勢 *的圖表*。有四個標籤可讓您自訂報表：

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 人口轉換比率</span></b> </p> </td> 
   <td colname="col2"> <p>傳回屬於已轉換之特定測試區段之裝置的百分比。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 轉換器</span></b> </p> </td> 
   <td colname="col2"> <p>傳回已在測試群組中選取轉換特徵的裝置數目。<a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> 觀看此影片</a> 以瞭解如何建立轉化特性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 轉換總數</span></b> </p> </td> 
   <td colname="col2"> <p>傳回測試區段產生的轉換次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 測試區段人口族群</span></b> </p> </td> 
   <td colname="col2"> <p>傳回屬於測試區段的裝置數。Toggle between <b><span class="uicontrol"> Total Population</span></b> or <b><span class="uicontrol"> Real-time Population</span></b>. The difference is explained in the <a href="../../faq/faq-reporting.md"> Reporting FAQ</a> . </p> </td>
  </tr>
 </tbody>
</table>

您可以選取要產生報表的特定轉換特徵，或者選取所有結合的特徵。You can define a date range for which the information should be returned and export the report as a [!DNL CSV] file.

>[!NOTE]
>
>* 測試群組的報告將在其開始日期後的一天填入。
>* 只有在測試開始日期後以及裝置已新增至測試區段後，才會對裝置計數。如果該裝置在指派測試群組之前發生轉換，則不會計算轉換。


A returned **[!UICONTROL Aggregate Reporting]** chart could look like this:

![](assets/aggregate-reporting.PNG)

A returned **[!UICONTROL Trend Reporting]** chart could look like the one below. Select **[!UICONTROL Normalized]** in the check box if you want to ignore the absolute numbers and simply focus on the test segments trends.

![](assets/trend-reporting.PNG)