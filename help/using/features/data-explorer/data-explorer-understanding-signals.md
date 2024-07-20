---
description: 訊號是Audience Manager中最小的資訊單位。 這類值代表使用者在您線上屬性上的互動或使用者活動，並會傳遞給Audience Manager以用於特徵規則。
seo-description: Signals are the smallest unit of information within Audience Manager. They represent user interactions or user activity on your online properties, and get passed on to Audience Manager to be used in trait rules.
seo-title: Understanding Signals
title: 瞭解訊號
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# 瞭解訊號

訊號是Audience Manager中最小的資訊單位。 這類值代表使用者在您線上屬性上的互動或使用者活動，並會傳遞給Audience Manager以用於特徵規則。

[!DNL Audience Manager]使用機碼值組來表示訊號。 例如，下列訊號可能表示訪客已到達包含電子產品的網頁：

* `page = electronics`

[訊號控制面板](../../features/data-explorer/data-explorer-signals-dashboard.md)會顯示多種可用來建立新特徵的訊號屬性。 以下是可用訊號屬性的詳細檢視：

* *機碼值組*&#x200B;顯示[!DNL Audience Manager]所接收訊號的機碼值組。
* *訊號型別*&#x200B;說明每個訊號的類別。 訊號屬於下列類別之一：
   * [可操作的記錄檔](/help/using/integration/media-data-integration/actionable-log-files.md)：從您的媒體效能記錄檔接收的即時訊號；
   * [!DNL Adobe Analytics]：從您的[!DNL Adobe Analytics]帳戶收到的即時訊號；
   * 一般線上資料：由您的對象活動產生的即時資料，不包含在可操作的記錄檔和[!DNL Adobe Analytics]中；
   * 上線記錄：透過批次資料傳輸收到的資料。
* *訊號Source*&#x200B;取決於訊號型別：
   * 對於已上線的訊號，訊號來源是資料來源名稱。
   * 對於來自[!DNL Adobe Analytics]的訊號，資料來源將一律是報表套裝。
   * 對於可操作的記錄檔和一般線上資料，不會顯示任何訊號來源資訊。
* *總計數*&#x200B;顯示[!DNL Audience Manager]在過去7天內接收即時訊號的總次數。
* *包含在特徵中*&#x200B;會顯示訊號是否屬於任何特徵的一部分。 按一下箭頭可檢視包含對應訊號的特徵。 對於不屬於任何特徵的訊號，欄值會變更為[!UICONTROL Create Onboarded Trait]或[!UICONTROL Create Rule-Based Trait]。

## 訊號資料重新整理頻率

由於Audience Manager每天處理的大量資料，[!UICONTROL Data Explorer]會根據訊號型別，以固定時間間隔重新整理顯示的訊號資料：

* 即時訊號資料（可操作的記錄檔、[!DNL Adobe Analytics]資料，以及一般線上資料）每4到6小時會重新整理一次。
* 已上線的訊號資料每24小時會重新整理一次。

## 相關概念

[訊號、特徵和區段](/help/using/reference/signal-trait-segment.md)
