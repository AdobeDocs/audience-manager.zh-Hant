---
description: 概述Audience Manager如何與第三方內容供應商執行即時資料傳輸。
seo-description: 概述Audience Manager如何與第三方內容供應商執行即時資料傳輸。
seo-title: 描述即時資料傳輸程序
solution: Audience Manager
title: 描述即時資料傳輸程序
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

概述Audience Manager如何與第三方內容供應商執行即時資料傳輸。

<!-- real-time-data-transfer-explained.xml -->

## 即時資料傳輸

即時資料傳輸會傳送並接收區段ID作為使用者瀏覽或在您的網站上採取動作。通常，同步資料傳輸會在使用者瀏覽您的庫存時立即符合資格，或立即分段。

## 資料整合步驟

即時資料整合程序運作如下：

1. 使用者瀏覽包含Audience Manager代碼的客戶網站。
1. Audience Manager loads an iframe and makes a call to our [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]).
1. The [!UICONTROL DCS] calls the third-party server (in real time) to check if the vendor has any segment information about the user.
1. 內容供應商會將該使用者的區段資訊傳回至Audience Manager。
1. Audience Manager會接收此區段資訊，並讓它可用於定位並建立新特性和區段。

![](assets/rt_reduce70.png)