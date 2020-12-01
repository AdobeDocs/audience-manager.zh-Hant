---
description: 使用邏輯運算子來分組索引鍵值配對和回填特徵。
seo-description: 使用邏輯運算子來分組索引鍵值配對和回填特徵。
seo-title: 支援的邏輯運算子
title: 支援的邏輯運算子
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 9%

---


# 支援的邏輯運算子 {#supported-logical-operators}

使用邏輯運算子來分組索引鍵值配對和回填特徵。

## 信號搜索的支援運算子{#supported-operators-search}

使用以下支援的邏輯運算子搜索鍵值對：

### 比較運算子

| 運算元 | 定義 |
|---|---|
| **==** | 等於 |
| **>** | 大於 |
| **&lt;** | 小於 |
| **=>** | 大於或等於 |
| **&lt;=** | 小於／等於 |

### 命名運算子

| 運算元 | 評估為[!DNL True]時 |
|---|---|
| **[!UICONTROL Contains]** | 鍵值對&#x200B;*中的值包含由此運算子指定的*&#x200B;字元。 |
| **[!UICONTROL Startswith]** | 鍵值對&#x200B;*中的值以此運算子指定的*&#x200B;字元開頭。 |
| **[!UICONTROL Endswith]** | 鍵值對&#x200B;*中的值以*&#x200B;結尾，該運算子指定的字元為結尾。 |

## 特徵回填和估計{#supported-operators-backfilling}的支援運算子

您可以回填包含包含[!UICONTROL Signal Search]支援任何運算子的運算式的特徵。 除了這些運算子外，特徵回填和估計也支援[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL AND NOT]邏輯運算子，用於在回填特徵運算式內結合索引鍵值對。