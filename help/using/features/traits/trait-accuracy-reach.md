---
description: 說明演演算法特徵中精確度和觸及率之間的關係。
seo-description: Describes the relationship between accuracy and reach in algorithmic traits.
seo-title: Accuracy and Reach
solution: Audience Manager
title: 精確度和觸及
uuid: d121e099-6642-4003-ad4f-507d21e478d8
feature: Traits
exl-id: 647b283a-fcfa-4e3f-8667-50c6aacbc78a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---

# 精確度和觸及 {#accuracy-and-reach}

說明演演算法特徵中精確度和觸及率之間的關係。

<!-- c_accuracy_reach.xml -->

## 精準度與觸及：關於

使用演演算法特徵時，請務必瞭解精確度和觸及率之間的關係。 正確性以評分值表示，其反映使用者與基準線的相似程度。 精確度範圍從0 （最不精確）到1 （最準確）。 觸及率只是一個值，代表您想在特徵中包含的不重複使用者人數。 觸及率和準確度成反比。 精確的特徵觸及率較低的使用者，而觸及率較高的特徵則較不準確。 下圖說明了此概念。

![](assets/Reach_v_Accuracy.png)

## 精確度和觸及率會影響對象規模

您的業務目標應可協助您在使用演演算法特徵時，針對精確度和觸及率做出正確的決策。 如果精確度是您的目標，請注意，特徵母體可能會隨著模型執行而增減。 母體變更是演演算法在每個評估期間進行決策的結果。 有時，演演算法會在處理週期中尋找更多合格使用者，而在其他週期中可能會尋找較少合格使用者。 結果由用來建立模型的基線資料，以及自上次模型執行以來出現的新訪客和特徵資格所決定。 相較之下，使用觸及率時，使用者母體計數會保持不變。 例如，如果您希望達到10,000位使用者，演演算法會確保每次執行模型時都會點選該數字。

## 精確度和觸及範圍的一般使用案例

精確度或觸及率的焦點取決於您想要對特定區段達成的目的。 下表可協助您在建立特徵時評估精確度與觸及率。

| 特徵決定偏好 | 協助尋找 |
|---|---|
| **準確度** | 類似於模型中基線客戶的使用者。 當您想要觸及特定受眾時，這對鎖定目標的行銷活動非常有用。 |
| **連線** | 每次資料執行的特定使用者人數。 當您對接觸特定規模的對象感興趣時，對品牌促銷活動會很有用。 |
