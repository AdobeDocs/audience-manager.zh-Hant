---
description: 訊號是Audience manager中最小的資訊單位。 它們代表您線上屬性上的使用者互動或使用者活動，並傳遞至Audience Manager以用於特徵規則。
seo-description: 訊號是Audience manager中最小的資訊單位。 它們代表您線上屬性上的使用者互動或使用者活動，並傳遞至Audience Manager以用於特徵規則。
seo-title: 瞭解信號
title: 瞭解信號
uuid: 04a0554e-954e-484a-8838-9161ef416872
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 瞭解信號

訊號是Audience manager中最小的資訊單位。 它們代表您線上屬性上的使用者互動或使用者活動，並傳遞至Audience Manager以用於特徵規則。

[!DNL Audience Manager] 使用鍵值對來表示信號。 例如，下列訊號可能表示訪客已到達包含電子產品的網頁：

* `page = electronics`

「信 [號儀表板](../../features/data-explorer/data-explorer-signals-dashboard.md) 」顯示可用於建立新特徵的多種信號屬性類型。 以下是可用信號屬性的詳細視圖：

* *鍵值對* (Key-value pair)顯示接收到的信號的鍵值對(key-value pair) [!DNL Audience Manager]。
* *信號類型* ，描述每個信號的類別。 信號分為以下類別：
   * [可操作的日誌檔案](/help/using/integration/media-data-integration/actionable-log-files.md):從媒體效能日誌檔案中接收的即時信號；
   * [!DNL Adobe Analytics]:從您的帳戶接收的即時 [!DNL Adobe Analytics] 信號；
   * 一般線上資料：您的觀眾活動產生的即時資料，未包含在可操作的記錄檔中 [!DNL Adobe Analytics];
   * 已登錄記錄：通過批次資料傳輸接收的資料。
* *信號源* (Signal Source)取決於信號類型：
   * 對於已登錄的信號，信號源是資料源名稱。
   * 若是源自的 [!DNL Adobe Analytics]訊號，資料來源將永遠是報表套裝。
   * 對於可操作的日誌檔案和一般的聯機資料，不顯示信號源資訊。
* *「總計* 」會顯示過去7天內即時訊號收 [!DNL Audience Manager] 到的總次數。
* *「特徵」中包含* ，可顯示信號是否屬於任何特徵。 按一下箭頭，查看包含對應訊號的特性。 對於不屬於任何特徵的信號，欄值會變更為 [!UICONTROL Create Onboarded Trait] 或 [!UICONTROL Create Rule-Based Trait]。

## 信號資料刷新頻率

由於Audience manager每日處理的資料量龐大，因此會根據訊號類型 [!UICONTROL Data Explorer] ，以固定的時間間隔重新整理顯示的信號資料：

* 即時訊號資料(可操作的記錄檔、 [!DNL Adobe Analytics] 資料和一般的線上資料)每4到6小時重新整理一次。
* 每24小時更新一次已登入的信號資料。

## 相關概念

[信號、特徵和區段](/help/using/reference/signal-trait-segment.md)