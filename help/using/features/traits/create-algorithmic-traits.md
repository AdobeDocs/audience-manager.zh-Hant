---
description: 說明演算特徵建立程式專屬的設定步驟和功能。
seo-description: 說明演算特徵建立程式專屬的設定步驟和功能。
seo-title: 建立演算法特徵
solution: Audience Manager
title: 建立演算法特徵
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 建立演算法特徵 {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

若要建立演算法特徵，請前往 [!UICONTROL Traits] 並遵循下列步驟：

1. 按一 **[!UICONTROL Create New Trait]** 下並從下 **[!UICONTROL Algorithmic]** 拉式選單中選取。
1. 在「基 [本資訊」部分](../../features/traits/create-onboarded-rule-based-traits.md)
   * 命名特徵。
   * 選取資料來源。
   * 選擇儲存資料夾。
1. 展開窗 [!UICONTROL Configuration] 格，然後按一下 **[!UICONTROL Browse All Models]**。
這會開啟新視窗，讓您選取要與特徵搭配使用的模型。
1. 選取模型，然後按一下 **[!UICONTROL Add Selected Model to Trait]**。
新增模型可顯示觸及度和精確度設定。
1. 選擇達到或準確度作為目標，並從各自的下拉式選單中選擇一個值。 Click **[!UICONTROL Save]** when done.

## 演算法特徵的組態設定 {#configure-settings}

在中 [!UICONTROL Trait Builder]，此區 [!UICONTROL Configuration] 段可讓您將演算法模型與特徵建立關聯。 若要完成演算法特徵建立程式，請選取模型並選擇達到或精確目標。

### 必備條件

<!-- r_algo_trait_config_section.xml -->

* [建立演算法模型](../../features/algorithmic-models/create-model.md#build-model)。
* 等待通知電子郵件，讓您知道模型資料執行已完成。
* 填寫「基本資訊」區段 [中的必填欄](../../features/traits/create-onboarded-rule-based-traits.md) 。

### 配置欄位和設定

| 介面元素 | 解釋 |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | 按一下該 **[!UICONTROL Update]** 按鈕開啟模型窗口。 從視窗中，選取您要用來建立特徵的演算法模型。 |
| **[!UICONTROL Select Goal Accuracy]** | 選取這個選項，可根據精確度建立特徵。 準確度是一個計分值，可指出潛在使用者與您的基準有多接近。 精確等級範圍從0（最不精確）到1（最精確）。 |
| **[!UICONTROL Reach and Accuracy Data Columns]** | 此區段位於右側，最多可顯示21列數值資料，顯示模型的準確度和觸及值。 |
| **[!UICONTROL Reach and Accuracy Slider]** | 滑桿位於圖形底部，可讓您設定觸及或精確目標的數值。 您可以設定滑桿，然後選擇到達或精確目標按鈕來建立特徵。 |

>[!MORELIKETHIS]
>
>* [準確性與觸及性](../../features/traits/trait-accuracy-reach.md)

