---
description: 訊號是Audience Manager內最小的資訊單位。 它們代表您線上屬性上的使用者互動或使用者活動，並傳遞至Audience Manager以用於特徵規則。
seo-description: 訊號是Audience Manager內最小的資訊單位。 它們代表您線上屬性上的使用者互動或使用者活動，並傳遞至Audience Manager以用於特徵規則。
seo-title: 瞭解訊號
title: 瞭解訊號
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# 瞭解訊號

訊號是Audience Manager內最小的資訊單位。 它們代表您線上屬性上的使用者互動或使用者活動，並傳遞至Audience Manager以用於特徵規則。

[!DNL Audience Manager] 使用機碼值組來表示訊號。例如，下列訊號可能表示訪客已到達包含電子產品的網頁：

* `page = electronics`

[訊號控制面板](../../features/data-explorer/data-explorer-signals-dashboard.md)顯示可用來建立新特徵的多種訊號屬性。 可用信號屬性的詳細檢視如下：

* *索引鍵* 值配對會顯示所接收訊號的索引鍵值 [!DNL Audience Manager]組。
* *信號* 類型描述每個信號的類別。訊號分為下列其中一類：
   * [可操作的記錄檔](/help/using/integration/media-data-integration/actionable-log-files.md):從您的媒體效能日誌檔案接收的即時信號；
   * [!DNL Adobe Analytics]:從您的帳戶接收的即時 [!DNL Adobe Analytics] 信號；
   * 一般線上資料：對象活動產生且不包含在可操作記錄檔和[!DNL Adobe Analytics]中的即時資料；
   * 已上線的記錄：透過批次資料傳輸接收的資料。
* *信* 號源取決於信號類型：
   * 對於已上線的訊號，訊號來源為資料來源名稱。
   * 若是源自[!DNL Adobe Analytics]的訊號，資料來源將一律為報表套裝。
   * 若為可操作的記錄檔和一般線上資料，則不會顯示訊號來源資訊。
* *「* 總計」顯示過去7天內即時訊號 [!DNL Audience Manager] 的接收總次數。
* *特徵中* 會顯示訊號是否屬於任何特徵。按一下箭頭可查看包含對應訊號的特徵。 對於不屬於任何特徵的訊號，欄值會變更為[!UICONTROL Create Onboarded Trait]或[!UICONTROL Create Rule-Based Trait]。

## 信號資料刷新頻率

由於Audience Manager每天處理的資料量很大，[!UICONTROL Data Explorer]會根據信號類型以固定時間間隔刷新顯示的信號資料：

* 每4到6小時會重新整理一次即時訊號資料（可操作的記錄檔、[!DNL Adobe Analytics]資料和一般線上資料）。
* 每24小時會重新整理已上線的訊號資料。

## 相關概念

[訊號、特徵和區段](/help/using/reference/signal-trait-segment.md)
