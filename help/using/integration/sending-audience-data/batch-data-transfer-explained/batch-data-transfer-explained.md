---
description: 關於Audience Manager如何與第三方供應商執行非同步批處理資料交換的概述。
seo-description: A general overview of how Audience Manager performs an asynchronous batch data exchange with a third-party vendor.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: 批次資料傳輸流程說明
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 5%

---

# 批次資料傳輸流程說明 {#batch-data-transfer-process-described}

概述 [!DNL Audience Manager] 執行與第三方供應商的非同步批處理資料交換。

## 批資料整合

<!-- c_async.xml -->

批處理資料整合流程會保存我們伺服器上的訪問者資訊，並定期將該資料與提供商發送的資料同步。 非同步資料傳輸過程在以下情況下非常有用：

* 不需要立即資料傳輸。
* 收集資料以構建一個大的分段用戶池。
* 您希望減少資料差異， `HTTP` 從瀏覽器發出的呼叫。

![](assets/s2s_70.png)

## 資料整合步驟

1. 用戶訪問客戶站點。
1. [!DNL Audience Manager] 第三方資料提供程式為訪問者分配一個唯一ID（通常使用cookie）。
1. [!DNL Audience Manager] 調用第三方資料提供程式以匹配訪問者ID。
1. 通常在每日間隔上的預定請求在以下之間交換訪問者段資料 [!DNL Audience Manager] 和第三方資料提供商。
1. 每當入站 [!UICONTROL Server-to-Server] 處理檔案，通過電子郵件將回執發送給合作夥伴解決方案，如果配置了，將回執發送給合作夥伴。 有關詳細資訊，請參見 [入站處理後發送給合作夥伴的示例消息](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md)。
