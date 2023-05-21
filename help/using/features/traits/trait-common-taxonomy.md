---
description: 本文概述了使用通用分類對特徵進行分類。
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: 使用通用分類法將特徵分類
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 3%

---

# 使用通用分類法將特徵分類 {#classifying-traits-with-a-common-taxonomy}

本文概述了使用通用分類對特徵進行分類。

## Audience Manager分類

<!-- c_common_taxonomy_about.xml -->

的 [!DNL Audience Manager] 分類法是一種可選功能，它使用統一、邏輯和常見的命名約定對特徵進行分類。 它在平台級別運行，以幫助確保命名一致性 [!DNL Audience Manager] 生態系統。 最終，通用分類法旨在使我們的產品與有關消費者隱私和選擇退出流程的行業標準更好地保持一致。

## 特質分類的優點

使我們的客戶能夠構建定制細分市場和資料模型是 [!DNL Audience Manager] 以及您從我們的平台獲取價值的能力。 但是，還需要一種強大且可擴展的方法，將有關細分的資訊傳達給您的客戶和合作夥伴。 此外，此通信要求段資訊以易於理解和普遍理解的語言共用，同時保護您的專有特性和段名稱。 的 [!DNL Audience Manager] 公共分類法提供了此語言和功能。

## 分類法使用行業標準分類類別

公用分類基於由 [!DNL Interactive Advertising Bureau (IAB)]。 請參閱 [!DNL IAB]`s [網站](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) 有關網路和交換的質量保證指南的詳細資訊。

## 分類組織

的 [!DNL Audience Manager] 分類將資料組織到稱為層的嵌套類別中。 每個類別最多可包含3個資料分類的獨立層。 在最高級別，第1層類別將資料分組為其最一般的形式（如地理位置）。 隨後的層對較高級別、一般類別(如 *地理 — >美國 — >紐約*)。 然而，並非每個類別都有3個層次，有些只使用2個。

## 在資料類別中分類特徵

在中建立或編輯特徵時，可分配分類分類 [!UICONTROL Add New Trait Wizard] (位於* **[!UICONTROL Audience Data > Traits]***)。 請參閱 [建立特徵的文檔](../../features/traits/create-onboarded-rule-based-traits.md) 的子菜單。

## 使用分類：其他注意事項

如果您決定根據我們的常見分類法對特徵進行分類，請記住：

* 分類是 *可選*。
* 性狀 *不是* 預設情況下分配給分類類別（即，特徵不被分類為「未知」或「未分類」等）。
* 特徵可屬於 *一個* 僅分類類別（不允許使用多分類和跨分類分類）。
