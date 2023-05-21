---
description: 定義和描述標準和序列化鍵值對。
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
source-wordcount: '267'
ht-degree: 6%

---

# 索引鍵值配對說明{#key-value-pairs-explained}

定義和描述標準和序列化鍵值對。

<!-- 

c_key_value_explained.xml

 -->

鍵值對由兩個相關資料元素組成：鍵，它是定義資料集（例如性別、顏色、價格）的常數，以及值，它是屬於該集的變數（例如，男/女，綠色，100）。 鍵值對完全形成，可能如下所示：

* `gender = male`
* `color = green`
* `price > 100`

## 標準和序列化鍵值對 {#standard-serialized-pairs}

目標接受中的鍵值資料 *`standard`* 或 *`serialized`* 的子菜單。 標準格式將資料組織成單獨的鍵值對。 每個鍵都被顯式地表示，即使再次用於定義不同的值時也是如此。 相反，序列化格式將多個值壓縮為由單個鍵定義的一個集。 此外，在序列化對中，使用特殊指示符來分隔鍵值集中的值。 最後，標準鍵值和序列化鍵值可以包含單個或多個值。 下表提供了標準和串列鍵值格式的示例。

| 格式 | 單鍵 | 鍵值對 |
|---|---|---|
| **標準** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **序列化** | `x=1;2` | `x=1;2&y=3;4` |



## 鍵、分隔符和分隔符 {#keys-delimiters-separators}

使用序列化資料時，必須指定分離值的字元 *內* 和 *間* 鍵值對。 鍵值對中的元素定義如下：

* **鍵：** 鍵值對中的唯一標識符。
* **值分隔符：** 分離單個鍵值對。
* **鍵值分隔符：** 將鍵與鍵值對中的值分離。
* **序列分隔符：** 分離序列化鍵值對中的單個值。

## 標準和序列化鍵值要素 {#standard-serialized-key-value-elements}


| 類型 | 範例 | 金鑰 | 鍵值分隔符 | 鍵值分隔符 | 序列分隔符 |
|---------|----------|---------|---------|----------|---------|
| **單鍵** （標準） | `x=1&x=2` | `x` | `=` | `&` | 不適用 |
| **鍵值對** （標準） | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | 不適用 |
| **單鍵** （串列） | `x=1;2;3` | `x` | `=` | 不適用 | `;` |
| **鍵值對** （串列） | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
