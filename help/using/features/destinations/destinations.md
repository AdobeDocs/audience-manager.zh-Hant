---
description: 探索目的地的優勢、類型和用途 – 目的地是要與其共用資料的第三方系統，例如廣告伺服器或 DSP。使用 Destination Builder 來建立和管理 Cookie、URL 或伺服器對伺服器目的地。
keywords: 整合代碼，目的地，目的地概觀，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地，目的地
landing-page-description: 探索目的地的優勢、類型和用途 – 目的地是要與其共用資料的第三方系統，例如廣告伺服器或 DSP。使用 Destination Builder 來建立和管理 Cookie、URL 或伺服器對伺服器目的地。
short-description: 探索目的地的優勢、類型和用途 – 目的地是要與其共用資料的第三方系統，例如廣告伺服器或 DSP。使用 Destination Builder 來建立和管理 Cookie、URL 或伺服器對伺服器目的地。
seo-title: Destinations
solution: Audience Manager
title: 目的地
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 19%

---

# [!UICONTROL Destinations]總覽 {#destinations}

在Audience Manager中，[!UICONTROL destination]是您想要與其共用資料的任何協力廠商系統（廣告伺服器、[!DNL DSP]、廣告網路等）。 [!UICONTROL Destination Builder]是您用來建立和管理[!UICONTROL cookie]、[!DNL URL]或[!UICONTROL server-to-server destinations]的工具。

## 用途與優點 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations]和[!UICONTROL Destination Builder]可讓您建立[!UICONTROL destinations]，並將分段使用者的相關資訊傳送給您的資料合作夥伴。 這可協助您：

* **保護資料值：**&#x200B;不是將所有使用者資料傳送給[!UICONTROL destination]，[!UICONTROL Destination Builder]僅可讓您共用合格使用者的特定資訊。
* **對您的資料採取行動：**&#x200B;傳送資料給[!UICONTROL destination]合作夥伴可協助他們快速開發及鎖定合格的對象區段。
* **減少技術負荷：**&#x200B;商務使用者可以在[!UICONTROL destinations]介面中安全地設定[!UICONTROL Destination Builder]。 這有助於減少部署前測試所需的時間。 透過[!UICONTROL Destination Builder]，您可在您的業務需求變更時建立、管理和刪除[!UICONTROL destinations]，無需經過漫長的開發週期。

## 技術考量 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

資料傳送取決於您的資料合作夥伴想要或可以接收[!UICONTROL destination]資訊的方式。 技術或工程限制可能會阻止[!UICONTROL destination]透過[!DNL URL]、[!UICONTROL cookie]或[!UICONTROL server-to-server]處理序接收資料。 請與您的第三方合作夥伴合作，決定他們可以使用的方法。

## 業務考量 {#business-considerations}

選擇一種傳遞方式而非另一種傳遞方式的商業決策，取決於您[!UICONTROL destination]合作夥伴的技術能力，以及您想要如何處理合格的使用者資訊。 例如，如果[!UICONTROL destination]無法透過特定傳遞方式接收資料，則技術限制可限制您的選項。 不過，如果沒有技術問題，您可以根據要如何對該資料採取行動來傳送資訊。 例如：

* [!DNL URL]和[!UICONTROL cookie-based destinations]幾乎與頁面上的使用者動作同步運作。
* [!UICONTROL Server-to-server]方法適合用於隨著時間建立深層受眾區段。

## [!UICONTROL Destination]型別和一般使用 {#destination-types}

下表中的範例可協助您瞭解何時使用特定[!UICONTROL destination]以及每個型別之間的差異。

| [!UICONTROL Destination]型別 | 通常用於 | 範例 | 考量事項 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 您必須傳送資料給其他Adobe Experience Cloud解決方案。 | 正在傳送資料至Adobe Analytics。 |  |
| **[!UICONTROL People-Based Destinations]** | 您需要將受眾區段傳送至以人物為基礎的環境，例如Facebook。 | 根據現有客戶的購買記錄，為其提供個人化優惠方案 | 對象鎖定目標會透過雜湊識別碼完成。 請參閱[以人物為基礎的目的地](people-based-destinations-overview.md)。 |
| **[!UICONTROL Device-Based Destinations]** （**伺服器對伺服器**） | <ul><li>不需要立即傳輸資料。</li><li>收集資料以建立大型合格使用者受眾集區。</li></ul> | 隨著時間（小時或天）收集資料，以便用於設定在稍後日期執行的行銷活動。 | <ul><li>傳輸新的和先前的網站訪客資料。 </li><li>訪客不需要再次出現，即可符合其他區段的資格。</li></ul> |
| **[!UICONTROL Custom Destinations]** （**URL**&#x200B;或&#x200B;**Cookie**） | 您必須立即傳輸資料，目的地才能立即對合格使用者採取行動。 | 從票證購買網站傳送資料。 使用[!UICONTROL URL]或[!UICONTROL cookie destination]來授與使用者資格，並立即重新鎖定目標。 | <ul><li>僅傳輸新訪客的相關資料。 </li><li>訪客必須再次出現，才符合區段的資格。</li></ul> |
