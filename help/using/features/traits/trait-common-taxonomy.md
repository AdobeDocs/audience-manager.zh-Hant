---
description: 本文提供使用通用分類法將特徵分類的一般概觀。
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
source-wordcount: '366'
ht-degree: 0%

---

# 使用通用分類法將特徵分類 {#classifying-traits-with-a-common-taxonomy}

本文提供使用通用分類法將特徵分類的一般概觀。

## Audience Manager分類法

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager]分類法是一項選擇性功能，可透過統一、邏輯及普遍瞭解的命名慣例來分類特徵。 它在平台層級運作，以協助確保整個[!DNL Audience Manager]生態系統的命名一致性。 歸根結底，通用分類法的設計目的，是為了讓我們的產品在消費者隱私權和選擇退出程式方面，更符合業界標準。

## 特徵分類的優點

讓我們的客戶建立自訂區段和資料模型，是[!DNL Audience Manager]模型和您從我們的平台擷取價值能力的核心。 然而，我們還需要強大且可擴充的手段，將區段的相關資訊傳達給您的客戶和合作夥伴。 此外，這項通訊需要以容易理解和普遍理解的語言共用區段資訊，同時保護您的專屬特徵和區段名稱。 [!DNL Audience Manager]通用分類法提供此語言和功能。

## 分類法使用產業標準分類類別

通用分類法以[!DNL Interactive Advertising Bureau (IAB)]建立的分類為基礎。 請參閱[!DNL IAB]的[網站](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines)，以取得有關網路和交換品質保證准則的詳細資訊。

## 分類組織

[!DNL Audience Manager]分類法會將資料組織成稱為階層的巢狀類別。 每個類別最多可包含3個不同的資料分類階層。 在最上層，第1級類別會將資料分組為其最一般的形式（例如，地理位置）。 後續層級會為較高層級的一般類別提供更高的特殊性（例如，*地理位置 — >美國 — >紐約*）。 不過，並非每個類別都有3個階層，有些僅使用2個。

## 分類資料類別中的特徵

您在[!UICONTROL Add New Trait Wizard] （位於* **[!UICONTROL Audience Data > Traits]***）中建立或編輯特徵時，指派分類法分類。 如需詳細資訊，請參閱有關建立特徵[&#128279;](../../features/traits/create-onboarded-rule-based-traits.md)的檔案。

## 使用分類法：其他考量事項

如果您決定根據我們的通用分類法將特徵分類，請務必記住：

* 分類為&#x200B;*選擇性*。
* 依預設，特徵&#x200B;*不會*&#x200B;指派給分類類別（亦即，特徵不會分類為「未知」或「未分類」等）。
* 特徵只能屬於&#x200B;*one*&#x200B;分類類別（不允許多重和跨類別分類）。
