---
description: 訊號是Audience Manager中最小的資訊單位。 它們代表您線上屬性上的使用者互動或使用者活動，並傳遞至Audience Manager以用於特徵規則。
seo-description: 訊號是Audience Manager中最小的資訊單位。 它們代表您線上屬性上的使用者互動或使用者活動，並傳遞至Audience Manager以用於特徵規則。
seo-title: 瞭解訊號
title: 瞭解訊號
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 2%

---


# 瞭解訊號

訊號是Audience Manager中最小的資訊單位。 它們代表您線上屬性上的使用者互動或使用者活動，並傳遞至Audience Manager以用於特徵規則。

[!DNL Audience Manager] 使用鍵值對來表示信號。例如，下列訊號可能表示訪客已到達包含電子產品的網頁：

* `page = electronics`

[Signals Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md)顯示多種類型的信號屬性，您可用來建立新特徵。 以下是可用信號屬性的詳細視圖：

* *鍵值配* 對顯示由接收的信號的鍵值對 [!DNL Audience Manager]。
* *Signal* type描述每個信號的類別。信號分為以下類別：
   * [可操作的日誌檔案](/help/using/integration/media-data-integration/actionable-log-files.md):從媒體效能日誌檔案中接收的即時信號；
   * [!DNL Adobe Analytics]:從您的賬戶收到的即時 [!DNL Adobe Analytics] 信號；
   * 一般線上資料：由觀眾活動產生且未包含在可操作記錄檔和[!DNL Adobe Analytics]中的即時資料；
   * 已登錄記錄：通過批次資料傳輸接收的資料。
* *信號* 源取決於信號類型：
   * 對於已登錄的信號，信號源是資料源名稱。
   * 對於源自[!DNL Adobe Analytics]的訊號，資料來源永遠是報表套裝。
   * 對於可操作的日誌檔案和一般的聯機資料，不顯示信號源資訊。
* *「總* 計」會顯示過去7天內即時訊號收 [!DNL Audience Manager] 到的總次數。
* *Traits中包* 含的資訊會顯示訊號是否屬於任何特徵。按一下箭頭，查看包含對應訊號的特性。 對於不屬於任何特徵的信號，列值將更改為[!UICONTROL Create Onboarded Trait]或[!UICONTROL Create Rule-Based Trait]。

## 信號資料刷新頻率

由於Audience Manager每日處理的資料量龐大，[!UICONTROL Data Explorer]會根據訊號類型，以固定的時間間隔重新整理顯示的訊號資料：

* 即時信號資料（可操作的記錄檔、[!DNL Adobe Analytics]資料和一般的線上資料）每4到6小時重新整理一次。
* 每24小時更新一次已登入的信號資料。

## 相關概念

[訊號、特徵和區段](/help/using/reference/signal-trait-segment.md)