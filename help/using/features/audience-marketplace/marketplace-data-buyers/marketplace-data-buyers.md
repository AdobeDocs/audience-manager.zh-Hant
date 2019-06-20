---
description: 想要從Audience Manager中購買第三方資料的資料購買者的概述和工作流程
seo-description: 想要從Audience Manager中購買第三方資料的資料購買者的概述和工作流程
seo-title: 資料購買者的觀眾市場
solution: Audience Manager
title: 資料購買者的觀眾市場
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128 b540 f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# Audience Marketplace for Data Buyers {#audience-marketplace-for-data-buyers}

Overview and workflow for data buyers who want to purchase third-party data from within [!DNL Audience Manager].

>[!NOTE]
>[角色型權限](../../../reporting/reports-dashboard.md) 可控制 [!UICONTROL Audience Marketplace] 功能的存取權。
>
>* 管理員可以建立資料饋送、管理用戶以及訂閱資料饋送。
>* 使用者只能搜尋和檢視動態消息。


## The Marketplace: About {#about-marketplace}

<!-- c_marketplace_about.xml -->

The [!UICONTROL Marketplace] is an [!DNL Audience Manager] feature for data buyers that lists data feeds you can subscribe to. It lists flat rate, [!DNL CPM], or private data feeds. These feeds are provided by third-party vendors that use [!DNL Audience Manager] to sell data. In the [!UICONTROL Marketplace], reporting tools let you track feed usage and the overlap between your traits and those in a subscribed data feed. Finally, with [!UICONTROL Audience Marketplace], [!DNL Adobe] takes care of invoices and fee payments (though you do have to self-report usage when subscribed to a [!DNL CPM] feed). 這些功能可讓您尋找有效的資料來源，而不浪費時間尋找資料供應商。

>[!TIP]
> 
>Use the **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** to find high quality data feeds that you can subscribe to. Then, go back into the Audience Manager UI or use the [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) to subscribe to the feeds you found.

![](assets/buyer_marketplace.png)

[!UICONTROL Marketplace] 清單中包含您可以排序及搜尋的資訊，以尋找適合您的資料饋送。[!UICONTROL Marketplace] 購買者清單中的項目包括：

* **[!UICONTROL Search]：** 依名稱或文字說明尋找資料饋送。
* **[!UICONTROL Name]：** 資料饋送的名稱。
* **[!UICONTROL Description]：** 資料饋送內容的相關資訊。
* **[!UICONTROL Provider]：** 資料提供者的名稱。
* **[!UICONTROL Traits]：** 資料饋送中的特徵數。
* **[!UICONTROL 30 Day Provider Unique Users]：** 最近30天內所看到的獨特使用者人數。
* **[!UICONTROL 30 Day Overlapped Uniques]：** 帳戶中與提供者帳戶中使用者重疊的使用者人數。
* **[!UICONTROL Feed Overlap]：** 30天重疊獨特值，以百分比顯示，計算方式為：資料購買者30天重疊唯一客戶數/資料購買者30天唯一客戶數x100。
* **[!UICONTROL Private Feeds]：** 請參閱 [私人資料饋送](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]：** 您與資料供應商的訂閱次數。

## 私人資料摘要 {#private-data-feeds}

[!UICONTROL Marketplace] 在清單中，提供者的名稱和特徵資料會標示為私用。This indicates a [private data feed](../../../features/audience-marketplace/marketplace-private-feeds.md). 私人資料饋送可讓賣方限制買家存取其資料。販售者可以在提供特殊交易、折扣或隱私權和存取權控制對他們重要時，將摘要設為私密。身為購買者，如果您想要存取私人摘要，則必須向賣方傳送訂閱要求。See [Subscribe to a Private Data Feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) for details.

>[!MORE_贊_ this]
>
>* [瞭解 Audience Marketplace 的「方案詳細資訊頁面」](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [資料購買者折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

