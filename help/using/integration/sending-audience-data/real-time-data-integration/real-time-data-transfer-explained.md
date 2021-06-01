---
description: 概述Audience Manager如何透過協力廠商內容提供者執行即時資料傳輸。
seo-description: 概述Audience Manager如何透過協力廠商內容提供者執行即時資料傳輸。
seo-title: 描述的即時資料傳輸過程
solution: Audience Manager
title: 描述的即時資料傳輸過程
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: 傳入資料傳輸
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 1%

---


# 描述的即時資料傳輸過程{#real-time-data-transfer-process-described}

概述Audience Manager如何透過協力廠商內容提供者執行即時資料傳輸。

<!-- real-time-data-transfer-explained.xml -->

## 即時資料傳輸

即時資料傳輸會以使用者造訪或在您的網站上採取動作的形式，傳送和接收區段ID。 通常，當您需要讓使用者在詳細目錄中導覽時，立即取得資格或劃分使用者區段時，同步資料傳輸就十分實用。

## 資料整合步驟

即時資料整合程式的運作方式如下：

1. 使用者造訪包含Audience Manager代碼的客戶網站。
1. Audience Manager載入iframe並呼叫[!UICONTROL Data Collection Server]([!DNL DCS])。
1. [!DNL DCS]會呼叫第三方伺服器（即時），以檢查供應商是否擁有有關該用戶的任何區段資訊。
1. 內容提供者會傳回關於該使用者的區段資訊以進行Audience Manager。
1. Audience Manager會收到此區段資訊，並可供定位及建立新特徵和區段。

![](assets/rt_reduce70.png)