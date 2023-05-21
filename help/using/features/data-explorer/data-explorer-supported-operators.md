---
description: 使用邏輯運算子對鍵值對和回填特徵進行分組。
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: 支援的邏輯運算子
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 8%

---

# 支援的邏輯運算子 {#supported-logical-operators}

使用邏輯運算子對鍵值對和回填特徵進行分組。

## 支援的信號搜索運算子 {#supported-operators-search}

使用以下受支援的邏輯運算子搜索鍵值對：

### 比較運算子

| 運算子 | 定義 |
|---|---|
| **==** | 等於 |
| **>** | 大於 |
| **&lt;** | 小於 |
| **=>** | 大於/等於 |
| **&lt;=** | 小於/等於 |

### 命名運算子

| 運算子 | 計算為 [!DNL True] 當 |
|---|---|
| **[!UICONTROL Contains]** | 鍵值對中的值 *包含* 由此運算子指定的字元。 |
| **[!UICONTROL Startswith]** | 鍵值對中的值 *開頭* 由此運算子指定的字元。 |
| **[!UICONTROL Endswith]** | 鍵值對中的值 *結尾* 此運算子指定的字元。 |

## 特徵回填和估計的支援算子 {#supported-operators-backfilling}

可以回填包含包含由支援的任何運算子的表達式的特徵 [!UICONTROL Signal Search]。 除了這些算子外，特徵回填和估計也支援 [!UICONTROL AND]。 [!UICONTROL OR], [!UICONTROL AND NOT] 邏輯運算子，用於在回填特徵表達式中組合鍵值對。
