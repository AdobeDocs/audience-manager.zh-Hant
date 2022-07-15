---
description: 探索目的地的優勢、類型和用途 – 目的地是要與其共用資料的協力廠商系統，例如廣告伺服器或 DSP。 使用 Destination Builder 來建立和管理 Cookie、URL 或伺服器對伺服器目的地。
keywords: 整合代碼、目標、目標概述、目標、目標、目標、目標、目標、目標、目標、目標、目標、目標、目標、目標、目標、目標、目標、目標、目標、目標
landing-page-description: 探索目的地的優勢、類型和用途 – 目的地是要與其共用資料的協力廠商系統，例如廣告伺服器或 DSP。 使用 Destination Builder 來建立和管理 Cookie、URL 或伺服器對伺服器目的地。
seo-title: Destinations
solution: Audience Manager
title: 目的地
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 865800eb076811db38aec8e98714ad9712804f77
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 15%

---

# [!UICONTROL Destinations] 概述 {#destinations}

在Audience Manager中，a [!UICONTROL destination] 是任何第三方系統(ad伺服器， [!DNL DSP]、ad網路等) 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder] 是用於建立和管理的工具 [!UICONTROL cookie]。 [!DNL URL]或 [!UICONTROL server-to-server destinations]。

## 目的和優勢 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 和 [!UICONTROL Destination Builder] 允許建立 [!UICONTROL destinations] 並向資料夥伴發送有關分段用戶的資訊。 這有助於：

* **Protect資料值：** 而不是將所有用戶資料發送到 [!UICONTROL destination]。 [!UICONTROL Destination Builder] 允許您僅共用有關合格用戶的特定資訊。
* **對您的資料採取操作：** 向 [!UICONTROL destination] 合作夥伴幫助他們快速開發並瞄準合格的受眾群。
* **減少技術開銷：** 業務用戶可以設定 [!UICONTROL destinations] 安全地 [!UICONTROL Destination Builder] 。 這有助於減少部署前測試所需的時間。 與 [!UICONTROL Destination Builder]，建立、管理和刪除 [!UICONTROL destinations] 隨著您的業務需要變化，所有這些都無需經過漫長的開發週期。

## 技術考量 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

資料交付取決於資料合作夥伴希望或能夠接收 [!UICONTROL destination] 的下界。 技術或工程限制可能會阻止 [!UICONTROL destination] 從通過 [!DNL URL]。 [!UICONTROL cookie]或 [!UICONTROL server-to-server] 進程。 與您的第三方合作夥伴合作，以確定他們可以使用哪種方法。

## 業務考量 {#business-considerations}

選擇一種交付方法而不是另一種交付方法的業務決策取決於您的技術能力 [!UICONTROL destination] 合作夥伴和您對合格用戶資訊的處理。 例如，技術約束可以限制選項 [!UICONTROL destination] 無法通過特定傳遞方法接收資料。 但是，如果沒有技術問題，您可以根據您希望如何對該資料執行操作來發送資訊。 例如：

* [!DNL URL]s和 [!UICONTROL cookie-based destinations] 幾乎與頁面上的用戶操作同步工作。
* [!UICONTROL Server-to-server] 方法有助於隨著時間推移構建深入的受眾群體。

## [!UICONTROL Destination] 類型和典型用途 {#destination-types}

下表中的示例可幫助您瞭解何時使用特定 [!UICONTROL destination] 以及每種類型的差異。

| [!UICONTROL Destination] 類型 | 通常在 | 範例 | 考量事項 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 您需要將資料發送到其他Adobe Experience Cloud解決方案。 | 正在向Adobe Analytics發送資料。 |  |
| **[!UICONTROL People-Based Destinations]** | 您需要將受眾段發送到基於人的環境，如Facebook。 | 根據現有客戶的購買歷史記錄向其提供個性化服務 | 通過散列標識符來實現受眾目標。 請參閱 [基於人的目的地](people-based-destinations-overview.md)。 |
| **[!UICONTROL Device-Based Destinations]** (**伺服器到伺服器**) | <ul><li>不需要立即傳輸資料。</li><li>收集資料以構建大量合格用戶的受眾池。</li></ul> | 收集隨時間（小時或天）的資料，以在稍後日期運行的市場活動集中使用它。 | <ul><li>傳輸有關新站點訪問者和以前站點訪問者的資料。 </li><li>訪問者不必再被看到，就能獲得其他分類。</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** 或 **Cookie**) | 您需要立即傳輸資料，以便目標可以立即對合格用戶執行操作。 | 從票證購買站點發送資料。 使用 [!UICONTROL URL] 或 [!UICONTROL cookie destination] 以限定用戶並立即重定目標。 | <ul><li>僅傳輸有關新訪問者的資料。 </li><li>必須再次看到訪問者，才有資格參加該節目。</li></ul> |
