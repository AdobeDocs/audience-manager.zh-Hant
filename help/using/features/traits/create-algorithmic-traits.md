---
description: 描述算法特徵建立過程所特有的設定步驟和特徵。
seo-description: Describes set up steps and features unique to the algorithmic trait creation process.
seo-title: Create Algorithmic Traits
solution: Audience Manager
title: 建立演算法特徵
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# 建立演算法特徵 {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

要建立算法特性，請 [!UICONTROL Traits] 並執行以下步驟：

1. 按一下 **[!UICONTROL Create New Trait]** 選擇 **[!UICONTROL Algorithmic]** 的下界。
1. 在 [基本資訊](../../features/traits/create-onboarded-rule-based-traits.md) 節
   * 說出特徵。
   * 選擇資料源。
   * 選擇儲存資料夾。
1. 展開 [!UICONTROL Configuration] 按一下 **[!UICONTROL Browse All Models]**。
這將開啟一個新窗口，通過該窗口可以選擇要與特徵一起使用的模型。
1. 選取模型，然後按一下 **[!UICONTROL Add Selected Model to Trait]**。
添加模型會顯示訪問範圍和精度設定。
1. 選擇達到或準確性作為目標，然後從相應的下拉菜單中選擇一個值。 按一下 **[!UICONTROL Save]** 完成。

## 算法特徵的配置設定 {#configure-settings}

在 [!UICONTROL Trait Builder]，也請參見Wiki頁。 [!UICONTROL Configuration] 讓你將算法模型與特徵關聯。 要完成算法特徵建立過程，請選擇一個模型，然後選擇一個達到或準確的目標。

### 必要條件

<!-- r_algo_trait_config_section.xml -->

* [建立相似模型](../../features/algorithmic-models/create-model.md).
* 等待通知電子郵件，該電子郵件使您知道模型資料運行已完成。
* 完成 [基本資訊](../../features/traits/create-onboarded-rule-based-traits.md) 的子菜單。

### 配置欄位和設定

| 介面元素 | 解釋 |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | 按一下 **[!UICONTROL Update]** 按鈕。 從窗口中，選擇要用於建立特徵的算法模型。 |
| **[!UICONTROL Select Goal Accuracy]** | 選擇此選項可基於精度建立特徵。 準確性是一個得分值，它指示潛在用戶與基線的距離。 精度刻度範圍從0（最不精確）到1（最精確）。 |
| **[!UICONTROL Reach and Accuracy Data Columns]** | 此部分位於右側，最多顯示21行數字資料，顯示模型的精度和到達值。 |
| **[!UICONTROL Reach and Accuracy Slider]** | 位於圖形底部的滑塊允許您為達到或精確目標設定數值。 您可以設定滑塊，然後選擇達到或精確目標按鈕以建立特徵。 |

>[!MORELIKETHIS]
>
>* [精確度和觸及](../../features/traits/trait-accuracy-reach.md)

