---
description: 說明演算法特徵建立程序專屬的步驟和功能。
seo-description: 說明演算法特徵建立程序專屬的步驟和功能。
seo-title: 建立演算法特徵
solution: Audience Manager
title: 建立演算法特徵
uuid: 50c2d2d1-f412-479b-be70-4f139429 c388
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Algorithmic Traits {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

To create an algorithmic trait, go to [!UICONTROL Traits] and follow the steps below:

1. Click **[!UICONTROL Create New Trait]** and select **[!UICONTROL Algorithmic]** from the drop down menu.
1. In the [Basic Information](../../features/traits/create-onboarded-rule-based-traits.md) section
   * 為特徵命名。
   * 選取資料來源。
   * 選擇儲存資料夾。
1. Expand the [!UICONTROL Configuration] pane and click **[!UICONTROL Browse All Models]**.
這會開啓新視窗，讓您選取要與特徵搭配使用的模型。
1. Select a model and click **[!UICONTROL Add Selected Model to Trait]**.
新增模型會顯示觸及和正確性設定。
1. 選擇觸及或準確度作為目標，並從個別下拉式選單選擇值。Click **[!UICONTROL Save]** when done.

>[!MORE_贊_ this]
>
>* [正確性與觸及面](../../features/traits/trait-accuracy-reach.md)


## Configuration Settings for Algorithmic Traits {#configure-settings}

In [!UICONTROL Trait Builder], the [!UICONTROL Configuration] section lets you associate an algorithmic model to a trait. 若要完成演算法特徵建立程序，請選取模型並選擇觸及或正確性目標。

### 必備條件

<!-- r_algo_trait_config_section.xml -->

* [建立演算法模型](../../features/algorithmic-models/create-model.md#build-model)。
* 等候通知電子郵件，讓您知道模型資料執行已完成。
* Complete the required fields in the [Basic Information](../../features/traits/create-onboarded-rule-based-traits.md) section.

### 設定欄位與設定

| 介面元素 | 解釋 |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Click the **[!UICONTROL Update]** button to open the models window. 在視窗中，選取您要用來建立特徵的演算法模型。 |
| **[!UICONTROL Select Goal Accuracy]** | 選取此選項，以根據準確度建立特徵。準確度是計分值，指出潛在使用者對您基準的程度。準確度等級從(至少不準確)到(最準確)。 |
| **[!UICONTROL Reach and Accuracy Data Columns]** | 此區域位於右側，最多顯示21列數值資料，顯示模型的準確性和觸及值。 |
| **[!UICONTROL Reach and Accuracy Slider]** | 滑桿位於圖形底部，可讓您設定覆蓋或準確度目標的數值。您可以設定滑桿，然後選擇觸及或正確性目標按鈕來建立特徵。 |

>[!MORE_贊_ this]
>
>* [正確性與觸及面](../../features/traits/trait-accuracy-reach.md)