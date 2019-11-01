---
description: 本文說明「特徵產生器」使用的比較運算子。
seo-description: 本文說明「特徵產生器」使用的比較運算子。
seo-title: 在特徵產生器中使用比較運算子
solution: Audience Manager
title: 在特徵產生器中使用比較運算子
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 在特徵產生器中使用比較運算子 {#working-with-comparison-operators-in-trait-builder}

本文說明比較運算子的使用方 [!UICONTROL Trait Builder]式。

## 比較運算子的用途

<!-- c_tb_comparison_operators.xml -->

比較運算子（或關聯運算子）可用來比較、測試或評估不同值之間的關係。 在建 [!UICONTROL Trait Builder]立訊號規則時，比較運算子可讓您測試不同鍵值對之間的關係。 例如，您可以建立訊號規則，為昂貴的相機購物者定義對象。 在這種情況下，您可以建立相機／價格金鑰值配對，並讓使用者在尋找價格等於或大於設定金額的相機時符合資格。

## 比較運算子的優點

當您需要評估並建立以多個值為基礎的特徵時，比較運算子會很有用。 從商品和服務的價格看，可以看出這個條件。 例如，您的企業可能想要根據訪客檢視的產品價格來識別訪客。 但是，根據特定值定義個別區段可能會在管理上缺乏效率。 比較運算子根據價格臨界值或範圍建立分段觸發，有助於克服這一障礙。

## 比較運算子

您可以使用下列比較運算子來建立規則：

| 運算元 | 定義 |
|---|---|
| **==** | 等於 |
| **!=** | 不等於 |
| **&gt;** | 大於 |
| **&lt;** | 小於 |
| **=&gt;** | 大於或等於 |
| **&lt;=** | 小於／等於 |

## 命名運算子

您可以使用下列命名運算子建立規則：

| 運算元 | 評估為 [!DNL True] 何時 |
|---|---|
| **[!UICONTROL Contains]** | 鍵值對中的值包含此運 *算符指* 定的字元。 |
| **[!UICONTROL Matcheswords]** | 鍵值對中的值與此運算子 *指定* 的模式匹配。 |
| **[!UICONTROL Startswith]** | 鍵值對中的值以此運算子 *指定的字元* 開頭。 |
| **[!UICONTROL Endswith]** | 鍵值對中的值以此運算子 *指定的字* 符結尾。 |
| **[!UICONTROL Matchesregex]** | 鍵值對中的值與規則運 *算式* 指定的模式匹配。 [進一步瞭解](../../features/traits/trait-builder-regex.md) ，如何在中使用規則運算式 [!UICONTROL Trait Builder]。 |

>[!MORELIKETHIS]
>
>* [特徵和區段產生器中的布林運算式](../../reference/boolean-expressions-tsb.md)
>* [瞭解TraitBuilder中的布林運算式](../../reference/boolean-expressions-tsb.md)
>* [TraitBuilder運算式中的運算順序](../../features/traits/trait-operator-precedence.md)
>* [具有布林運算子和比較運算子的範例運算式](../../features/traits/trait-expression-samples.md)

