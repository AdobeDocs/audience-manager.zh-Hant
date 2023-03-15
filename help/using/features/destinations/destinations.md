---
description: 探索目的地的優勢、類型和用途 – 目的地是要與其共用資料的協力廠商系統，例如廣告伺服器或 DSP。 使用 Destination Builder 來建立和管理 Cookie、URL 或伺服器對伺服器目的地。
keywords: 整合代碼，目的地，目的地概觀，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地
landing-page-description: 探索目的地的優勢、類型和用途 – 目的地是要與其共用資料的協力廠商系統，例如廣告伺服器或 DSP。 使用 Destination Builder 來建立和管理 Cookie、URL 或伺服器對伺服器目的地。
short-description: Discover the advantages, types, and uses of destinations – any third-party system, such as an ad server or DSP, where you share data. Use Destination Builder to create and manage cookies, URL, or server-to-server destinations.
seo-title: Destinations
solution: Audience Manager
title: 目的地
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 15%

---

# [!UICONTROL Destinations] 概述 {#destinations}

在Audience Manager中， [!UICONTROL destination] 是任何協力廠商系統(廣告伺服器、 [!DNL DSP]、廣告網路等) 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder] 是您用來建立和管理的工具 [!UICONTROL cookie], [!DNL URL]，或 [!UICONTROL server-to-server destinations].

## 用途與優點 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 和 [!UICONTROL Destination Builder] 可讓您建立 [!UICONTROL destinations] 並將分段使用者的相關資訊傳送給您的資料合作夥伴。 這可協助您：

* **Protect資料值：** 將所有使用者資料傳送至 [!UICONTROL destination], [!UICONTROL Destination Builder] 可讓您僅共用合格使用者的特定資訊。
* **對您的資料採取動作：** 傳送資料至 [!UICONTROL destination] 合作夥伴可協助他們快速開發及鎖定合格的受眾區段。
* **降低技術開銷：** 業務用戶可以設定 [!UICONTROL destinations] 安全地 [!UICONTROL Destination Builder] 介面。 這有助於縮短部署前測試所需的時間。 使用 [!UICONTROL Destination Builder]，您可以建立、管理和刪除 [!UICONTROL destinations] 隨著您的業務需求改變，所有這一切都無需經過漫長的開發週期即可完成。

## 技術考量 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

資料傳送取決於您的資料合作夥伴想要或可以接收 [!UICONTROL destination] 資訊。 技術或工程限制可能會防止 [!UICONTROL destination] 從接收資料 [!DNL URL], [!UICONTROL cookie]，或 [!UICONTROL server-to-server] 程式。 請與您的協力廠商合作夥伴合作，決定他們可使用的方法。

## 業務考量 {#business-considerations}

選擇一種傳送方法而非另一種傳送方法的業務決策，取決於您的 [!UICONTROL destination] 合作夥伴，以及您要對合格使用者資訊執行的操作。 例如，技術限制可限制選項，若 [!UICONTROL destination] 無法透過特定傳送方法接收資料。 不過，如果沒有技術問題，您可以根據對該資料採取動作的方式來傳送資訊。 例如：

* [!DNL URL]s和 [!UICONTROL cookie-based destinations] 與頁面上的使用者動作幾乎同步處理。
* [!UICONTROL Server-to-server] 方法有助於隨著時間建立深層受眾區段。

## [!UICONTROL Destination] 類型和典型使用 {#destination-types}

下表中的範例可協助您了解何時使用特定 [!UICONTROL destination] 以及每種類型之間的差異。

| [!UICONTROL Destination] 類型 | 通常用於 | 範例 | 考量事項 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 您需要將資料傳送至其他Adobe Experience Cloud解決方案。 | 傳送資料至Adobe Analytics。 |  |
| **[!UICONTROL People-Based Destinations]** | 您需要將受眾區段傳送至以人物為基礎的環境，例如Facebook。 | 根據現有客戶的購買記錄，為其提供個人化優惠方案 | 對象鎖定目標是透過雜湊識別碼完成。 請參閱 [以人物為基礎的目的地](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**伺服器對伺服器**) | <ul><li>不需要立即傳輸資料。</li><li>收集資料以建立大量合格使用者受眾池。</li></ul> | 收集一段時間（小時或天）的資料，以便在行銷活動集中使用，以便日後執行。 | <ul><li>傳輸新訪客和先前網站訪客的相關資料。 </li><li>訪客不需要再被看到才能符合其他區段。</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** 或 **Cookie**) | 您需要立即傳輸資料，讓目的地能立即對合格使用者採取行動。 | 從票證購買網站傳送資料。 使用 [!UICONTROL URL] 或 [!UICONTROL cookie destination] 來授與使用者的資格，並立即重新鎖定目標。 | <ul><li>僅傳輸有關新訪客的資料。 </li><li>訪客必須再次被看到才能符合區段資格。</li></ul> |
