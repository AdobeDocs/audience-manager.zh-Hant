---
description: Audience manager每天都會收到大量資料。 這會影響處理資料和產生報表結果所花的時間。 本節內容說明這些時間間隔對您的Audience manager帳戶有何影響。 此外，此處所述的時間範圍和時間表僅是一般准則。 這些時間表不構成與資料交付相關的服務級別協定(SLA)或承諾。 Adobe保留隨時變更時間範圍和排程的權利，恕不另行通知。
seo-description: Audience manager每天都會收到大量資料。 這會影響處理資料和產生報表結果所花的時間。 本節內容說明這些時間間隔對您的Audience manager帳戶有何影響。 此外，此處所述的時間範圍和時間表僅是一般准則。 這些時間表不構成與資料交付相關的服務級別協定(SLA)或承諾。 Adobe保留隨時變更時間範圍和排程的權利，恕不另行通知。
seo-title: 資料傳送和檔案處理時間對報表的影響
solution: Audience Manager
title: 資料傳送和檔案處理時間對報表的影響
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 資料傳送和檔案處理時間對報表的影響{#how-data-delivery-and-file-processing-times-affect-reports}

Audience manager每天都會收到大量資料。 這會影響處理資料和產生報表結果所花的時間。 本節內容說明這些時間間隔對您的Audience manager帳戶有何影響。 此外，此處所述的時間範圍和時間表僅是一般准則。 這些時間表不構成與資料交付相關的服務級別協定(SLA)或承諾。 Adobe保留隨時變更時間範圍和排程的權利，恕不另行通知。

## 報表編號 {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

下表列出並說明一般和即時報告中的時間間隔。

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
   <td colname="col2"> <p> 今天的即時數字是從昨天開始的00:00到23:59:59. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>一般報表資料</b> </p> </td> 
   <td colname="col2"> <p>「一般報 <a href="../reporting/general-reports.md#general-reports-overview"> 表」中的資料</a> ，取決於其他作業程式是否成功完成以及某一天收到的資料量。 大多數時候，「 <span class="wintitle"> 一般報告</span> 」資料應在每天18:00 UTC之前更新。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 入站和出站檔案傳輸 {#inbound-outbound-file-transfers}

[!DNL Audience Manager] 根據本節所述的計畫，處 [!UICONTROL Server-to-Server (S2S)] 理併發送入站和出站檔案傳輸。 有了這些排程和中斷時間，您可能會發現即時和總區段數之間的新區段不一致。

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>傳入檔案擷取（離線資料）</b> </p> </td> 
   <td colname="col2"> <p>每天會執行兩次檔案處理。 這些程式會收集資料並準備傳送。 </p> <p>檔案傳送時間因客戶資料總量而異，因此會有所不同。 從檔案上傳到 <span class="keyword"> Audience Manager</span> ，直到資料可供報告和啟動，您最多預計會延遲48小時。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>出站（導出）檔案</b> </p> </td> 
   <td colname="col2"> <p>每天大約14:00 UTC進行一次檔案處理和傳送。 請記住，這些檔案的總數和大小會影響處理和傳送。 在某些情況下，檔案處理可能會延遲長達24小時。 發生此情況時， <span class="keyword"> Audience Manager</span> 將傳送2個檔案給特定日期，而非1。 在Audience Manager必須完全停止處理檔案的罕見情況下 <span class="keyword"></span> ，我們會通知客戶。 鑒於這些情況，很難估計出站資料的傳送時間。 </p> <p>要確定您是否收到完整的檔案集，請檢查時間戳記並查找任何缺少的日期。 這是一個13位數的UNIX UTC時間戳記，記錄檔案建立的時間。 請參 <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> 閱即時出站資料傳輸</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [傳入客戶資料擷取常見問答集](../faq/faq-inbound-data-ingestion.md)

