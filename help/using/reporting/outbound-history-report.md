---
description: 查看指定目標和時間期的出站批處理作業歷史記錄資訊。
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
ht-degree: 6%

---

# 傳出檔案歷史記錄 {#outbound-file-history}

查看指定目標和時間期的出站批處理作業歷史記錄資訊。

<!-- 

t_reports_outbound_history.xml

 -->

1. 按一下 **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![步驟結果](assets/outbound_history.png)

1. 在 **[!UICONTROL Search for a Destination]** 框中，開始鍵入並選擇所需的目標。
1. 在 **[!UICONTROL Select a Date Range]** 框中，指定報表的起始日期和終止日期，然後按一下 **[!UICONTROL Apply Date Filter]**。

   ![步驟結果](assets/outbound_history_stats.png)

   下表包含與報表中各列對應的資訊：

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 折線圖 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 資料同步檔案名 </td> 
   <td colname="col2"> <p>所有出站檔案的清單 <span class="keyword"> Adobe</span> 為已一起處理的此目標生成。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 成功 </td> 
   <td colname="col2"> <p>成功從發送的記錄數 <span class="keyword"> Audience Manager</span> 到目的地。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 顯示 </td> 
   <td colname="col2"> <p>無法發送到目標的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 接收的記錄 </td> 
   <td colname="col2"> <p>記錄總數 <span class="keyword"> Adobe</span> 並嘗試發送到目標。 在大多數情況下，這應該是成功檔案和失敗檔案的總數。 </p> </td> 
  </tr> 
 </tbody> 
</table>
