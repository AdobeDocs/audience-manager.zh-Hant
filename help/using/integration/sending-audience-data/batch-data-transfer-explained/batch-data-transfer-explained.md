---
description: 概述Audience Manager如何執行與協力廠商的非同步批次資料交換。
seo-description: 概述Audience Manager如何執行與協力廠商的非同步批次資料交換。
seo-title: 批次資料傳輸流程說明
solution: Audience Manager
title: 批次資料傳輸流程說明
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: 傳入資料傳輸
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 8%

---

# 批次資料傳輸流程說明 {#batch-data-transfer-process-described}

概述[!DNL Audience Manager]如何執行與協力廠商的非同步批次資料交換。

## 批次資料整合

<!-- c_async.xml -->

批次資料整合程式會儲存伺服器上的訪客資訊，並定期將該資料與提供者傳送的資料同步。 非同步資料傳輸程式在下列情況下相當實用：

* 不需要立即傳輸資料。
* 收集資料以建立大量分段使用者。
* 您想要減少瀏覽器的資料差異和`HTTP`呼叫。

![](assets/s2s_70.png)

## 資料整合步驟

1. 使用者造訪客戶網站。
1. [!DNL Audience Manager] 而協力廠商資料提供者會為訪客指派唯一ID（通常具有cookie）。
1. [!DNL Audience Manager] 呼叫協力廠商資料提供者以符合訪客ID。
1. 排程的請求（通常是在每日間隔）會在[!DNL Audience Manager]和您的第三方資料提供者之間交換訪客區段資料。
1. 每當處理傳入[!UICONTROL Server-to-Server]檔案時，都會透過電子郵件傳送回執給合作夥伴解決方案，並在已設定時傳送給合作夥伴。 如需詳細資訊，請參閱傳入處理後傳送給合作夥伴的範例訊息](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md)。[
