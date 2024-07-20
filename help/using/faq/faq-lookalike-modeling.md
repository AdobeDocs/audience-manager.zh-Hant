---
description: 相似建模可協助您透過自動化資料分析，探索新的不重複受眾。 本文提供常見問題的解答。
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: 相似建模常見問題集
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# 相似建模常見問題集

## 概述 {#overview}

本文提供有關[!UICONTROL Look-Alike Modeling]最常見問題的解答。

## 問題 {#questions}

**為什麼我會取得一般[!UICONTROL Accuracy & Reach]圖表？**

平面的[!UICONTROL Accuracy & Reach]圖表表示幾乎所有使用者在模型中都收到相同的評分。 當您在執行模型的資料來源中包含網站訪客特徵時，可能會發生此狀況。 若要避免此問題，請在模型建立步驟期間，使用[!UICONTROL Exclusions]欄位從模型輸入中移除泛型特徵。

 

**為什麼我的一些最具影響力特徵只有很小的對象？**

演演算法會選取與基線特徵高度相關的特徵。 例如，如果特定特徵與基線特徵有100%的重疊，則即使該特徵中的使用者數量較少，也會有很高的權重。

 

**為什麼我的模型沒有執行/重新執行？**

只有在您建立至少一個使用中的演演算法特徵，並將它對應至使用中的區段和目的地時，產生結果的模型才會繼續執行。

 

**為什麼我的模型沒有產生任何結果？**

這通常是因為在基線母體與所選資料來源母體之間沒有顯著的特徵重疊所導致。

 

**對於基準特徵或區段大小是否有任何建議？**

由於基準母體與所選資料來源中的母體之間存在重大特徵重疊，因此只有數千名使用者才足以在其上執行模型。 [!UICONTROL Look-Alike Modeling]會產生更精確的結果，基準線越大。

 

**我應該為我的模型選擇哪些協力廠商資料來源？**

使用與基線特徵/區段至少有一些重疊，但同時引進其他使用者的資料來源。 您也應該考慮與每個資料摘要相關的成本。 在[!UICONTROL Audience Marketplace]中，不同資料提供者的成本和定價模型各有不同。

 

**使用協力廠商資料進行模型化是否需要費用？**

這取決於所選資料摘要的定價模型。 有些摘要可免費提供模型製作，有些則需額外付費。 如需詳細資訊，請參閱[資料摘要購買者的帳單](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)。

 

**我可以建立多少模型/特徵？**

目前，您可以建立最多20個演演算法模型和50個演演算法特徵。

 

**模型訓練和演演算法特徵母體的重新整理頻率為何？**

模型每8天會重新訓練一次，並會重新整理演演算法特徵母體。
