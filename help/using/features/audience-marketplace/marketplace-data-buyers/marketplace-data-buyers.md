---
description: 想要從Audience Manager中購買第三方資料的資料購買者的概述和工作流程
seo-description: 想要從Audience Manager中購買第三方資料的資料購買者的概述和工作流程
seo-title: 適用於資料購買者的 Audience Marketplace
solution: Audience Manager
title: 適用於資料購買者的 Audience Marketplace
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 3%

---


# [!UICONTROL Audience Marketplace] 適用於資料購買者 {#audience-marketplace-for-data-buyers}

想要從內部購買第三方資料的資料購買者的概述和工作流程 [!DNL Audience Manager]。

>[!NOTE]
>[角色型權限](../../../reporting/reports-dashboard.md) ，可控制功能的 [!UICONTROL Audience Marketplace] 存取。
>
>* 管理員可以建立資料饋送、管理訂閱者，以及訂閱資料饋送。
>* 使用者只能搜尋和檢視動態消息。


## The [!UICONTROL Marketplace]: 關於 {#about-marketplace}

此功 [!UICONTROL Marketplace] 能是資 [!DNL Audience Manager] 料購買者的功能，列出您可訂閱的資料饋送。 它會列出固定費率 [!DNL CPM]和私人資料饋送。 這些饋送是由使用資料銷售的協力廠商 [!DNL Audience Manager] 提供。

在中，報 [!UICONTROL Marketplace]告工具可讓您追蹤動態消息的使用情況，以及您與已訂閱資料 [!UICONTROL traits] 動態消息中的重疊情況。 最後，您 [!UICONTROL Audience Marketplace]會 [!DNL Adobe] 處理髮票和費用付款(雖然您訂閱動態消息時必須自行報告使用 [!DNL CPM] 情形)。 這些功能可讓您找到有效的資料來源，而不浪費時間尋找資料供應商。

>[!TIP]
>
>使用 **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)**，尋找可訂閱的高品質資料饋送。 然後，返回使用[!DNL Audience Manager]者介面或使用[Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)，訂閱您找到的動態消息。

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

清 [!UICONTROL Marketplace] 單包含您可排序和搜尋的資訊，以尋找適合您的資料饋送。 採購員清 [!UICONTROL Marketplace] 單中的項目包括：

* **[!UICONTROL Search]**: 依名稱或文字說明尋找資料饋送。
* **[!UICONTROL Similar Traits]**: 顯示資料饋送中 [!UICONTROL traits] 的類似數目。 此列在您在區段中輸入 [!UICONTROL trait] 或 [!UICONTROL segment] 篩選依據後顯 **[!UICONTROL Similarity To]** 示。
* **[!UICONTROL Name]**: 資料饋送的名稱。
* **[!UICONTROL Description]**: 資料饋送內容的相關資訊。
* **[!UICONTROL Provider]**: 資料提供者的名稱。
* **[!UICONTROL Traits]**: 資料饋送 [!UICONTROL traits] 中的數目。
* **[!UICONTROL 30 Day Provider Unique Users]**: 過去30天內檢視的獨特使用者人數。
* **[!UICONTROL 30 Day Overlapped Uniques]**: 您帳戶中與提供者帳戶中的使用者重疊的使用者人數。
* **[!UICONTROL Feed Overlap]**: 30天重疊的獨特值（以百分比顯示），計算為： 資料購買者30天重疊獨特客戶／資料購買者30天獨特客戶)x 100。
* **[!UICONTROL Private Feeds]**: 請參 [閱私人資料饋送](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]**: 您與資料提供者的訂閱數。

 

若要輕鬆找到符合您需求的最佳資料饋送，請使用頁面左側的下列篩選 [!UICONTROL Marketplace] 器：

* **[!UICONTROL Similarity To]**: 根據資料饋送的相似性來篩選 [!UICONTROL trait] 您 [!UICONTROL segment] 選擇的資料饋送。 輸入或區 [!UICONTROL trait] 段以進行比較時，您可以使用或 [!UICONTROL trait][!UICONTROL segment] ID或其各自的名稱。
* **[!UICONTROL Similarity Cutoff]**: 拖曳滑桿以根據資料饋送與您選取或的 [!UICONTROL traits] 相似程度來篩選 [!UICONTROL trait] 資料 [!UICONTROL segment]。 若要進一步瞭解相 [!UICONTROL trait] 似性分數，請參 [閱特徵相似性分數](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: 根據您的訂閱狀態篩選資料饋送。
* **[!UICONTROL Plan Use Case]**: 根據支援的使用案例篩選資料饋送： **[!UICONTROL Activation]**、 **[!UICONTROL Segments and Overlap]**&#x200B;和 **[!UICONTROL Modelling]**。
* **[!UICONTROL Plan Unit]**: 根據資料饋送的定價類型篩選資料饋送。

## 尋找類似項目 [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] 提供您選項，根據 [!UICONTROL traits] 不同資料饋送與現有或區段的相似性，從中 [!UICONTROL traits] 尋找。 以下是如何做到的：

1. 前往 **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**。
2. 使用選 **[!UICONTROL Similarity To]** 擇器，在根據或進行篩選之 [!UICONTROL trait] 間選擇 [!UICONTROL segment]。 您可以根據 [!UICONTROL trait]/[!UICONTROL segment] ID或名稱進行篩選。 搜尋方塊會根據您的輸入自動顯示相關建議。
3. 在您識別要篩選依據的特徵或區段後，在建議清單中按一下它。
4. 若要縮小結果範圍，請使用滑 **[!UICONTROL Similarity Cutoff]** 桿從較不相似的滑桿移 [!UICONTROL traits]動到較相似的滑桿。

篩選完成後，您會在結果頁面中看到新欄： **[!UICONTROL Similar Traits]**. 此欄顯示符合篩選條件 [!UICONTROL traits] 的每個資料饋送中，您篩選依據的相似數目。

若要查看類似特徵的完整清單，請按一下欄中的 **[!UICONTROL Similar Traits]** 數字。

>[!NOTE]
>
> Audience Marketplace會顯示資料饋送中 [!UICONTROL trait] 前500個類似結果。

觀看以下影片，以取得如何尋找類似內容的完整概觀 [!UICONTROL traits]。

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## 私人資料摘要 {#private-data-feeds}

在清單 [!UICONTROL Marketplace] 中，有時提供者的名稱和資料 [!UICONTROL trait] 會標籤為私有。 這表示私人 [資料饋送](../../../features/audience-marketplace/marketplace-private-feeds.md)。 私人資料饋送可讓賣家限制買家存取其資料。 當賣家提供特殊優惠、折扣或隱私權和存取控制對他們很重要時，就可以私下提供餵送。 身為買家，如果您想要存取私人動態消息，您必須傳送訂閱要求給賣方。 如需詳 [細資訊，請參閱訂閱私人資料饋送](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 。

>[!MORELIKETHIS]
>
>* [瞭解 Audience Marketplace 的「方案詳細資訊頁面」](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [資料購買者的折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

