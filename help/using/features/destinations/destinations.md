---
description: 在 Audience Manager 中，目的地是您想要與其共用資料的任何協力廠商系統 (廣告伺服器、DSP 和廣告網路等)任何其他系統 (廣告伺服器、DSP、廣告網路等)。目的地產生器是您用來建立和管理 Cookie、URL 或伺服器對伺服器目的地的工具。
keywords: 整合代碼，目的地，目的地概觀，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地
landing-page-description: 目的地是要與其共用資料的協力廠商系統，例如廣告伺服器或 DSP。使用 Destination Builder 來建立和管理 Cookie、URL 或伺服器對伺服器目的地。
seo-title: 目的地
solution: Audience Manager
title: 目的地
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: 目的地基本知識
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 15%

---

# [!UICONTROL Destinations] 概述 {#destinations}

在Audience Manager中，[!UICONTROL destination]是任何協力廠商系統（廣告伺服器、[!DNL DSP]、廣告網路等） 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder] 是您用來建立和管理、 [!UICONTROL cookie]或 [!DNL URL]的工 [!UICONTROL server-to-server destinations]具。

## 用途與優點 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 並可 [!UICONTROL Destination Builder] 讓您建立分 [!UICONTROL destinations] 段使用者的相關資訊，並傳送給您的資料合作夥伴。這可協助您：

* **Protect資料值：** 與其將所有使用者資料傳送至， [!UICONTROL destination]不 [!UICONTROL Destination Builder] 如讓您僅共用合格使用者的特定資訊。
* **對您的資料採取行動：** 傳送資料給合作 [!UICONTROL destination] 夥伴可協助他們快速開發及鎖定合格的受眾區段。
* **降低技術開銷：** 商務使用者可在介 [!UICONTROL destinations] 面中安全地 [!UICONTROL Destination Builder] 設定。這有助於縮短部署前測試所需的時間。 使用[!UICONTROL Destination Builder]，您可以隨著業務需求的變化建立、管理和刪除[!UICONTROL destinations]，而所有這一切都無需經過漫長的開發週期。

## 技術考量 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

資料傳送取決於您的資料合作夥伴希望或能夠如何接收[!UICONTROL destination]資訊。 技術或工程限制可能會阻止[!UICONTROL destination]通過[!DNL URL]、[!UICONTROL cookie]或[!UICONTROL server-to-server]進程接收資料。 請與您的協力廠商合作夥伴合作，決定他們可使用的方法。

## 業務考量 {#business-considerations}

選擇一種傳送方法而選擇另一種傳送方法的業務決策取決於[!UICONTROL destination]合作夥伴的技術能力，以及您要對合格的用戶資訊執行什麼操作。 例如，如果[!UICONTROL destination]無法透過特定傳送方法接收資料，技術限制可能會限制選項。 不過，如果沒有技術問題，您可以根據對該資料採取動作的方式來傳送資訊。 例如：

* [!DNL URL]和與在 [!UICONTROL cookie-based destinations] 頁面上的使用者動作幾乎同步運作。
* [!UICONTROL Server-to-server] 方法有助於隨著時間建立深層受眾區段。

## [!UICONTROL Destination] 類型和典型使用  {#destination-types}

下表中的範例可協助您了解何時使用特定[!UICONTROL destination]以及每種類型之間的差異。

| [!UICONTROL Destination] 類型 | 通常用於 | 範例 | 考量事項 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 您需要將資料傳送至其他Adobe Experience Cloud解決方案。 | 傳送資料至Adobe Analytics。 |  |
| **[!UICONTROL People-Based Destinations]** | 您需要將受眾區段傳送至以人物為基礎的環境，例如Facebook。 | 根據現有客戶的購買記錄，為其提供個人化優惠方案 | 對象鎖定目標是透過雜湊識別碼完成。 請參閱[以人物為基礎的目的地](people-based-destinations-overview.md)。 |
| **[!UICONTROL Device-Based Destinations]** (**伺服器對伺服器**) | <ul><li>不需要立即傳輸資料。</li><li>收集資料以建立大量合格使用者受眾池。</li></ul> | 收集一段時間（小時或天）的資料，以便在行銷活動集中使用，以便日後執行。 | <ul><li>傳輸新訪客和先前網站訪客的相關資料。 </li><li>訪客不需要再被看到才能符合其他區段。</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URL或 **Cookie**) | 您需要立即傳輸資料，讓目的地能立即對合格使用者採取行動。 | 從票證購買網站傳送資料。 使用[!UICONTROL URL]或[!UICONTROL cookie destination]來限定用戶並立即重新定位。 | <ul><li>僅傳輸有關新訪客的資料。 </li><li>訪客必須再次被看到才能符合區段資格。</li></ul> |
