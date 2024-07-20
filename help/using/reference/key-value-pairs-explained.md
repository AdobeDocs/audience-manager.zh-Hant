---
description: 定義並描述標準和序列化的索引鍵值配對。
keywords: 整合程式碼
seo-description: Defines and describes standard and serialized key-value pairs.
seo-title: Key-Value Pairs Explained
solution: Audience Manager
title: 索引鍵值配對說明
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: Reference
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 3%

---

# 索引鍵值配對說明{#key-value-pairs-explained}

定義並描述標準和序列化的索引鍵值配對。

<!-- 

c_key_value_explained.xml

 -->

機碼 — 值組包含兩個相關的資料元素：機碼，是定義資料集的常數（例如，性別、顏色、價格），以及值，是屬於該集的變數（例如，男性/女性、綠色、100）。 格式完整，機碼值組可能如下所示：

* `gender = male`
* `color = green`
* `price > 100`

## 標準和序列化的索引鍵值配對 {#standard-serialized-pairs}

目的地接受&#x200B;*`standard`*&#x200B;或&#x200B;*`serialized`*&#x200B;格式的機碼值資料。 標準格式會將資料整理為單獨的索引鍵/值組。 每個鍵都會明確指出，即使再次用來定義不同的值。 相較之下，序列化格式會將多個值壓縮為由單一索引鍵定義的一個集合。 此外，在序列化配對中，會使用特殊指示器來分隔索引鍵值集中的值。 最後，標準和序列化的機碼值可以包含單一或多個值。 下表提供標準和序列索引鍵值格式的範例。

| 格式化 | 單一金鑰 | 索引鍵值配對 |
|---|---|---|
| **標準** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **已序列化** | `x=1;2` | `x=1;2&y=3;4` |



## 鍵、分隔符號和分隔符號 {#keys-delimiters-separators}

使用序列化資料時，您必須指定在機碼值組之間&#x200B;*和*&#x200B;內&#x200B;*和*&#x200B;分隔值的字元。 索引鍵值配對中的元素定義如下：

* **機碼：**&#x200B;機碼值組中的唯一識別碼。
* **值分隔符號：**&#x200B;分隔個別的索引鍵/值組。
* **機碼值分隔符號：**&#x200B;將機碼與機碼值組中的值分開。
* **序列分隔符號：**&#x200B;分隔序列化機碼值組中的個別值。

## 標準和序列化的索引鍵值元素 {#standard-serialized-key-value-elements}


| 類型 | 範例 | 索引鍵 | 索引鍵值分隔符號 | 索引鍵值分隔字元 | 序列分隔符號 |
|---------|----------|---------|---------|----------|---------|
| **單一金鑰** （標準） | `x=1&x=2` | `x` | `=` | `&` | 不適用 |
| **機碼值組** （標準） | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | 不適用 |
| **單一金鑰** （序號） | `x=1;2;3` | `x` | `=` | 不適用 | `;` |
| **索引鍵值配對** （序列） | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
