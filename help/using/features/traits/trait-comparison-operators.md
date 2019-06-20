---
description: 本文說明「特徵產生器」使用的比較運算子。
seo-description: 本文說明「特徵產生器」使用的比較運算子。
seo-title: 使用特徵產生器中的比較運算子
solution: Audience Manager
title: 使用特徵產生器中的比較運算子
uuid: 41bec3b3-e5 df-4a6 f-abb0-80ce4 c75 f5 e7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Working with Comparison Operators in Trait Builder {#working-with-comparison-operators-in-trait-builder}

This article describes the comparison operators used by [!UICONTROL Trait Builder].

## 比較運算子的目的

<!-- c_tb_comparison_operators.xml -->

比較運算子(或關聯運算子)用於比較、測試或評估不同值之間的關係。In [!UICONTROL Trait Builder], when building signal rules, comparison operators let you test the relationship between different key-value pairs. 例如，您可以建立信號規則來定義昂貴相機購物者的對象。在這種情況下，您可以建立相機/價格機碼配對配對，並符合使用者尋找的價格等於或大於固定金額的相機。

## 比較運算子的優勢

當您需要根據多個值評估和建立特徵時，比較運算子很有用。檢視商品和服務的價格可證明本情況。例如，您的企業可能想要根據他們檢視的產品價格來識別訪客。不過，根據特定值定義個別區段的效率可能會比較低。比較運算子可根據價格臨界值或範圍建立分段觸發，協助克服此障礙。

## 比較運算子

您可以使用下列比較運算子建立規則：

| 運算元 | 定義 |
|---|---|
| **==** | 等於 |
| **!=** | 不等於 |
| **&gt;** | 大於 |
| **&lt;** | 小於 |
| **=&gt;** | 大於/等於 |
| **&lt;=** | 小於/等於 |

## 具名運算子

您可以使用下列命名運算子建立規則：

| 運算元 | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Matcheswords]** | The value in a key-value pair *matches* the pattern specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |
| **[!UICONTROL Matchesregex]** | The value in a key-value pair *matches* the pattern specified by a regular expression. [進一步瞭解](../../features/traits/trait-builder-regex.md) 如何使用規則運算式 [!UICONTROL Trait Builder]。 |

>[!MORE_贊_ this]
>
>* [特徵和區段產生器中的布林運算式](../../reference/boolean-expressions-tsb.md)
>* [瞭解TraitBuilder中的布林運算式](../../reference/boolean-expressions-tsb.md)
>* [TraitBuilder運算式中的操作順序](../../features/traits/trait-operator-precedence.md)
>* [使用布林和比較運算子的運算式範例](../../features/traits/trait-expression-samples.md)

