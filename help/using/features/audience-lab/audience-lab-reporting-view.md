---
description: 測試群組報告區段會傳回測試群組轉換的資訊，讓您輕鬆比較測試區段的效能。 有許多篩選器和維度可供資料視覺化使用。
seo-description: 測試群組報告區段會傳回測試群組轉換的資訊，讓您輕鬆比較測試區段的效能。 有許多篩選器和維度可供資料視覺化使用。
seo-title: 測試群組報表
solution: Audience Manager
title: 測試群組報表
topic-edit: DIL API
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 3%

---

# 測試群組報表 {#test-group-reporting}

測試群組報告區段會傳回測試群組轉換的資訊，讓您輕鬆比較測試區段的效能。 有許多篩選器和維度可供資料視覺化使用。

[!UICONTROL Audience Lab] 傳回您建立之測試區段的詳細報表資訊，並可讓您將報表資料儲存為 [!DNL CSV] 檔案。您可以選擇&#x200B;**[!UICONTROL Aggregate Reporting]**&#x200B;和&#x200B;**[!UICONTROL Trend Reporting]**。

**[!UICONTROL Aggregate Reporting]** 傳回測試區段的絕對數。**[!UICONTROL Trend Reporting]** 傳回特定時段 *的趨勢圖*。四個標籤可讓您自訂報表：

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 人口轉換率</span></b> </p> </td> 
   <td colname="col2"> <p>傳回屬於已轉換之特定測試區段之裝置的百分比。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 轉換器</span></b> </p> </td> 
   <td colname="col2"> <p>傳回已顯示測試群組中選取之轉換特徵的裝置數目。 <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> 觀看此影</a> 片，瞭解如何建立轉換特性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 轉換總數</span></b> </p> </td> 
   <td colname="col2"> <p>傳回測試區段產生的轉換數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 測試區段人口族群</span></b> </p> </td> 
   <td colname="col2"> <p>傳回屬於測試區段的裝置數。 在<b><span class="uicontrol">總人口</span></b>或<b><span class="uicontrol">即時人口</span></b>之間切換。 差異在<a href="../../faq/faq-reporting.md">報告常見問答集</a>中說明。 </p> </td>
  </tr>
 </tbody>
</table>

您可以選取要產生報表的特定轉換特徵，或選取所有結合的特徵。 您可以定義要傳回資訊的日期範圍，並將報表匯出為[!DNL CSV]檔案。

>[!NOTE]
>
>* 測試群組的報表會在其開始日期後的某一天填入。
>* 轉換只會在測試開始日期之後以及裝置已新增至測試區段後，計入裝置。 如果該裝置在指派測試群組之前發生轉換，則不會計算轉換。


傳回的&#x200B;**[!UICONTROL Aggregate Reporting]**&#x200B;圖表可能如下所示：

![](assets/aggregate-reporting.PNG)

傳回的&#x200B;**[!UICONTROL Trend Reporting]**&#x200B;圖表可能類似下方的圖表。 如果您要忽略絕對數字，並只關注測試區段趨勢，請在核取方塊中選取&#x200B;**[!UICONTROL Normalized]**。

![](assets/trend-reporting.PNG)
