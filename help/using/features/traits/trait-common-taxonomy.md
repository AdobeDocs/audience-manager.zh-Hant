---
description: 本文提供使用通用分類法分類特徵的一般概述。
keywords: DIL
seo-description: 本文提供使用通用分類法分類特徵的一般概述。
seo-title: 使用通用分類法將特徵分類
solution: Audience Manager
title: 使用通用分類法將特徵分類
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: 特徵
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 5%

---

# 使用通用分類法將特徵分類 {#classifying-traits-with-a-common-taxonomy}

本文提供使用通用分類法分類特徵的一般概述。

## Audience Manager分類法

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager]分類法是選用功能，可使用統一、邏輯和常見的命名慣例來分類特徵。 它在平台層級運作，有助於確保[!DNL Audience Manager]生態系統中的命名一致性。 最終，通用分類法旨在讓我們的產品與消費者隱私權和退出程式的業界標準更趨一致。

## 特徵分類的優點

讓客戶建立自訂區段和資料模型，是[!DNL Audience Manager]模型及您從平台擷取價值的核心。 不過，您還需要具備強大且可擴充的方式，將區段相關資訊傳達給客戶和合作夥伴。 此外，此通訊需要以簡單易懂且普遍了解的語言來共用區段資訊，同時保護您的專屬特徵和區段名稱。 [!DNL Audience Manager]通用分類法提供了此語言和功能。

## 分類法使用行業標準分類類別

常見分類法以[!DNL Interactive Advertising Bureau (IAB)]所建立的分類為基礎。 有關網路和交換的質量保證指南的詳細資訊，請參閱[!DNL IAB]的[website](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines)。

## 分類組織

[!DNL Audience Manager]分類法將資料組織到稱為分層的嵌套類別中。 每個類別最多可包含3個資料分類的不同層級。 在最高層級，第1層類別會將資料分組為最一般的形式（例如地理位置）。 後續各層對較高級別的一般類別（例如&#x200B;*geography —>美國 — >紐約*）提供了更大的特異性。 然而，並非每個類別都有3個層級，有些僅使用2個層級。

## 分類資料類別中的特徵

在[!UICONTROL Add New Trait Wizard]中建立或編輯特徵時（位於* **[!UICONTROL Audience Data > Traits]***中），您會指派分類。 如需詳細資訊，請參閱有關建立特徵](../../features/traits/create-onboarded-rule-based-traits.md)的檔案。[

## 使用分類法：其他考量事項

如果您決定根據我們的通用分類法來分類特徵，請務必記住：

* 分類為&#x200B;*optional*。
* 特徵&#x200B;*預設不會*&#x200B;指派給分類類別（亦即特徵未分類為「未知」或「未分類」等）。
* 特徵只能屬於&#x200B;*一個*&#x200B;分類類別（不允許使用多個和跨類別分類）。
