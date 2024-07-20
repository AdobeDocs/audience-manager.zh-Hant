---
description: 說明演演算法特徵建立程式專屬的設定步驟和功能。
seo-description: Describes set up steps and features unique to the algorithmic trait creation process.
seo-title: Create Algorithmic Traits
solution: Audience Manager
title: 建立演演算法特徵
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# 建立演演算法特徵 {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

若要建立演演算法特徵，請前往[!UICONTROL Traits]並遵循下列步驟：

1. 按一下&#x200B;**[!UICONTROL Create New Trait]**，然後從下拉式功能表中選取&#x200B;**[!UICONTROL Algorithmic]**。
1. 在[基本資訊](../../features/traits/create-onboarded-rule-based-traits.md)區段中
   * 為特徵命名。
   * 選取資料來源。
   * 選擇儲存資料夾。
1. 展開[!UICONTROL Configuration]窗格並按一下&#x200B;**[!UICONTROL Browse All Models]**。
這會開啟一個新視窗，讓您選取要用於特徵的模型。
1. 選取模型並按一下&#x200B;**[!UICONTROL Add Selected Model to Trait]**。
新增模型會顯示觸及和精度設定。
1. 選取觸及率或準確度作為您的目標，然後從各自的下拉式功能表中選擇一個值。 完成時，按一下&#x200B;**[!UICONTROL Save]**。

## 演演算法特徵的組態設定 {#configure-settings}

在[!UICONTROL Trait Builder]中，[!UICONTROL Configuration]區段可讓您將演演算法模型與特徵建立關聯。 若要完成演演算法特徵建立程式，請選取模型並選擇觸及率或準確度目標。

### 必備條件

<!-- r_algo_trait_config_section.xml -->

* [建立相似模型](../../features/algorithmic-models/create-model.md)。
* 等待通知電子郵件，通知您模型資料執行已完成。
* 完成[基本資訊](../../features/traits/create-onboarded-rule-based-traits.md)區段中的必要欄位。

### 組態欄位與設定

| 介面元素 | 解釋 |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | 按一下&#x200B;**[!UICONTROL Update]**&#x200B;按鈕以開啟模型視窗。 從視窗中，選取要用來建立特徵的演演算法模型。 |
| **[!UICONTROL Select Goal Accuracy]** | 選取此選項可根據準確度建立特徵。 精確度是已評分的值，可指出潛在使用者與基準線的接近程度。 精確度範圍從0 （最不精確）到1 （最準確）。 |
| **[!UICONTROL Reach and Accuracy Data Columns]** | 此區段位於右側，會顯示最多21列數值資料，用以顯示模型的精確度和觸及值。 |
| **[!UICONTROL Reach and Accuracy Slider]** | 滑桿位於圖形底部，可讓您設定觸及率或準確度目標的數值。 您可以設定滑桿，然後選擇觸及或準確度目標按鈕，以建立特徵。 |

>[!MORELIKETHIS]
>
>* [精確度和觸及](../../features/traits/trait-accuracy-reach.md)
