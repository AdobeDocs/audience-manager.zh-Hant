---
description: 概述Audience Manager如何與協力廠商內容提供者執行即時資料傳輸。
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: 即時資料傳輸流程說明
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: a03b8192-8410-479f-a326-4cddf10757f6
    internal-label: Inbound data transfers
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%
---

# 即時資料傳輸流程說明{#real-time-data-transfer-process-described}

概述Audience Manager如何與協力廠商內容提供者執行即時資料傳輸。

<!-- real-time-data-transfer-explained.xml -->

## 即時資料傳輸

即時資料傳輸會在使用者造訪您的網站或在您的網站上採取動作時，傳送及接收區段ID。 通常，當您需要立即讓使用者在瀏覽您的詳細目錄時符合資格或劃分使用者時，同步資料傳輸會很有用。

## 資料整合步驟

即時資料整合程式的運作方式如下：

1. 使用者造訪包含Audience Manager程式碼的客戶網站。
1. Audience Manager載入iframe並呼叫[!UICONTROL Data Collection Server] ( [!DNL DCS])。
1. [!DNL DCS]會呼叫協力廠商伺服器（即時）以檢查廠商是否有任何關於使用者的區段資訊。
1. 內容提供者會將該使用者的相關區段資訊傳回給Audience Manager。
1. Audience Manager會收到此區段資訊，並可用於鎖定和建立新特徵和區段。

![](assets/rt_reduce70.png)