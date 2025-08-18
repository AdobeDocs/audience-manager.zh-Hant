---
description: 檢視指定目的地和時段的輸出批次工作歷史記錄資訊。
seo-description: View outbound batch job history information for a specified destination and time period.
seo-title: Outbound File History
solution: Audience Manager
title: 傳出檔案歷史記錄
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: Inbound and Outbound Reports
exl-id: 8072c44f-bc9a-4b40-99d9-8cb87bb58d98
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 1%

---

# 傳出檔案歷史記錄 {#outbound-file-history}

檢視指定目的地和時段的輸出批次工作歷史記錄資訊。

<!-- 

t_reports_outbound_history.xml

 -->

1. 按一下&#x200B;**[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**。

   ![步驟結果](assets/outbound_history.png)

1. 在&#x200B;**[!UICONTROL Search for a Destination]**&#x200B;方塊中，開始輸入並選取想要的目的地。
1. 在&#x200B;**[!UICONTROL Select a Date Range]**&#x200B;方塊中，指定報告的開始和結束日期，然後按一下&#x200B;**[!UICONTROL Apply Date Filter]**。

   ![步驟結果](assets/outbound_history_stats.png)

   下表包含與報表中各欄對應的資訊：

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 折線圖 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 資料同步檔案名稱 </td> 
   <td colname="col2"> <p><span class="keyword"> Adobe</span>針對此目的地產生的所有輸出檔案清單，這些檔案已一起處理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 成功 </td> 
   <td colname="col2"> <p>從<span class="keyword"> Audience Manager</span>成功傳送至目的地的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 顯示 </td> 
   <td colname="col2"> <p>無法傳送到目的地的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已接收的記錄 </td> 
   <td colname="col2"> <p>在檔案中產生並嘗試傳送至目的地的記錄總數<span class="keyword"> Adobe</span>。 在大多數情況下，這應該是成功檔案和失敗檔案的總數。 </p> </td> 
  </tr> 
 </tbody> 
</table>
