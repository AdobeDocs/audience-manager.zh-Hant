---
description: Audience Manager每天都會收到大量資料。 這會影響處理資料和產生報表結果所花的時間。 本節內容說明這些時間間隔對您的Audience Manager帳戶有何影響。 此外，此處所述的時間範圍和時間表僅是一般准則。 這些時間表不構成與資料交付相關的服務級別協定(SLA)或承諾。 Adobe保留隨時變更時間範圍和排程的權利，恕不另行通知。
seo-description: Audience Manager每天都會收到大量資料。 這會影響處理資料和產生報表結果所花的時間。 本節內容說明這些時間間隔對您的Audience Manager帳戶有何影響。 此外，此處所述的時間範圍和時間表僅是一般准則。 這些時間表不構成與資料交付相關的服務級別協定(SLA)或承諾。 Adobe保留隨時變更時間範圍和排程的權利，恕不另行通知。
seo-title: 資料傳送和檔案處理時間對報表的影響
solution: Audience Manager
title: 資料傳送和檔案處理時間對報表的影響
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: 6bdf79b17ec96ed0d54ed97ab5d69fadb68763b5

---


# 資料傳送和檔案處理時間對報表的影響{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager每天都會收到大量資料。 這會影響處理資料和產生報表結果所花的時間。 本節內容說明這些時間間隔對您的Audience Manager帳戶有何影響。 此外，此處所述的時間範圍和時間表僅是一般准則。 這些時間表不構成與資料交付相關的服務級別協定(SLA)或承諾。 Adobe保留隨時變更時間範圍和排程的權利，恕不另行通知。

## 報表編號 {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

下表列出並說明一般和即時報告中的時間間隔。


| 資料類型 | 說明 |
|---|---|
| 即時資料 | 今天的即時數字是從昨天開始的00:00到23:59:59. |
| 一般報表資料 | 「一般報 [告」中的資料](../reporting/general-reports.md#general-reports-overview) ，取決於其他作業流程的成功完成以及特定日期接收的資料量。 大多數時候，資 [!UICONTROL General Report] 料應在每天18:00 UTC前更新。 |

## 入站和出站檔案傳輸 {#inbound-outbound-file-transfers}

[!DNL Audience Manager] 根據本節所述的計畫，處 [!UICONTROL Server-to-Server (S2S)] 理併發送入站和出站檔案傳輸。 有了這些排程和中斷時間，您可能會發現即時和總區段數之間的新區段不一致。

| 檔案類型 | 說明 |
|---|---|
| 傳入檔案擷取（離線資料） | 每天會執行兩次檔案處理。 這些程式會收集資料並準備傳送。 檔案傳送時間因客戶資料總量而異，因此會有所不同。 從檔案上傳到Audience Manager到資料可供報告和啟用，您最多應該有48小時的延遲。 |
| 出站（導出）檔案 | 每天大約14:00 UTC進行一次檔案處理和傳送。 請記住，這些檔案的總數和大小會影響處理和傳送。 在某些情況下，檔案處理可能會延遲長達24小時。 發生此情況時，Audience Manager會傳送2個檔案給特定日期，而非1個檔案。 在Audience Manager必須完全停止處理檔案的罕見情況下，我們會通知客戶。 鑒於這些情況，很難估計出站資料的傳送時間。 要確定您是否收到完整的檔案集，請檢查時間戳記並查找任何缺少的日期。 這是一個13位數的UNIX UTC時間戳記，記錄檔案建立的時間。 請參 [閱即時出站資料傳輸](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md)。 |
| 廣告伺服器記錄檔 | 檔案處理會近乎即時執行，以在每小時檔案就緒時收錄記錄檔。 準備要報告的檔案的程式每天執行一次。 檔案傳送時間因客戶資料總量而異，因此會有所不同。 從您將檔案上傳至Audience Manager到資料可供報告和啟動之間，您最多應該會等待48小時。 |

>[!MORELIKETHIS]
>
>* [傳入客戶資料擷取常見問答集](../faq/faq-inbound-data-ingestion.md)

