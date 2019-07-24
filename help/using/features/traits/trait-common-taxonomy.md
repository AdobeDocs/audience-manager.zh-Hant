---
description: 本文提供一般分類法分類特性的一般概述。
keywords: DIL
seo-description: 本文提供一般分類法分類特性的一般概述。
seo-title: 使用常見的分類法分類特徵
solution: Audience Manager
title: 使用常見的分類法分類特徵
uuid: 2e177344-07d9-40a7-40a7-8c99-c6 c6518 b9 d97
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Classifying Traits with a Common Taxonomy {#classifying-traits-with-a-common-taxonomy}

本文提供一般分類法分類特性的一般概述。

## Audience Manager Taxonomy

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager] 分類法是選用的功能，可使用一致、邏輯和常用的命名慣例來分類特徵。It operates at the platform level to help ensure naming consistency throughout the [!DNL Audience Manager] ecosystem. 一般的分類法旨在讓我們的產品更符合消費者隱私權和選擇退出程序的業界標準。

## 特徵分類的優點

Enabling our customers to build custom segments and data models is core to the [!DNL Audience Manager] model and to your ability to capture value from our platform. 但是，還需要一種健全且可擴充的方式，以便向客戶和合作夥伴傳達有關細分的資訊。此外，此項通訊需要以易懂和普遍易懂的語言共用區段資訊，同時保護您專屬特徵和區段名稱。[!DNL Audience Manager] 一般的分類法提供此語言和功能。

## The Taxonomy使用業界標準分類類別

The common taxonomy is based on the classifications created by the [!DNL Interactive Advertising Bureau (IAB)]. Refer to the [!DNL IAB]'s [website](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) for more information about quality assurance guidelines for networks and exchanges.

## 分類組織

[!DNL Audience Manager] 分類會將資料組織成巢狀類別，稱為層。每個類別最多可包含個不同的資料分類層級。在最高層級，層級類別將資料分成最一般的形式(例如地理位置)。Subsequent tiers provide greater specificity to the higher level, general category (e.g., *geography --&gt; United States --&gt; New York*). 不過，並非每個類別都有個層級，有些則僅使用2。

## 分類資料類別中的特徵

You assign taxonomic classifications when creating or editing traits in the [!UICONTROL Add New Trait Wizard] (located in * **[!UICONTROL Audience Data > Traits]***). Refer to the [documentation on creating traits](../../features/traits/create-onboarded-rule-based-traits.md) for more information.

## 使用分類法：其他考量事項

如果您決定根據我們的一般分類法分類特徵，請務必記住：

* Classification is *optional*.
* Traits *are not* assigned to a taxonomic category by default (i.e., traits are not classified as "unknown" or "uncategorized" etc.).
* Traits can belong to *one* taxonomic category only (multiple and cross-category classifications are not allowed).