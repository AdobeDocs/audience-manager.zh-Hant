---
description: 概述Audience Manager如何與第三方廠商執行非同步批次資料交換。
seo-description: 概述Audience Manager如何與第三方廠商執行非同步批次資料交換。
seo-title: 批次資料傳輸程序說明
solution: Audience Manager
title: 批次資料傳輸程序說明
uuid: a eeee940-151c-44f8-9Fe9-4ab47d7fu45c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Batch Data Transfer Process Described {#batch-data-transfer-process-described}

概述Audience Manager如何與第三方廠商執行非同步批次資料交換。

## 批次資料整合

<!-- c_async.xml -->

批次資料整合程序可將訪客資訊儲存在我們的伺服器上，並將該資料與供應商在定期間隔傳送的資料同步。在下列情況下，非同步資料傳輸程序很有用：

* 不需要立即傳輸資料。
* 收集資料以建立一大群區段使用者。
* You want to reduce data discrepancies and `HTTP` calls from the browser.

![](assets/s2s_70.png)

## 資料整合步驟

1. 使用者瀏覽客戶網站。
1. Audience Manager和第三方資料提供者會指派訪客唯一ID(通常使用Cookie)。
1. Audience Manager會呼叫第三方資料提供者以符合訪客ID。
1. 排程的請求通常會在每日間隔內，交換Audience Manager與第三方資料供應商之間的訪客區段資料。
1. Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner. For more information, see [Sample Message to Partners after Inbound Processing](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).