---
description: 概述Audience Manager如何與協力廠商執行非同步批次資料交換。
seo-description: 概述Audience Manager如何與協力廠商執行非同步批次資料交換。
seo-title: 批次資料傳輸流程說明
solution: Audience Manager
title: 批次資料傳輸流程說明
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 7%

---


# 批次資料傳輸流程說明 {#batch-data-transfer-process-described}

概述如何執行 [!DNL Audience Manager] 與協力廠商的非同步批次資料交換。

## 批次資料整合

<!-- c_async.xml -->

批次資料整合程式會將訪客資訊儲存在我們的伺服器上，並定期將該資料與供應商傳送的資料同步。 在下列情況下，非同步資料傳輸程式非常有用：

* 不需要立即傳送資料。
* 收集資料，以建立龐大的細分使用者群。
* 您想要減少來自瀏覽器的資 `HTTP` 料不一致和呼叫。

![](assets/s2s_70.png)

## 資料整合步驟

1. 使用者瀏覽客戶網站。
1. [!DNL Audience Manager] 協力廠商資料提供者會為訪客指派唯一ID（通常使用Cookie）。
1. [!DNL Audience Manager] 呼叫協力廠商資料提供者，以符合訪客ID。
1. 排程的請求（通常在每日間隔內）會在您與第三方資料提供者之 [!DNL Audience Manager] 間交換訪客區段資料。
1. 每當處理傳 [!UICONTROL Server-to-Server] 入檔案時，收據會透過電子郵件傳送給合作夥伴解決方案，如果已設定，則會傳送給合作夥伴。 如需詳細資訊，請參 [閱傳入處理後傳送給合作夥伴的範例訊息](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md)。
