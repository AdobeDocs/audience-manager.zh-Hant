---
description: 在 Audience Manager 中，目的地是您想要與其共用資料的任何協力廠商系統 (廣告伺服器、DSP 和廣告網路等)任何其他系統 (廣告伺服器、DSP、廣告網路等)。目的地產生器是您用來建立和管理 Cookie、URL 或伺服器對伺服器目的地的工具。
keywords: 整合程式碼，目標，目標概觀，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標，目標
landing-page-description: 目的地是要與其共用資料的協力廠商系統，例如廣告伺服器或 DSP。使用 Destination Builder 來建立和管理 Cookie、URL 或伺服器對伺服器目的地。
seo-title: 目的地
solution: Audience Manager
title: 目的地
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: 目標基礎
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
translation-type: tm+mt
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 15%

---

# [!UICONTROL Destinations] 概述 {#destinations}

在Audience Manager中，[!UICONTROL destination]是任何第三方系統（廣告伺服器、[!DNL DSP]廣告網路等） 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder] 是您用來建立和管理、 [!UICONTROL cookie]或 [!DNL URL]的工 [!UICONTROL server-to-server destinations]具

## 用途和優勢{#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 並可 [!UICONTROL Destination Builder] 讓您建立 [!UICONTROL destinations] 細分使用者的相關資訊，並傳送給您的資料合作夥伴。這有助於：

* **Protect資料值：** 您不必將所有使用者資料傳送至某個 [!UICONTROL destination], [!UICONTROL Destination Builder] 而只能分享合格使用者的特定資訊。
* **對您的資料採取行動：將資** 料傳送至合作夥伴 [!UICONTROL destination] 可協助他們快速開發並鎖定合格的受眾細分。
* **降低技術開銷：** 商業使用者可在介面 [!UICONTROL destinations] 中安全設 [!UICONTROL Destination Builder] 定。這有助於縮短部署前測試所需的時間。 使用[!UICONTROL Destination Builder]，您可以隨著業務需求的變更，建立、管理和刪除[!UICONTROL destinations]，而不需長時間的開發週期。

## 技術考量 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

資料傳送取決於您的資料合作夥伴想要或能夠接收[!UICONTROL destination]資訊的方式。 技術或工程限制可能會阻止[!UICONTROL destination]通過[!DNL URL]、[!UICONTROL cookie]或[!UICONTROL server-to-server]進程接收資料。 與您的協力廠商合作夥伴合作，以判斷他們可以使用哪種方法。

## 業務考量 {#business-considerations}

選擇一種傳送方法而非另一種傳送方法的商業決策取決於[!UICONTROL destination]合作夥伴的技術能力以及您想要如何處理合格的使用者資訊。 例如，技術限制可限制您的選項（如果[!UICONTROL destination]無法透過特定傳送方法接收資料）。 不過，如果沒有技術問題，您可以根據想要對該資料採取行動的方式傳送資訊。 例如：

* [!DNL URL]與頁面上 [!UICONTROL cookie-based destinations] 的使用者動作幾乎同步運作。
* [!UICONTROL Server-to-server] 方法有助於建立長期的深層受眾細分。

## [!UICONTROL Destination] 類型和典型用途  {#destination-types}

下表中的範例可協助您瞭解何時使用特定[!UICONTROL destination]以及每種類型之間的差異。

| [!UICONTROL Destination] 類型 | 通常用於 | 範例 | 考量事項 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 您需要將資料傳送至其他Adobe Experience Cloud解決方案。 | 傳送資料至Adobe Analytics。 |  |
| **[!UICONTROL People-Based Destinations]** | 您需要將受眾細分傳送至以人為本的環境，例如Facebook。 | 根據現有客戶的購買記錄，為其提供個人化優惠 | 對象定位是透過雜湊識別碼來完成。 請參閱[以人為本的目標](people-based-destinations-overview.md)。 |
| **[!UICONTROL Device-Based Destinations]** (**伺服器對伺服器**) | <ul><li>不需要立即傳輸資料。</li><li>收集資料，以建立龐大的合格使用者群。</li></ul> | 收集一段時間（小時或天）的資料，以便在促銷活動集中使用，以便在稍後日期執行。 | <ul><li>傳輸有關新訪客和舊訪客的資料。 </li><li>訪客不必再被看到，即可符合其他區段的資格。</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URL或 **Cookie**) | 您需要立即傳輸資料，以便目的地能立即對符合資格的使用者採取行動。 | 從票證購買網站傳送資料。 使用[!UICONTROL URL]或[!UICONTROL cookie destination]來限定使用者，並立即重新定位。 | <ul><li>僅傳輸有關新訪客的資料。 </li><li>必須再次檢視訪客才能符合區段的資格。</li></ul> |
