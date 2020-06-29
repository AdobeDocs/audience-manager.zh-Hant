---
description: 產品與功能的相關常見疑問與問題。
keywords: audience manager cookies
seo-description: 產品與功能的相關常見疑問與問題。
seo-title: 產品特色與功能常見問題集
solution: Audience Manager
title: 產品特色與功能常見問題集
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 91%

---


# 產品特色與功能常見問題集{#product-features-and-functions-faq}

產品與功能的相關常見疑問與問題。

 

<!-- 

faq_features_functions.xml

 -->

**什麼是組織 ID？在哪裡可找到它？**

*`Organization ID`* 是不重複 ID，可向 [!DNL Audience Manager] 與 [!DNL Adobe Experience Cloud] 識別您的組織。它包含區分大小寫的 24 個英數字元字串，後面接著 [!UICONTROL @AdobeOrg]。

例如，*`Organization ID`* 看起來像這樣：`1FD6776A524453CC0A490D44@AdobeOrg`。

*`Organization ID`* 用於 Audience Manager 的 [DIL](../dil/dil-overview.md) API、[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html)，以及其他 [!DNL Experience Cloud] 解決方案。擁有管理員權限的使用者可以在 [!DNL Adobe Admin Console] 上找到 *`Organization ID`*。請參閱[管理 - 使用者管理常見問題集](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/manage-users-and-products/admin-getting-started.html)。

 

**我可以建立大量特徵或目的地嗎？**

是。請參閱[大量管理工具](../reference/bulk-management-tools/bulk-management-intro.md)。

>[!NOTE]
>
>[!DNL Audience Manager] *不*&#x200B;支援 [!UICONTROL Bulk Management Tools] 工具。之所以提供是出於便利性和禮貌。若要進行大量變更，建議您改用 [Audience Manager API](../api/api.md)。

 

**當執行大量ID匯出至目標時，會遺失部分客戶ID。 Why does that happen?**

當裝置ID([AAM UUID](../reference/ids-in-aam.md))連結至多個CRM ID([DPUUID](../reference/ids-in-aam.md))時，只會匯出最新的對應。 這就是為什麼您可能會看到匯出的裝置ID數量低於預期。

 

**[!DNL Audience Manager]可以減少對第三方標籤或像素的需求，並改善頁面載入時間嗎？**

如果 [!DNL Audience Manager] 已與您的第三方資料合作夥伴整合，您可以對 [!DNL Audience Manager] 發出伺服器對伺服器 ID 呼叫，取代其像素和標籤。在這種情況下，當我們第一次看到某個使用者，[!DNL Audience Manager] 會引發單一 ID 呼叫，並將該資訊與您的第三方合作夥伴同步。如此一來，您就不需要從每個頁面發出多個像素呼叫。減少像素呼叫可改善頁面載入時間。

 

**我已訂閱資料摘要。資料會儲存在哪裡？**

您的資料摘要和摘要中包含的所有特徵，會在 [!DNL Audience Manager] 中顯示為子檔案夾和特徵。前往 **[!UICONTROL Audience Data > Traits]** 並展開 [!UICONTROL 3rd-Party Data] 資料夾來檢視您的特徵，或使用此資料建立區段和模型。

 

**什麼是[!UICONTROL Tag Insertion Manager (TIM)]？**

Audience Manager 使用 [!UICONTROL Tag Insertion Manager] (TIM) 來建立和管理 [!UICONTROL data collection code (DIL)]。此功能已淘汰，並前後以 [!UICONTROL Dynamic Tag Manager (DTM)] 和 [!DNL Adobe Experience Platform Launch] 取代。如需詳細資訊，請參閱 [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) 和 [Dynamic Tag Management](https://docs.adobe.com/content/help/zh-Hant/dtm/using/dtm-home.html)。

 

**演算法模型與特徵建議之間有何差異？分別應在何時使用？**

**演算法模型**

演算法模型不僅可找出最具影響力的特徵，還會根據這些特徵對使用者進行評分，並為每位使用者指派個別的分數。接著您可建立演算法特徵，來鎖定您的使用者。在特徵產生器中，您可以透過精確度和觸及控制功能，指定哪些使用者擁有您想鎖定的具影響力特徵。

演算法模型可讓您選取不同精確度等級的使用者，並在 Audience Lab 中測試哪一組使用者轉換效果較佳。請參閱[在 Audience Lab 中比較模型](../features/audience-lab/audience-lab-use-cases.md#compare-models)中的詳細使用案例。

在演算模型中，模型每 8 天會執行一次，並重新整理符合演算法特徵的使用者。

**特徵建議**

特徵建議可快速深入分析有哪些其他特徵與您在區段中所使用的特徵相似。

您應在下列情況下使用特徵建議：

* 您在建立區段時需要快速的深入分析；
* 您正使用區段進行簡短的行銷活動，或想要快速隱藏轉換的受眾；
* 您正嘗試最大程度提高觸及率。

 

**Adobe Analytics 和 Audience Manager 區段之間是否有任何差異？**

有，請參閱[瞭解 Analytics 和 Audience Manager 中的區段](https://docs.adobe.com/content/help/zh-Hant/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)，深入瞭解差異。
