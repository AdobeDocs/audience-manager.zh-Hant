---
description: 想要從Audience manager中購買第三方資料的資料購買者的概述和工作流程
seo-description: 想要從Audience manager中購買第三方資料的資料購買者的概述和工作流程
seo-title: ' 適用於資料購買者的Audience Marketplace'
solution: Audience Manager
title: ' 適用於資料購買者的Audience Marketplace'
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# 適用於資料購買者的Audience Marketplace {#audience-marketplace-for-data-buyers}

想要從內部購買第三方資料的資料購買者的概述和工作流程 [!DNL Audience Manager]。

>[!NOTE]
>[角色型權限](../../../reporting/reports-dashboard.md) ，可控制功能的 [!UICONTROL Audience Marketplace] 存取。
>
>* 管理員可以建立資料饋送、管理訂閱者，以及訂閱資料饋送。
>* 使用者只能搜尋和檢視動態消息。


## 市集：關於 {#about-marketplace}

<!-- c_marketplace_about.xml -->

此功 [!UICONTROL Marketplace] 能是資 [!DNL Audience Manager] 料購買者的功能，列出您可訂閱的資料饋送。 它會列出固定費率 [!DNL CPM]或私人資料饋送。 這些饋送是由使用資料銷售的協力廠商 [!DNL Audience Manager] 提供。 在中，報 [!UICONTROL Marketplace]告工具可讓您追蹤動態消息的使用情況，以及特徵與已訂閱資料動態消息中的特徵之間的重疊。 最後，您 [!UICONTROL Audience Marketplace]會 [!DNL Adobe] 處理髮票和費用付款(雖然您訂閱動態消息時必須自行報告使用 [!DNL CPM] 情形)。 這些功能可讓您找到有效的資料來源，而不浪費時間尋找資料供應商。

>[!TIP]
> 
>使用 **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** ，尋找可訂閱的高品質資料饋送。 然後，返回Audience Manager UI或使用 [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) ，訂閱您找到的動態消息。

![](assets/buyer_marketplace.png)

清 [!UICONTROL Marketplace] 單包含您可排序和搜尋的資訊，以尋找適合您的資料饋送。 採購員清 [!UICONTROL Marketplace] 單中的項目包括：

* **[!UICONTROL Search]** :依名稱或文字說明尋找資料饋送。
* **[!UICONTROL Name]** :資料饋送的名稱。
* **[!UICONTROL Description]** :資料饋送內容的相關資訊。
* **[!UICONTROL Provider]** :資料提供者的名稱。
* **[!UICONTROL Traits]** :資料饋送中的特徵數。
* **[!UICONTROL 30 Day Provider Unique Users]** :過去30天內檢視的獨特使用者人數。
* **[!UICONTROL 30 Day Overlapped Uniques]** :您帳戶中與提供者帳戶中的使用者重疊的使用者人數。
* **[!UICONTROL Feed Overlap]** :30天重疊的獨特值（以百分比顯示），計算為：資料購買者30天重疊獨特客戶／資料購買者30天獨特客戶)x 100。
* **[!UICONTROL Private Feeds]** :請參 [閱私人資料饋送](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]** :您與資料提供者的訂閱數。

## 私人資料摘要 {#private-data-feeds}

在清單 [!UICONTROL Marketplace] 中，有時提供者的名稱和特徵資料會標示為私人。 這表示私人 [資料饋送](../../../features/audience-marketplace/marketplace-private-feeds.md)。 私人資料饋送可讓賣家限制買家存取其資料。 當賣家提供特殊優惠、折扣或隱私權和存取控制對他們很重要時，就可以私下提供餵送。 身為買家，如果您想要存取私人動態消息，您必須傳送訂閱要求給賣方。 如需詳 [細資訊，請參閱訂閱私人資料饋送](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 。

>[!MORE_LIKE_THIS]
>
>* [瞭解 Audience Marketplace 的「方案詳細資訊頁面」](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [資料購買者的折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

