---
description: 信號是Audience Manager內最小的資訊單位。 它們表示您的線上屬性上的用戶交互或用戶活動，並傳遞給Audience Manager以用於特性規則。
seo-description: Signals are the smallest unit of information within Audience Manager. They represent user interactions or user activity on your online properties, and get passed on to Audience Manager to be used in trait rules.
seo-title: Understanding Signals
title: 瞭解訊號
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 2%

---

# 瞭解訊號

信號是Audience Manager內最小的資訊單位。 它們表示您的線上屬性上的用戶交互或用戶活動，並傳遞給Audience Manager以用於特性規則。

[!DNL Audience Manager] 使用鍵值對來表示信號。 例如，以下信號可能表示訪問者已訪問包含電子產品的網頁：

* `page = electronics`

的 [信號儀表板](../../features/data-explorer/data-explorer-signals-dashboard.md) 顯示了多種類型的信號屬性，可用於建立新特徵。 下面是可用信號屬性的詳細視圖：

* *鍵值對* 向您顯示由 [!DNL Audience Manager]。
* *信號類型* 描述了每個信號的類別。 信號分為以下類別之一：
   * [可操作的日誌檔案](/help/using/integration/media-data-integration/actionable-log-files.md):從媒體效能日誌檔案接收的即時信號；
   * [!DNL Adobe Analytics]:從您的 [!DNL Adobe Analytics] 賬戶；
   * 常規聯機資料：由受眾活動生成且不包含在可操作日誌檔案和 [!DNL Adobe Analytics];
   * 登機記錄：通過批處理資料傳輸接收的資料。
* *信號源* 取決於信號類型：
   * 對於已裝載的信號，信號源是資料源名稱。
   * 對於來自 [!DNL Adobe Analytics]，資料源將始終是報告套件。
   * 對於可操作的日誌檔案和常規聯機資料，不顯示信號源資訊。
* *總計數* 顯示接收即時信號的總次數 [!DNL Audience Manager] 過去七天裡。
* *包含在特徵中* 顯示信號是否是任何特性的一部分。 按一下箭頭查看包含相應信號的特徵。 對於不屬於任何特性的信號，列值將更改為 [!UICONTROL Create Onboarded Trait] 或 [!UICONTROL Create Rule-Based Trait]。

## 信號資料刷新頻率

由於Audience Manager每天處理的資料量很大， [!UICONTROL Data Explorer] 根據信號類型，以固定時間間隔刷新顯示的信號資料：

* 即時信號資料(可操作的日誌檔案， [!DNL Adobe Analytics] 資料和一般線上資料)每4到6小時刷新一次。
* 每24小時更新一次登機信號資料。

## 相關概念

[訊號、特徵和區段](/help/using/reference/signal-trait-segment.md)
