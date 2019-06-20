---
description: 使用邏輯運算子將索引鍵值配對和回填特徵分組。
seo-description: 使用邏輯運算子將索引鍵值配對和回填特徵分組。
seo-title: 支援的邏輯運算子
title: 支援的邏輯運算子
uuid: 645fcp6f-50ac-49bc-8bc-9c799c749cf8f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Supported Logical Operators {#supported-logical-operators}

使用邏輯運算子將索引鍵值配對和回填特徵分組。

## Supported Operators for Signal Search {#supported-operators-search}

使用下列支援的邏輯運算子來搜尋索引鍵值配對：

### 比較運算子

| 運算元 | 定義 |
|---|---|
| **==** | 等於 |
| **&gt;** | 大於 |
| **&lt;** | 小於 |
| **=&gt;** | 大於/等於 |
| **&lt;=** | 小於/等於 |

### 具名運算子

| 運算元 | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |

## Supported Operators for Trait Backfilling and Estimation {#supported-operators-backfilling}

You can backfill traits that include expressions containing any of the operators supported by [!UICONTROL Signal Search]. In addition to these operators, trait backfilling and estimation also support the [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL AND NOT] logical operators, used to combine key-value pairs within the backfilled trait expressions.