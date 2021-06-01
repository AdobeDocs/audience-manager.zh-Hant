---
description: 使用邏輯運算子來分組索引鍵值配對和回填特徵。
seo-description: 使用邏輯運算子來分組索引鍵值配對和回填特徵。
seo-title: 支援的邏輯運算子
title: 支援的邏輯運算子
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 10%

---

# 支援的邏輯運算子 {#supported-logical-operators}

使用邏輯運算子來分組索引鍵值配對和回填特徵。

## 支援的信號搜索{#supported-operators-search}運算子

使用下列支援的邏輯運算子來搜尋索引鍵值配對：

### 比較運算子

| 運算元 | 定義 |
|---|---|
| **==** | 等於 |
| **>** | 大於 |
| **&lt;** | 小於 |
| **=>** | 大於/等於 |
| **&lt;=** | 小於/等於 |

### 命名運算子

| 運算元 | 評估為[!DNL True]時 |
|---|---|
| **[!UICONTROL Contains]** | 鍵值對&#x200B;*中的值包含此運算子指定的*&#x200B;字元。 |
| **[!UICONTROL Startswith]** | 鍵值對&#x200B;*中的值以*&#x200B;字元開頭，由此運算子指定。 |
| **[!UICONTROL Endswith]** | 鍵值對&#x200B;*中的值以*&#x200B;結尾，此運算子指定的字元。 |

## 支援的特徵回填和估計運算子{#supported-operators-backfilling}

您可以回填包含運算式的特徵，這些運算式包含[!UICONTROL Signal Search]支援的任何運算子。 除了這些運算子外，特徵回填和估計也支援[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL AND NOT]邏輯運算子，用於結合回填特徵運算式中的索引鍵值配對。
