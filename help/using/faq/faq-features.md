---
description: 常見產品與功能相關問題與問題。
keywords: 觀眾管理員Cookie
seo-description: 常見產品與功能相關問題與問題。
seo-title: 產品功能與功能常見問題解答
solution: Audience Manager
title: 產品功能與功能常見問題解答
uuid: da5f5089-24a8-4455-88a6-eb62 d83939 d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Product Features and Functions FAQ{#product-features-and-functions-faq}

常見產品與功能相關問題與問題。

<br> 

<!-- 

faq_features_functions.xml

 -->

**甚麼是我的組織ID，我要如何找到它？**

The *`Organization ID`* is a unique ID that identifies your organization to [!DNL Audience Manager] and the [!DNL Adobe Experience Cloud]. It consists of a case-sensitive, 24-character alphanumeric string followed by [!UICONTROL @AdobeOrg].

For example, an *`Organization ID`* looks like this: `1FD6776A524453CC0A490D44@AdobeOrg`.

The *`Organization ID`* is used by Audience Manager's [DIL](../dil/dil-overview.md) API, the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/), and other [!DNL Experience Cloud] solutions. Users with Administrator permissions can find the *`Organization ID`* on the [!DNL Adobe Admin Console]. See the [Administration - User Management FAQ](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

<br> 

**我可以大量建立特徵或目的地嗎？**

是。See [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools] 工具 *不* 受支援 [!DNL Audience Manager]。這些項目提供方便，僅提供給學生使用。For bulk changes, we recommend you work with the [Audience Manager APIs](../api/api.md) instead.

<br> 

**可以[!DNL Audience Manager]降低對協力廠商標籤或像素的需求，並改善頁面載入時間？**

[!DNL Audience Manager] 如果與第三方資料合作夥伴整合，您可以使用伺服器對伺服器ID呼叫來取代其像素和標籤 [!DNL Audience Manager]。In this case, [!DNL Audience Manager] would fire a single ID call the first time we see a user and synchronize that information with your third-party partner. 如此就無須從每個頁面呼叫多個像素。降低像素呼叫可改善頁面載入時間。

<br> 

**我已訂閱資料饋送。Where is that data stored?**

Your data feed and all the traits contained in the feed appear as subfolders and traits in [!DNL Audience Manager]. Go to **[!UICONTROL Audience Data > Traits]** and expand the [!UICONTROL 3rd-Party Data] folder to view your traits or create segments and models with this data.

<br> 

**什麼是[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager used [!UICONTROL Tag Insertion Manager] (TIM) to create and manage [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. For more information, see [Adobe Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**演算法模型與特徵建議之間有何差異？When should I use each of them?**

**演算法模型**

演算法模型不僅找出最具影響力的特徵，還能根據這些特性向使用者評分，並為每位使用者指派個別分數。然後，您可以建立演算法特徵來定位您的使用者。透過「特徵產生器」中的精確和觸及控制，您可以指定哪些使用者擁有您想要定位的具影響力特徵。

演算法模型可讓您在Audience Lab中，以不同的精確度層級和測試來選擇使用者，並更好地轉換使用者群組。See the detailed use case in [Compare Models in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

在演算法模型中，模型每個天執行一次，並重新整理符合演算法特性的使用者。

**特徵建議**

特徵Recommendations可快速取得其他特性的深入分析，這些分析與您在區段中使用的其他特性類似。

您應在下列情況下使用特徵Recommendations：

* 建立區段時需要快速深入解析；
* 您使用群體來簡短促銷活動或想要快速抑制轉換的對象；
* 您正在嘗試最大化觸及面。

<br> 

**Adobe Analytics和Audience Manager區段之間有任何差異嗎？**

Yes, please read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.
