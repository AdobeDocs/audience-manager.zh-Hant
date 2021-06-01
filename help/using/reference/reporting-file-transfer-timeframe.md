---
description: Audience Manager每天都會收到大量資料。 這會影響處理資料和產生報表結果所花的時間。 本節中的內容說明這些時間間隔對您的Audience Manager帳戶有何影響。 此外，此處描述的時間範圍和排程僅為一般准則。 這些時間表不構成與資料傳送相關的服務級別協定(SLA)或承諾。 Adobe保留隨時變更時間範圍和排程的權利，恕不另行通知。
seo-description: Audience Manager每天都會收到大量資料。 這會影響處理資料和產生報表結果所花的時間。 本節中的內容說明這些時間間隔對您的Audience Manager帳戶有何影響。 此外，此處描述的時間範圍和排程僅為一般准則。 這些時間表不構成與資料傳送相關的服務級別協定(SLA)或承諾。 Adobe保留隨時變更時間範圍和排程的權利，恕不另行通知。
seo-title: 資料傳送和檔案處理時間對報表的影響
solution: Audience Manager
title: 資料傳送和檔案處理時間對報表的影響
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: 參考
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 5%

---

# 資料傳送和檔案處理時間對報表的影響{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager每天都會收到大量資料。 這會影響處理資料和產生報表結果所花的時間。 本節中的內容說明這些時間間隔對您的Audience Manager帳戶有何影響。 此外，此處描述的時間範圍和排程僅為一般准則。 這些時間表不構成與資料傳送相關的服務級別協定(SLA)或承諾。 Adobe保留隨時變更時間範圍和排程的權利，恕不另行通知。

## 報表編號{#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

下表列出並說明一般和即時報表中的時間間隔。


| 資料類型 | 說明 |
|---|---|
| 即時資料 | 當天的即時數字為00:00到23:59:59 UTC的時間。 |
| 一般報表資料 | [一般報表](../reporting/general-reports.md#general-reports-overview)中的資料取決於其他作業流程的成功完成以及特定日期收到的資料量。 大多數情況下，[!UICONTROL General Report]資料應以每天18:00 UTC更新。 |

## 傳入和傳出檔案傳輸{#inbound-outbound-file-transfers}

[!DNL Audience Manager] 會根據本節所述的排程 [!UICONTROL Server-to-Server (S2S)] 處理及傳送傳入和傳出檔案傳輸。有了這些排程和截止時間，您可能會在即時和總區段數之間看到新區段的差異。

| 檔案類型 | 說明 |
|---|---|
| 傳入檔案擷取（離線資料） | 檔案處理每天執行兩次。 這些程式會擷取資料並準備傳送。 檔案傳送時間可能有所不同，因為它們會受到需要處理的客戶資料總量的影響。 從檔案以Audience Manager上傳到資料可供報表和啟動之前，最多應延遲48小時。 |
| 傳出（匯出）檔案 | 檔案處理和傳送每天進行一次，大約在UTC 14:00。 請記住，處理和傳送會受這些檔案的總數和大小影響。 在某些情況下，檔案處理可能會延遲24小時。 發生此情況時，Audience Manager會針對特定日期傳送2個檔案，而非1個。 在Audience Manager必須完全停止處理檔案的罕見情況下，我們會通知客戶。 基於這些條件，很難估計傳出資料的傳送時間。 若要確定您是否收到完整的檔案集，請檢查時間戳記，並尋找任何遺失的日期。 這是13位數的UNIX UTC時間戳記，會記錄檔案建立的時間。 請參閱[即時傳出資料傳輸](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md)。 |
| 廣告伺服器記錄檔 | 檔案處理會近乎即時執行，以在每小時檔案準備就緒時內嵌記錄檔記錄。 準備檔案以進行報告的程式每天執行一次。 檔案傳送時間可能有所不同，因為它們會受到需要處理的客戶資料總量的影響。 從您上傳檔案至Audience Manager，到資料可供報表和啟動，最長應延遲48小時。 |

>[!MORELIKETHIS]
>
>* [傳入客戶資料擷取常見問題集](../faq/faq-inbound-data-ingestion.md)

