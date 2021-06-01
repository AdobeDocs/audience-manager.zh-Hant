---
description: 想要從Audience Manager內購買協力廠商資料的資料購買者的概述和工作流程
seo-description: 想要從Audience Manager內購買協力廠商資料的資料購買者的概述和工作流程
seo-title: 適用於資料購買者的 Audience Marketplace
solution: Audience Manager
title: 適用於資料購買者的 Audience Marketplace
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: 訪客交易市場
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 3%

---

# [!UICONTROL Audience Marketplace] 適用於資料購買者  {#audience-marketplace-for-data-buyers}

想要從[!DNL Audience Manager]內購買第三方資料的資料購買者的概述和工作流程。

>[!NOTE]
>[角色型權限](../../../reporting/reports-dashboard.md)控制[!UICONTROL Audience Marketplace]功能的存取。
>
>* 管理員可以建立資料摘要、管理訂閱者及訂閱資料摘要。
>* 使用者只能搜尋和檢視摘要。


## [!UICONTROL Marketplace]:關於{#about-marketplace}

[!UICONTROL Marketplace]是資料購買者的[!DNL Audience Manager]功能，列出您可訂閱的資料摘要。 它列出固定速率、[!DNL CPM]和私人資料饋送。 這些摘要是由使用[!DNL Audience Manager]來銷售資料的第三方廠商提供。

在[!UICONTROL Marketplace]中，報表工具可讓您追蹤摘要使用情況，以及[!UICONTROL traits]與訂閱資料摘要中的使用情況和重疊。 最後，使用[!UICONTROL Audience Marketplace]時， [!DNL Adobe]會處理髮票和費用支付（雖然訂閱[!DNL CPM]摘要時您確實必須自行報告使用情況）。 這些功能可讓您找出有效的資料來源，而不浪費尋找資料提供者的時間。

>[!TIP]
>
>使用&#x200B;**[AdobeAudience Finder](https://www.adobe-audience-finder.com/)**&#x200B;尋找可訂閱的高品質資料摘要。 接著，返回[!DNL Audience Manager]使用者介面，或使用[Audience Marketplace購買者API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)訂閱您找到的摘要。

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

[!UICONTROL Marketplace]清單包含可排序和搜尋以尋找適合您的資料摘要的資訊。 [!UICONTROL Marketplace]採購員清單中的項目包括：

* **[!UICONTROL Search]**:依名稱或文字說明尋找資料摘要。
* **[!UICONTROL Similar Traits]**:顯示資料摘要中 [!UICONTROL traits] 的類似數量。在&#x200B;**[!UICONTROL Similarity To]**&#x200B;區段中輸入[!UICONTROL trait]或[!UICONTROL segment]以篩選依據後，會顯示此欄。
* **[!UICONTROL Name]**:資料摘要的名稱。
* **[!UICONTROL Description]**:資料摘要內容的相關資訊。
* **[!UICONTROL Provider]**:資料提供程式的名稱。
* **[!UICONTROL Traits]**:資料摘 [!UICONTROL traits] 要中的數量。
* **[!UICONTROL 30 Day Provider Unique Users]**:過去30天內不重複檢視的使用者人數。
* **[!UICONTROL 30 Day Overlapped Uniques]**:您帳戶中與提供者帳戶中的使用者重疊的使用者人數。
* **[!UICONTROL Feed Overlap]**:30天重疊的唯一客戶值（以百分比顯示），計算方式為：資料購買者30天重疊唯一客戶/資料購買者30天唯一客戶)x 100。
* **[!UICONTROL Private Feeds]**:請參 [閱私人資料摘要](../../../features/audience-marketplace/marketplace-private-feeds.md)。
* **[!UICONTROL Currently Subscribed Plan Count]**:您擁有資料提供者的訂閱數。

 

若要輕鬆找到符合您需求的最佳資料摘要，請使用[!UICONTROL Marketplace]頁面左側可用的下列篩選器：

* **[!UICONTROL Similarity To]**:根據資料摘要與或您選擇之 [!UICONTROL trait] 的 [!UICONTROL segment] 相似度來篩選。輸入[!UICONTROL trait]或區段進行比較時，可以使用[!UICONTROL trait]或[!UICONTROL segment] ID或其各自的名稱。
* **[!UICONTROL Similarity Cutoff]**:拖曳滑桿以根據資料摘要與您選取或的 [!UICONTROL traits] 相似程度來篩 [!UICONTROL trait] 選資 [!UICONTROL segment]料摘要。若要深入了解[!UICONTROL trait]相似度分數，請參閱[特徵相似度分數](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**:根據您的訂閱狀態篩選資料摘要。
* **[!UICONTROL Plan Use Case]**:根據資料摘要的支援使用案例篩選資料摘要： **[!UICONTROL Activation]**、  **[!UICONTROL Segments and Overlap]**&#x200B;和 **[!UICONTROL Modelling]**。
* **[!UICONTROL Plan Unit]**:根據其定價類型篩選資料摘要。

## 查找類似的[!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] 可讓您根據與現有 [!UICONTROL traits] 或區段的相似度，從各種資料摘要中 [!UICONTROL traits] 尋找。以下是操作方法：

1. 前往&#x200B;**[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**。
2. 使用&#x200B;**[!UICONTROL Similarity To]**&#x200B;選擇器，在基於[!UICONTROL trait]或[!UICONTROL segment]的篩選之間進行選擇。 您可以根據[!UICONTROL trait]/[!UICONTROL segment] ID或名稱進行篩選。 搜尋方塊會根據您的輸入自動顯示相關建議。
3. 識別您要篩選依據的特徵或區段後，請在建議清單中按一下該特徵或區段。
4. 若要縮小結果範圍，請使用&#x200B;**[!UICONTROL Similarity Cutoff]**&#x200B;滑桿，從較不相似的[!UICONTROL traits]移至較相似的。

篩選完成後，您會在結果頁面中看到新欄：**[!UICONTROL Similar Traits]**。 此欄會顯示符合篩選准則之每個資料摘要中，與您篩選依據之類似[!UICONTROL traits]的數量。

若要查看類似特徵的完整清單，請按一下&#x200B;**[!UICONTROL Similar Traits]**&#x200B;欄中的數字。

>[!NOTE]
>
> Audience Marketplace顯示前500個類似[!UICONTROL trait]結果，來自於所有資料摘要。

請觀看以下影片以取得如何尋找類似[!UICONTROL traits]的完整概述。

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## 私人資料摘要 {#private-data-feeds}

在[!UICONTROL Marketplace]清單中，有時提供者的名稱和[!UICONTROL trait]資料會標示為私人。 這表示[私人資料饋送](../../../features/audience-marketplace/marketplace-private-feeds.md)。 私人資料摘要可讓銷售者限制購買者存取其資料的權限。 當賣家提供特別優惠、折扣，或是當隱私和存取控制對他們很重要時，他們可以將摘要設為私人。 身為購買者，如果您想要存取私人摘要，必須傳送訂閱請求給賣方。 如需詳細資訊，請參閱[訂閱私人資料摘要](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 。

>[!MORELIKETHIS]
>
>* [瞭解 Audience Marketplace 的「方案詳細資訊頁面」](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
* [資料購買者的折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

