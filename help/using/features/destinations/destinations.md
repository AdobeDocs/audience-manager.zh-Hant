---
description: 在Audience manager中，目標是任何協力廠商系統（廣告伺服器、DSP和網路等）您想要與其共用資料。 「目標產生器」是您用來建立和管理Cookie、URL或伺服器對伺服器目標的工具。
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: 在Audience manager中，目標是任何協力廠商系統（廣告伺服器、DSP和網路等）您想要與其共用資料。 「目標產生器」是您用來建立和管理Cookie、URL或伺服器對伺服器目標的工具。
seo-title: 目的地
solution: Audience Manager
title: 目的地
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
translation-type: tm+mt
source-git-commit: 431a254f1a70958db29621a59acc6239d2a6b005

---


# Destinations Overview {#destinations}

在Audience Manager中，目標是任何協力廠商系統(廣告伺服 [!DNL DSP]器、廣告網路等)您想要與其共用資料。 [!UICONTROL Destination Builder] 是您用來建立和管理Cookie、伺服器 [!DNL URL]對伺服器目標的工具。

## 用途與優勢 {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 並讓 [!UICONTROL Destination Builder] 您建立目標，並將細分使用者的相關資訊傳送給您的資料合作夥伴。 這有助於：

* **** 保護資料價值：您不必將所有使用者資料傳送至目的地，而 [!UICONTROL Destination Builder] 是只能分享符合資格使用者的特定資訊。
* **** 對您的資料採取行動：將資料傳送至目標合作夥伴，可協助他們快速開發並鎖定合格的受眾細分。
* **** 降低技術開銷：商業使用者可在介面中安全地設定目 [!UICONTROL Destination Builder] 標。 這有助於縮短部署前測試所需的時間。 您可 [!UICONTROL Destination Builder]以隨著業務需求的變更，建立、管理和刪除目標，而不需經過長時間的開發週期。

## 技術考量 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

資料傳送取決於您的資料合作夥伴想要或能夠接收目的地資訊的方式。 技術或工程限制可能會使目標無法透過 [!DNL URL]、Cookie或伺服器對伺服器程式接收資料。 與您的協力廠商合作夥伴合作，以判斷他們可以使用哪種方法。

## 業務考量 {#business-considerations}

選擇一種傳送方法而非另一種傳送方法的業務決策取決於目標合作夥伴的技術能力，以及您想要如何處理合格的使用者資訊。 例如，如果目標無法透過特定傳送方法接收資料，技術限制可限制您的選項。 不過，如果沒有技術問題，您可以根據想要對該資料採取行動的方式傳送資訊。 例如:

* [!DNL URL]s和Cookie型目標與頁面上的使用者動作幾乎同步運作。
* 伺服器對伺服器方法有助於建立長期的深層受眾細分。

## 目標類型和典型用途 {#destination-types}

下表中的範例可協助您瞭解何時使用特定目的地以及每種類型之間的差異。

| 目標類型 | 通常用於 | 範例 | 考量事項 |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | 您需要將資料傳送至其他Adobe Experience cloud解決方案。 | 傳送資料至Adobe Analytics。 |  |
| **[!UICONTROL People-Based Destinations]** | 您需要將觀眾區隔傳送至以人為本的環境，例如Facebook。 | 根據現有客戶的購買記錄，為其提供個人化優惠 | 對象定位是透過雜湊識別碼來完成。 查看 [基於人的目標](people-based-destinations-overview.md) |
| **[!UICONTROL Device-Based Destinations]**(**&#x200B;伺服器對伺服器&#x200B;**) | <ul><li>不需要立即傳輸資料。</li><li>收集資料，以建立龐大的合格使用者群。</li></ul> | 收集一段時間（小時或天）的資料，以便在促銷活動集中使用，以便在稍後日期執行。 | <ul><li>傳輸有關新訪客和舊訪客的資料。 </li><li>訪客不必再被看到，即可符合其他區段的資格。</li></ul> |
| **[!UICONTROL Custom Destinations]**(** URL **或** Cookie **) | 您需要立即傳輸資料，以便目的地能立即對符合資格的使用者採取行動。 | 從票證購買網站傳送資料。 使用URL或Cookie目標來限定使用者，並立即重新定位。 | <ul><li>僅傳輸有關新訪客的資料。 </li><li>必須再次檢視訪客才能符合區段的資格。</li></ul> |

