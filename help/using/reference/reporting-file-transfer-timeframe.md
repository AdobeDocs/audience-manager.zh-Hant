---
description: Audience Manager每天收到大量資料。這會影響處理資料並產生報告結果所需的時間。本節內容說明這些時間間隔如何影響Audience Manager帳戶。此外，此處所述的時間範圍和時間表僅為一般指引。這些計劃不構成服務層級合約(SLA)或與資料傳送相關的承諾。Adobe保留隨時變更時限和時程的權利，恕不另行通知。
seo-description: Audience Manager每天收到大量資料。這會影響處理資料並產生報告結果所需的時間。本節內容說明這些時間間隔如何影響Audience Manager帳戶。此外，此處所述的時間範圍和時間表僅為一般指引。這些計劃不構成服務層級合約(SLA)或與資料傳送相關的承諾。Adobe保留隨時變更時限和時程的權利，恕不另行通知。
seo-title: 資料傳送和檔案處理時間如何影響報表
solution: Audience Manager
title: 資料傳送和檔案處理時間如何影響報表
uuid: 4b975512-f67 e-4749-a7 ef-168415597682
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# How Data Delivery and File Processing Times Affect Reports{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager每天收到大量資料。這會影響處理資料並產生報告結果所需的時間。本節內容說明這些時間間隔如何影響Audience Manager帳戶。此外，此處所述的時間範圍和時間表僅為一般指引。這些計劃不構成服務層級合約(SLA)或與資料傳送相關的承諾。Adobe保留隨時變更時限和時程的權利，恕不另行通知。

## Reporting Numbers {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

下表列出並說明一般與即時報告中的時間間隔。

<table id="table_73AF95DF5D3A423894486444505D816A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 資料類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>即時資料</b> </p> </td> 
   <td colname="col2"> <p> 今天的即時數字是從昨天的00：00到23：59：59UTC。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>一般報表資料</b> </p> </td> 
   <td colname="col2"> <p><a href="../reporting/general-reports.md#general-reports-overview"> 「一般報表」中的資料</a> 取決於其他工作流程是否成功完成，以及特定日期收到的資料量。Most of the time, <span class="wintitle"> General Report</span> data should be updated by 18:00 UTC each day. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Inbound and Outbound File Transfers {#inbound-outbound-file-transfers}

[!DNL Audience Manager] 程序，並根據本節所述的排程傳送傳入和傳出 [!UICONTROL Server-to-Server (S2S)] 檔案傳輸。鑒於這些時間表和截止時間，您可能會看到即時和區段總數之間新區段的差異。

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>傳入檔案擷取(離線資料)</b> </p> </td> 
   <td colname="col2"> <p>檔案處理每天執行兩次。這些程序收錄資料並準備用於傳送。 </p> <p>檔案傳送時間因客戶資料總金額所受到的影響而有所不同。You should expect a maximum latency of 48 hours between the moment the file is uploaded in <span class="keyword"> Audience Manager</span> and until the data is available for reporting and activation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>輸出(匯出)檔案</b> </p> </td> 
   <td colname="col2"> <p>檔案處理和傳送每天進行一次，大約14：00UTC。請記住，處理和傳送會受到這些檔案總數和大小的影響。在某些情況下，檔案處理可能延遲長達24小時。When this happens, <span class="keyword"> Audience Manager</span> will send 2 files for a particular day instead of 1. <span class="keyword"> 在Audience Manager</span> 必須停止處理檔案的罕見案例中，我們會通知客戶。在這些情況下，很難估計傳出資料的傳送時間。 </p> <p>若要判斷您是否已收到完整的檔案集，請檢查時間戳記並尋找遺漏的日期。這是13位數的UNIX UTC時間戳記，用來記錄檔案建立的時間。See <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> Real-Time Outbound Data Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_贊_ this]
>
>* [傳入客戶資料擷取常見問題集](../faq/faq-inbound-data-ingestion.md)

