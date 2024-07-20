---
description: 使用邏輯運運算元將索引鍵值配對和回填特徵分組。
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: 支援的邏輯運運算元
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 4%

---

# 支援的邏輯運運算元 {#supported-logical-operators}

使用邏輯運運算元將索引鍵值配對和回填特徵分組。

## 支援的訊號搜尋運運算元 {#supported-operators-search}

使用下列支援的邏輯運運算元來搜尋機碼值組：

### 比較運運算元

| 運算子 | 定義 |
|---|---|
| **==** | 等於 |
| **>** | 大於 |
| **&lt;** | 小於 |
| **=>** | 大於/等於 |
| **&lt;=** | 小於/等於 |

### 已命名的運運算元

| 運算子 | 評估為[!DNL True]，當 |
|---|---|
| **[!UICONTROL Contains]** | 機碼值組&#x200B;*中的值包含此運運算元指定的*&#x200B;個字元。 |
| **[!UICONTROL Startswith]** | 機碼值組&#x200B;*中的值以此運運算元所指定的*&#x200B;個字元開頭。 |
| **[!UICONTROL Endswith]** | 機碼值組&#x200B;*中的值結尾是*&#x200B;此運運算元指定的字元。 |

## 特徵回填和預估的支援運運算元 {#supported-operators-backfilling}

您可以回填包含[!UICONTROL Signal Search]支援之任何運運算元之運算式的特徵。 除了這些運運算元之外，特徵回填和估計也支援[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL AND NOT]邏輯運運算元，這些運運算元用來結合回填特徵運算式中的索引鍵值組。
