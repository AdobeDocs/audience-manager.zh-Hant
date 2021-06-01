---
description: 本文說明特徵產生器使用的比較運算子。
seo-description: 本文說明特徵產生器使用的比較運算子。
seo-title: 在特徵產生器中使用比較運算子
solution: Audience Manager
title: 在特徵產生器中使用比較運算子
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: 特徵
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 12%

---

# 在特徵產生器中使用比較運算子 {#working-with-comparison-operators-in-trait-builder}

本文描述[!UICONTROL Trait Builder]使用的比較運算子。

## 比較運算子的用途

<!-- c_tb_comparison_operators.xml -->

比較運算子（或關係運算子）用於比較、測試或評估不同值之間的關係。 在[!UICONTROL Trait Builder]中，建立訊號規則時，比較運算子可讓您測試不同索引鍵值組之間的關係。 例如，您可以建立訊號規則，為昂貴的相機購物者定義對象。 在此情況下，如果用戶已查找價格等於或大於設定金額的照相機，則可以建立照相機/價格鍵值對，並對其進行資格鑑定。

## 比較運算子的優點

當您需要根據多個值來評估和建立特徵時，比較運算子很實用。 觀察商品和服務的價格可以說明這一情況。 例如，您的企業可能想要根據訪客檢視的產品價格來識別訪客。 不過，根據特定值定義個別區段可能在管理上效率不彰。 比較運算子會根據價格臨界值或範圍建立分段觸發器，以協助克服此障礙。

## 比較運算子

您可以使用下列比較運算子來建立規則：

| 運算元 | 定義 |
|---|---|
| **==** | 等於 |
| **!=** | 不等於 |
| **>** | 大於 |
| **&lt;** | 小於 |
| **=>** | 大於/等於 |
| **&lt;=** | 小於/等於 |

## 命名運算子

您可以使用下列命名運算子來建立規則：

| 運算元 | 評估為[!DNL True]時 |
|---|---|
| **[!UICONTROL Contains]** | 鍵值對&#x200B;*中的值包含此運算子指定的*&#x200B;字元。 |
| **[!UICONTROL Matcheswords]** | 鍵值對&#x200B;*中的值與*&#x200B;此運算子指定的模式匹配。 |
| **[!UICONTROL Startswith]** | 鍵值對&#x200B;*中的值以*&#x200B;字元開頭，由此運算子指定。 |
| **[!UICONTROL Endswith]** | 鍵值對&#x200B;*中的值以*&#x200B;結尾，此運算子指定的字元。 |
| **[!UICONTROL Matchesregex]** | 鍵值對&#x200B;*中的值與規則運算式指定的模式*&#x200B;匹配。 [進一](../../features/traits/trait-builder-regex.md) 步了解在中使用規則運算 [!UICONTROL Trait Builder]式。 |

>[!MORELIKETHIS]
>
>* [特徵和區段產生器中的布林運算式](../../reference/boolean-expressions-tsb.md)
* [了解TraitBuilder中的布林運算式](../../reference/boolean-expressions-tsb.md)
* [TraitBuilder運算式中的作業順序](../../features/traits/trait-operator-precedence.md)
* [使用布林值和比較運算子的運算式範例](../../features/traits/trait-expression-samples.md)

