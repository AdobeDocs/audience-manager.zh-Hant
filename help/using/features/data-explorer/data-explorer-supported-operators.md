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

## 支援的信號搜尋運算元 {#supported-operators-search}

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

| 運算元 | 評估為 [!DNL True] 何時 |
|---|---|
| **[!UICONTROL Contains]** | 鍵值對中的值包含此運 *算符指* 定的字元。 |
| **[!UICONTROL Startswith]** | 鍵值對中的值以此運算子 *指定的字元* 開頭。 |
| **[!UICONTROL Endswith]** | 鍵值對中的值以此運算子 *指定的字* 符結尾。 |

## 特徵回填與估計的支援算子 {#supported-operators-backfilling}

您可以回填包含運算式的特徵，這些運算式包含支援的任何運算子 [!UICONTROL Signal Search]。 除了這些運算子外，特徵回填和估計也支援 [!UICONTROL AND]、 [!UICONTROL OR][!UICONTROL AND NOT] 和邏輯運算子，用來在回填特徵運算式中組合索引鍵值對。