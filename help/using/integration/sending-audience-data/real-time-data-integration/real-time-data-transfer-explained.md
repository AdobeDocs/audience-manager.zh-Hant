---
description: 概述Audience Manager如何與第三方內容供應商執行即時資料傳輸。
seo-description: 概述Audience Manager如何與第三方內容供應商執行即時資料傳輸。
seo-title: 描述的即時資料傳輸過程
solution: Audience Manager
title: 描述的即時資料傳輸過程
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

概述Audience Manager如何與第三方內容供應商執行即時資料傳輸。

<!-- real-time-data-transfer-explained.xml -->

## 即時資料傳輸

即時資料傳輸會以使用者造訪或在您的網站上採取動作的方式傳送和接收區段ID。 通常，同步資料傳輸在您需要立即取得使用者資格或劃分使用者瀏覽庫存時非常有用。

## 資料整合步驟

即時資料整合程式的運作方式如下：

1. 使用者瀏覽包含Audience Manager代碼的客戶網站。
1. Audience Manager會載入iframe，並呼叫我們 [!UICONTROL Data Collection Server] 的( [!DNL DCS])。
1. 此 [!DNL DCS] 時會呼叫協力廠商伺服器（即時），以檢查廠商是否有使用者的區段資訊。
1. 內容提供者會將有關該使用者的區段資訊傳回至Audience Manager。
1. Audience Manager會接收此區段資訊，並可用於定位和建立新特徵和區段。

![](assets/rt_reduce70.png)