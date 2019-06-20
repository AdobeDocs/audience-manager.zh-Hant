---
description: 在Audience Manager中，目的地是任何第三方系統(廣告伺服器、DSP、廣告網路等)。您要與其共用資料。「目標產生器」是用來建立和管理Cookie、URL或伺服器至伺服器目的地的工具。
keywords: 整合程式碼，目的地，目的地總覽
seo-description: 在Audience Manager中，目的地是任何第三方系統(廣告伺服器、DSP、廣告網路等)。您要與其共用資料。「目標產生器」是用來建立和管理Cookie、URL或伺服器至伺服器目的地的工具。
seo-title: 目的地
solution: Audience Manager
title: 目的地
uuid: 5c7dbec-f73 f-46fe-46f12-7685e8 d7334 f
translation-type: tm+mt
source-git-commit: 157e70906b80bd0a23ba6e7721d2c456d378ffb5

---


# 目的地 {#destinations}

In Audience Manager, a destination is any third-party system (ad server, [!DNL DSP], ad network, etc.) 您要與其共用資料。[!UICONTROL Destination Builder] 是用來建立和管理Cookie、 [!DNL URL]或伺服器對伺服器目的地的工具。

## Purpose and Advantages {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] 並可 [!UICONTROL Destination Builder] 讓您建立目標，並傳送有關細分使用者的資訊給您的資料合作夥伴。這有助於您：

* **保護資料價值：** 您不能將所有使用者資料傳送至 [!UICONTROL Destination Builder] 目的地，只能分享符合資格使用者的特定資訊。
* **對您的資料採取行動：** 將資料傳送給目的地合作夥伴可協助他們快速開發和鎖定合格受眾細分。
* **降低技術負擔：** 商業使用者可在 [!UICONTROL Destination Builder] 介面中安全地設定目的地。如此可縮短部署前測試所需的時間。With [!UICONTROL Destination Builder], you create, manage, and delete destinations as your business needs change, all without working through a long development cycle.

## 技術考量 {#technical-considerations}

<!-- destination-delivery-methods.xml -->

資料傳送取決於資料合作夥伴想要或可以接收目的地資訊的方式。Technical or engineering constraints may prevent a destination from receiving data via [!DNL URL], cookie, or server-to-server processes. 與第三方合作夥伴合作決定他們可以使用的方法。

## 業務考量 {#business-considerations}

選擇一種傳送方式的商業決策取決於目的地合作夥伴的技術能力，以及您想要使用合格使用者資訊的行為。例如，如果目的地無法依特定傳送方法接收資料，技術限制可以限制您的選項。但是，如果沒有技術問題，您可以根據您對該資料採取行動的方式傳送資訊。例如:

* [!DNL URL]和基於Cookie的目的地幾乎可與頁面上的使用者動作同步運作。
* 伺服器對伺服器方法很適合用來建立深度受眾細分。

## Destination Types and Typical Uses {#destination-types}

下表中的範例可協助您瞭解使用特定目的地的時機以及各類型之間的差異。

| 目的地類型 | 通常用於 | 範例 | 考量事項 |
|--- |--- |--- |--- |
| **URL** 或 **Cookie** | 您需要立即傳輸資料，讓目的地可以立即對合格使用者採取行動。 | 從票證購買網站傳送資料。使用URL或Cookie目的地以符合使用者資格並立即重新定位。 | <ul><li>僅傳輸新訪客的相關資料。 </li><li>必須再次查看訪客以符合區段資格。</li></ul> |
| **伺服器至伺服器** | <ul><li>不需要立即傳送資料。</li><li>收集資料以建立龐大的合格使用者群。</li></ul> | 透過時間(小時或天)收集資料，以便在稍後的促銷活動集中使用。 | <ul><li>傳輸新和舊網站訪客的相關資料。 </li><li>訪客不需要再次查看，才能符合其他區段的資格。</li></ul> |
