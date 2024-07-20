---
description: 概述Audience Manager如何與協力廠商執行非同步批次資料交換。
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
ht-degree: 0%

---

# 批次資料傳輸流程說明 {#batch-data-transfer-process-described}

[!DNL Audience Manager]如何與協力廠商執行非同步批次資料交換的一般概觀。

## 批次資料整合

<!-- c_async.xml -->

批次資料整合程式會將訪客資訊儲存在我們的伺服器上，並定期將該資料與提供者傳送的資料同步。 非同步資料傳輸程式在下列情況下相當實用：

* 不需要立即傳輸資料。
* 收集資料以建立大型分段使用者集區。
* 您想要減少資料差異和瀏覽器的`HTTP`呼叫。

![](assets/s2s_70.png)

## 資料整合步驟

1. 使用者造訪客戶網站。
1. [!DNL Audience Manager]和協力廠商資料提供者會為訪客指派唯一ID （通常使用Cookie）。
1. [!DNL Audience Manager]會呼叫第三方資料提供者來比對訪客ID。
1. 排程請求（通常為每日間隔）會在[!DNL Audience Manager]和您的第三方資料提供者之間交換訪客區段資料。
1. 每當處理輸入[!UICONTROL Server-to-Server]檔案時，會透過電子郵件將收據傳送給合作夥伴解決方案，若已設定，則傳送給合作夥伴。 如需詳細資訊，請參閱[傳入處理之後傳送給合作夥伴的範例訊息](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md)。
