---
description: 本文概括地介紹了使用通用分類法對特徵進行分類的方法。
keywords: DIL
seo-description: 本文概括地介紹了使用通用分類法對特徵進行分類的方法。
seo-title: 使用通用分類法分類特徵
solution: Audience Manager
title: 使用通用分類法分類特徵
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# 使用通用分類法分類特徵 {#classifying-traits-with-a-common-taxonomy}

本文概括地介紹了使用通用分類法對特徵進行分類的方法。

## Audience Manager分類法

<!-- c_common_taxonomy_about.xml -->

分類 [!DNL Audience Manager] 法是選用的功能，可使用統一、邏輯和常見的命名慣例來分類特徵。 它在平台層級運作，以協助確保整個生態系統的命名一 [!DNL Audience Manager] 致性。 最後，通用分類法旨在讓我們的產品更符合消費者隱私權和退出程式的業界標準。

## 特徵分類的優點

讓客戶建立自訂細分和資料模型是模型的核心，也是 [!DNL Audience Manager] 您從我們平台獲取價值的核心。 但是，您還需要一種強穩且可擴充的方式，將區段相關資訊傳達給客戶和合作夥伴。 此外，此項通訊要求區段資訊必須以易於理解且廣為瞭解的語言來共用，同時保護您的專屬特性和區段名稱。 通用 [!DNL Audience Manager] 分類法提供了此語言和功能。

## 分類法使用行業標準分類類別

通用分類法基於由建立的分類 [!DNL Interactive Advertising Bureau (IAB)]。 如需網路與交 [!DNL IAB]流所的 [品質保證方針的詳細資訊](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) ，請參閱網站。

## 分類組織

分類 [!DNL Audience Manager] 將資料組織成稱為層的巢狀類別。 每個類別最多可包含3個不同的資料分類層。 在最高層，第1層類別會將資料分組成最一般的表單（例如地理位置）。 後續各層對較高級別的一般類別(例如，地理—&gt; *美國—&gt;紐約*)提供了更高的專一性。 但是，並非每個類別都有3個層級，有些僅使用2個層級。

## 分類資料類別中的特徵

在(位於* [!UICONTROL Add New Trait Wizard]**[!UICONTROL Audience Data > Traits]***)中建立或編輯特徵時，您會指派分類。 如需詳細資 [訊，請參閱有關建立特徵](../../features/traits/create-onboarded-rule-based-traits.md) 的檔案。

## 使用分類法：其他考量事項

如果您決定根據我們的常見分類法來分類特徵，請務必記住：

* 分類是選 *用的*。
* 特 *徵預設不會* 指派給分類類別（亦即，特徵未分類為「未知」或「未分類」等）。
* 特徵只能屬於 *一個分類* （不允許多個和跨類別分類）。