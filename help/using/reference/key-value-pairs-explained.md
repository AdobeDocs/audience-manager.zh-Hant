---
description: 定義並說明標準和序號的金鑰值配對。
keywords: integration code
seo-description: 定義並說明標準和序號的金鑰值配對。
seo-title: 索引鍵值配對說明
solution: Audience Manager
title: 索引鍵值配對說明
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: reference
translation-type: tm+mt
source-git-commit: 5d6983f5308f1dfd4560ee1b38bcaee3ca6e422f
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 6%

---


# 索引鍵值配對說明{#key-value-pairs-explained}

定義並說明標準和序號的金鑰值配對。

<!-- 

c_key_value_explained.xml

 -->

鍵值對由兩個相關的資料元素組成：一個鍵，它是定義資料集（例如性別、顏色、價格）的常數，一個值是屬於該集的變數（例如，男／女、綠色、100）。 完整格式的索引鍵值對可能如下所示：

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

目標接受或格式的鍵 *`standard`* 值 *`serialized`* 資料。 標準格式將資料組織成個別的索引鍵值對。 每個鍵都被明確指定，即使再次用於定義不同的值。 相反地，序列化的格式化會將多個值濃縮成由單一鍵定義的一組值。 此外，在序列化對中，使用特殊指示符來分隔鍵值集內的值。 最後，標準和序號的索引鍵值可包含單一或多個值。 下表提供標準和序號鍵值格式的範例。

| 格式 | 單鍵 | 鍵值對 |
|---|---|---|
| **標準** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **序列化** | `x=1;2` | `x=1;2&y=3;4` |



## 鍵、分隔字元和分隔字元 {#keys-delimiters-separators}

使用序列化資料時，您必須指定在鍵值配對 *內**和之* 間分隔值的字元。 鍵值對中的元素定義如下：

* **索引鍵：** 鍵值對中的唯一標識符。
* **值分隔字元：** 分離個別的鍵值對。
* **鍵值分隔符號：** 將鍵與鍵值對中的值分隔。
* **序號分隔符號：** 分隔序列化索引鍵值對中的個別值。

## 標準和序號的關鍵值元素 {#standard-serialized-key-value-elements}


| 類型 | 範例 | 金鑰 | 鍵值分隔符號 | 鍵值分隔字元 | 序列分隔符號 |
---------|----------|---------|---------|----------|---------
| **單鍵** （標準） | `x=1&x=2` | `x` | `=` | `&` | 不適用 |
| **鍵值配對** （標準） | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | 不適用 |
| **單鍵** （串列） | `x=1;2;3` | `x` | `=` | 不適用 | `;` |
| **金鑰值配對** （串列） | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
