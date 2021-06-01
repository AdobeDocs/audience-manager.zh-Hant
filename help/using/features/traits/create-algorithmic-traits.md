---
description: 說明演算法特徵建立程式專屬的設定步驟和功能。
seo-description: 說明演算法特徵建立程式專屬的設定步驟和功能。
seo-title: 建立演算法特徵
solution: Audience Manager
title: 建立演算法特徵
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: 特徵
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 5%

---

# 建立演算法特徵 {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

若要建立演算法特徵，請前往[!UICONTROL Traits]並遵循下列步驟：

1. 按一下&#x200B;**[!UICONTROL Create New Trait]**&#x200B;並從下拉菜單中選擇&#x200B;**[!UICONTROL Algorithmic]**。
1. 在[基本資訊](../../features/traits/create-onboarded-rule-based-traits.md)部分
   * 為特徵命名。
   * 選取資料來源。
   * 選擇儲存資料夾。
1. 展開[!UICONTROL Configuration]窗格，然後按一下&#x200B;**[!UICONTROL Browse All Models]**。
這會開啟一個新視窗，讓您選取要與特徵搭配使用的模型。
1. 選擇模型，然後按一下&#x200B;**[!UICONTROL Add Selected Model to Trait]**。
新增模型會顯示觸及和正確性設定。
1. 選取達到或準確度作為目標，然後從個別下拉式功能表中選擇值。 完成後，按一下&#x200B;**[!UICONTROL Save]**。

## 演算法特徵的組態設定{#configure-settings}

在[!UICONTROL Trait Builder]中， [!UICONTROL Configuration]區段可讓您將演算法模型與特徵建立關聯。 若要完成演算法特徵建立程式，請選取模型並選擇達到或準確目標。

### 必要條件

<!-- r_algo_trait_config_section.xml -->

* [建立相似模型](../../features/algorithmic-models/create-model.md).
* 等待通知電子郵件，讓您知道模型資料執行已完成。
* 填寫[基本資訊](../../features/traits/create-onboarded-rule-based-traits.md)部分中的必填欄位。

### 配置欄位和設定

| 介面元素 | 解釋 |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | 按一下&#x200B;**[!UICONTROL Update]**&#x200B;按鈕以開啟模型窗口。 從視窗中，選取您要用來建立特徵的演算法模型。 |
| **[!UICONTROL Select Goal Accuracy]** | 選取此選項，根據準確度建立特徵。 準確度是指可指出潛在使用者與您基準之間的距離範圍的得分值。 精度刻度範圍從0（最不精確）到1（最精確）。 |
| **[!UICONTROL Reach and Accuracy Data Columns]** | 此區段位於右側，最多會顯示21列數值資料，用以顯示模型的準確度和觸及值。 |
| **[!UICONTROL Reach and Accuracy Slider]** | 滑桿位於圖表底部，可讓您為觸及或準確度目標設定數值。 您可以設定滑桿，然後選擇達到或準確度目標按鈕以建立特徵。 |

>[!MORELIKETHIS]
>
>* [精確度和觸及](../../features/traits/trait-accuracy-reach.md)

