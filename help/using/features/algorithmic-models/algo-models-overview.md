---
description: 說明Audience Manager中可用的演算法模型。
keywords: algo模型如何運用預測對象
seo-description: 說明Audience Manager中可用的演算法模型。
seo-title: 演算法模型概述
solution: Audience Manager
title: 演算法模型概述
feature: 演算法模型
exl-id: ee5c3392-2756-45c5-b325-41a51d3c494f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 16%

---

# 演算法模型概述

## 什麼是演算法建模{#what-algo-modeling}

Audience Manager中的演算法模型是指運用資料科學來擴充現有受眾，或將其分類為角色。

這可透過兩種演算法來完成：[!UICONTROL Look-Alike Modeling]和[!UICONTROL Predictive Audiences]。

## 外觀類似塑型{#lam}

[!UICONTROL Look-Alike Modeling] 可協助您透過自動化資料分析，探索新的不重複受眾。當您選取特徵或區段、時間間隔以及第一方和第三方資料來源時，程式就會開始。 您的選擇為演算法模型提供輸入。 分析程式執行時，會根據所選母體的共用特性，尋找符合資格的使用者。

完成後，此資料可在[特徵產生器](../../features/traits/about-trait-builder.md)中使用，您可在此處根據[正確度建立特徵並達到](../../features/traits/trait-accuracy-reach.md)。 此外，您也可以建立區段，將演算法特徵與規則型特徵結合，並使用布林運算式和比較運算子新增其他資格要求。

[!UICONTROL Look-Alike Modeling] 可讓您以動態方式從所有可用的特徵資料中擷取值。

若要深入了解[!UICONTROL Look-Alike Modeling]，請參閱[了解相似建模](understanding-models.md)。

## 預測受眾{#predictive-audiences}

[!UICONTROL Predictive Audiences] 可協助您使用進階的資料科學技術，將未知的受眾即時分類為不重複角色。

 在行銷環境中，角色是一種受眾區段，由擁有一組共同特定特徵 (例如人口統計、瀏覽習慣、購物記錄等) 的訪客、使用者或潛在購買者所定義。

[!UICONTROL Predictive Audiences] 模型運用Audience Manager的機器學習功能，將未知的對象自動分類為不重複角色，進一步運用此概念。Audience Manager會計算未知對象對一組已知對象的傾向來達成此目的。

若要深入了解[!UICONTROL Predictive Audiences]，請參閱[預測對象概述](predictive-audiences.md)。
