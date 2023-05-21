---
description: Audience Manager每天都接收大量資料。 這會影響處理資料和生成報告結果所花的時間。 本節的內容介紹這些時間間隔如何影響您的Audience Manager帳戶。 此外，此處描述的時間框架和計畫僅是一般准則。 這些計畫不構成與資料交付相關的服務級別協定(SLA)或承諾。 Adobe保留隨時更改時間框架和時間表的權利，恕不另行通知。
seo-description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-title: How Data Delivery and File Processing Times Affect Reports
solution: Audience Manager
title: 資料傳送和檔案處理時間對報表的影響
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: Reference
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 4%

---

# 資料傳送和檔案處理時間對報表的影響{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager每天都接收大量資料。 這會影響處理資料和生成報告結果所花的時間。 本節的內容介紹這些時間間隔如何影響您的Audience Manager帳戶。 此外，此處描述的時間框架和計畫僅是一般准則。 這些計畫不構成與資料交付相關的服務級別協定(SLA)或承諾。 Adobe保留隨時更改時間框架和時間表的權利，恕不另行通知。

## 報告編號 {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

下表列出並描述了常規報告和即時報告中的時間間隔。


| 資料類型 | 說明 |
|---|---|
| 即時資料 | 今天的即時數是00:00到23小時:59:世界協調時，昨天開始。 |
| 一般報告資料 | 中的資料 [一般報告](../reporting/general-reports.md#general-reports-overview) 取決於其他作業進程的成功完成以及特定日期接收的資料量。 大多數時候， [!UICONTROL General Report] 每天18:00 UTC前更新資料。 |

## 入站和出站檔案傳輸 {#inbound-outbound-file-transfers}

[!DNL Audience Manager] 進程和發送入站和出站 [!UICONTROL Server-to-Server (S2S)] 根據本節中介紹的時間表進行檔案傳輸。 考慮到這些計畫和截止時間，您可能會看到即時段編號和總段編號之間存在新段的差異。

| 檔案類型 | 說明 |
|---|---|
| 入站檔案接收（離線資料） | 每天執行兩次檔案處理。 這些過程會接收資料並準備交付。 檔案交付時間因需要處理的客戶資料總量而異。 從檔案以Audience Manager形式上載到資料可用於報告和激活之前，您應該預計最大延遲為48小時。 |
| 出站（導出）檔案 | 檔案處理和傳遞每天進行一次，大約在UTC時間14點。 請記住，這些檔案的總數和大小會影響處理和交付。 在某些情況下，檔案處理可能會延遲24小時。 當發生這種情況時，Audience Manager將發送2個檔案，而不是1個。 在Audience Manager必須完全停止處理檔案的情況下，我們將通知客戶。 鑒於這些情況，很難估計出站資料的交付時間。 要確定您是否收到完整的檔案集，請檢查時間戳並查找任何丟失的日期。 這是一個13位的UNIX UTC時間戳，記錄檔案建立的時間。 請參閱 [即時出站資料傳輸](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md)。 |
| Ad Server日誌檔案 | 檔案處理在小時檔案就緒時以接近即時的方式執行以接收日誌檔案記錄。 為報告準備檔案的過程每天執行一次。 檔案交付時間因需要處理的客戶資料總量而異。 從您將檔案上載到Audience Manager到資料可用於報告和激活之間，您應該預計最大延遲為48小時。 |

>[!MORELIKETHIS]
>
>* [傳入客戶資料擷取常見問題集](../faq/faq-inbound-data-ingestion.md)

