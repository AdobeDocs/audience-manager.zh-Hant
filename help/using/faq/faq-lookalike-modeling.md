---
description: 外觀相似的建模通過自動資料分析幫助您發現新的、獨特的受眾。 本文提供了最常見問題的答案。
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: 相似建模常見問題
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# 相似建模常見問題

## 概述 {#overview}

本文提供了有關 [!UICONTROL Look-Alike Modeling]。

## 問題 {#questions}

**我為什麼要去 [!UICONTROL Accuracy & Reach] 圖？**

公寓 [!UICONTROL Accuracy & Reach] 圖表示幾乎每個用戶都通過模型得到相同的分數。 當您在運行模型的資料源中包含站點訪問者特性時，可能會發生這種情況。 要避免這種情況，請使用 [!UICONTROL Exclusions] 的子菜單。

 

**為什麼我的一些最有影響力的特質擁有很少的觀眾？**

算法選擇與基線特徵高度相關的特徵。 例如，如果某個特徵與基線特徵有100%的重疊，那麼它的體重將非常高，即使該特徵的用戶數量很小。

 

**為什麼我的模型沒有運行/重新運行？**

產生結果的模型只有在建立了至少一個活動算法特性並將其映射到活動段和目的地時才會繼續運行。

 

**為什麼我的模型沒有產生任何結果？**

這通常是由於在選定資料源中的基線種群和種群之間沒有顯著特徵重疊。

 

**是否對基線特性或段大小有任何建議？**

鑑於所選資料源中的基線人口和人口之間存在顯著的特徵重疊，幾千個用戶應足以運行該模型。 [!UICONTROL Look-Alike Modeling] 結果越準確，基線越大。

 

**我應為我的模型選擇哪些第三方資料源？**

使用與基線特性/段至少有一些重疊的資料源，但同時引入更多用戶。 您還應考慮與每個資料饋送關聯的成本。 在以下方面，不同資料提供商的成本和定價模型各不相同 [!UICONTROL Audience Marketplace]。

 

**使用第三方資料進行建模是否成本高？**

它取決於所選資料饋送的定價模型。 有些源允許免費建模，而其他源則收費。 請參閱 [為資料源購買者開單](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) 的雙曲餘切值。

 

**我可以建立多少個模型/特徵？**

目前，你可以建立多達20種算法模型和50種算法特性。

 

**模型訓練和算法特徵群的刷新頻率是多少？**

該模型每8天重新訓練一次，同時刷新算法特徵種群。
