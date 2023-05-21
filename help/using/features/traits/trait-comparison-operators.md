---
description: 本文介紹了Trait Builder使用的比較運算子。
seo-description: This article describes the comparison operators used by Trait Builder.
seo-title: Working with Comparison Operators in Trait Builder
solution: Audience Manager
title: 在特徵產生器中使用比較運算子
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 10%

---

# 在特徵產生器中使用比較運算子 {#working-with-comparison-operators-in-trait-builder}

本文描述了使用的比較運算子 [!UICONTROL Trait Builder]。

## 比較運算子的用途

<!-- c_tb_comparison_operators.xml -->

比較運算子（或關係運算子）用於比較、test或評估不同值之間的關係。 在 [!UICONTROL Trait Builder]，在生成信號規則時，比較運算子允許您test不同鍵值對之間的關係。 例如，您可以建立一個信號規則，為昂貴的相機購物者定義受眾。 在這種情況下，如果用戶查找的相機價格等於或大於設定金額，則可以建立相機/價格鍵值對，並驗證用戶的資格。

## 比較算子的優勢

當您需要基於多個值評估和建立特徵時，比較運算子非常有用。 從商品和服務的價格看，就能說明這一狀況。 例如，您的企業可能希望根據查看的產品的價格確定訪問者。 但是，根據特定值定義各個段可能在管理上效率低下。 比較運算子通過基於價格閾值或範圍建立分段觸發器來幫助克服這一障礙。

## 比較運算子

可以使用以下比較運算子構建規則：

| 運算子 | 定義 |
|---|---|
| **==** | 等於 |
| **!=** | 不等於 |
| **>** | 大於 |
| **&lt;** | 小於 |
| **=>** | 大於/等於 |
| **&lt;=** | 小於/等於 |

## 命名運算子

可以使用以下命名運算子構建規則：

| 運算子 | 計算為 [!DNL True] 當 |
|---|---|
| **[!UICONTROL Contains]** | 鍵值對中的值 *包含* 由此運算子指定的字元。 |
| **[!UICONTROL Matcheswords]** | 鍵值對中的值 *匹配* 此運算子指定的模式。 |
| **[!UICONTROL Startswith]** | 鍵值對中的值 *開頭* 由此運算子指定的字元。 |
| **[!UICONTROL Endswith]** | 鍵值對中的值 *結尾* 此運算子指定的字元。 |
| **[!UICONTROL Matchesregex]** | 鍵值對中的值 *匹配* 規則運算式指定的模式。 [瞭解更多資訊](../../features/traits/trait-builder-regex.md) 關於使用規則運算式 [!UICONTROL Trait Builder]。 |

>[!MORELIKETHIS]
>
>* [特徵和區段產生器中的布林運算式](../../reference/boolean-expressions-tsb.md)
>* [瞭解TraitBuilder中的布爾表達式](../../reference/boolean-expressions-tsb.md)
>* [TraitBuilder表達式中的操作順序](../../features/traits/trait-operator-precedence.md)
>* [使用布林值和比較運算子的運算式範例](../../features/traits/trait-expression-samples.md)

