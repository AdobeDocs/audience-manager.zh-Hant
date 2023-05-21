---
description: 關於Audience Manager如何與第三方內容提供商執行即時資料傳輸的概述。
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: 描述的即時資料傳輸過程
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---


# 描述的即時資料傳輸過程{#real-time-data-transfer-process-described}

關於Audience Manager如何與第三方內容提供商執行即時資料傳輸的概述。

<!-- real-time-data-transfer-explained.xml -->

## 即時資料傳輸

作為用戶訪問或在您的站點上執行操作，即時資料傳輸發送和接收段ID。 通常，在您需要立即確定用戶資格或對用戶進行細分時，同步資料傳輸非常有用，因為用戶在清單中導航。

## 資料整合步驟

即時資料整合過程的工作如下：

1. 用戶訪問包含Audience Manager代碼的客戶站點。
1. Audience Manager載入一個幀，並呼叫我們 [!UICONTROL Data Collection Server] ( [!DNL DCS])。
1. 的 [!DNL DCS] 調用第三方伺服器（即時）以檢查供應商是否具有有關用戶的任何段資訊。
1. 內容提供方將有關該用戶的段資訊返回給Audience Manager。
1. Audience Manager接收此段資訊，並使其可用於定位和構建新的特性和段。

![](assets/rt_reduce70.png)