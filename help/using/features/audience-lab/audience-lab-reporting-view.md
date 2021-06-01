---
description: 測試群組報表區段會傳回測試群組轉換的資訊，以便輕鬆比較測試區段效能。 資料視覺化可使用許多篩選器和維度。
seo-description: 測試群組報表區段會傳回測試群組轉換的資訊，以便輕鬆比較測試區段效能。 資料視覺化可使用許多篩選器和維度。
seo-title: 測試群組報表
solution: Audience Manager
title: 測試群組報表
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 3%

---

# 測試群組報表 {#test-group-reporting}

測試群組報表區段會傳回測試群組轉換的資訊，以便輕鬆比較測試區段效能。 資料視覺化可使用許多篩選器和維度。

[!UICONTROL Audience Lab] 會傳回您建立之測試區段的詳細報表資訊，並可讓您將報表資料儲存為 [!DNL CSV] 檔案。您可以在&#x200B;**[!UICONTROL Aggregate Reporting]**&#x200B;和&#x200B;**[!UICONTROL Trend Reporting]**&#x200B;之間進行選擇。

**[!UICONTROL Aggregate Reporting]** 傳回測試區段的絕對數字。**[!UICONTROL Trend Reporting]** 傳回特定期間 *的趨勢圖*。四個索引標籤可讓您自訂報表：

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 母體轉換率</span></b> </p> </td> 
   <td colname="col2"> <p>傳回屬於已轉換之特定測試區段的裝置百分比。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 轉換器</span></b> </p> </td> 
   <td colname="col2"> <p>傳回已顯示在測試群組中選取之轉換特徵的裝置數。 <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> 觀看此影</a> 片，了解如何建立轉換特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 轉換總數</span></b> </p> </td> 
   <td colname="col2"> <p>傳回測試區段產生的轉換數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 測試區段母體</span></b> </p> </td> 
   <td colname="col2"> <p>傳回屬於測試區段的裝置數。 在「總母體</span></b>」或「<b><span class="uicontrol">即時母體</span></b>」之間切換。 <b><span class="uicontrol">差異在<a href="../../faq/faq-reporting.md">報表常見問題集</a>中說明。 </span></b></p> </td>
  </tr>
 </tbody>
</table>

您可以選取要為其產生報表的特定轉換特徵，或選取合併的所有特徵。 您可以定義應傳回資訊的日期範圍，並將報表匯出為[!DNL CSV]檔案。

>[!NOTE]
>
>* 測試群組的報表會在其開始日期後填入。
>* 轉換只會在測試開始日期之後和裝置已新增至測試區段後計入。 如果該裝置在指派測試群組前發生轉換，則不會計算轉換。


傳回的&#x200B;**[!UICONTROL Aggregate Reporting]**&#x200B;圖表可能如下所示：

![](assets/aggregate-reporting.PNG)

傳回的&#x200B;**[!UICONTROL Trend Reporting]**&#x200B;圖表看起來可能如下所示。 如果要忽略絕對數字，並只關注測試區段趨勢，請選取核取方塊中的&#x200B;**[!UICONTROL Normalized]** 。

![](assets/trend-reporting.PNG)
