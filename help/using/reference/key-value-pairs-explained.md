---
description: 定義並描述標準和序列化索引鍵值配對。
keywords: 整合程式碼
seo-description: 定義並描述標準和序列化索引鍵值配對。
seo-title: 索引鍵值對說明
solution: Audience Manager
title: 索引鍵值對說明
uuid: f1435742-81ca-4964-8370-accf2 f1 c47 a
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Key-Value Pairs Explained{#key-value-pairs-explained}

定義並描述標準和序列化索引鍵值配對。

<!-- 

c_key_value_explained.xml

 -->

關鍵值配對包含兩個相關資料元素：索引鍵，它是一個常數，用來定義資料集(例如性別、顏色、價格)和值，這是屬於該組的變數(例如男性/女性、綠色、100)。完全成立後，關鍵值配對看起來就像這樣：

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format. 標準格式會將資料組織成個別的索引鍵值配對。每個索引鍵都明確表述，即使再次使用，也能定義不同的值。相反地，序列化格式會將多個值壓縮為單一索引鍵所定義的一組。此外，在序列化的配對中，使用特殊指標來分隔機碼值集內的值。最後，標準和序列化索引鍵值可以包含單一或多個值。下表提供標準和串行鍵值格式的範例。

| 格式設定 | 單一按鍵 | 索引鍵值配對 |
|---|---|---|
| **標準** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **序列化序列化** | `x=1;2` | `x=1;2&y=3;4` |



## Keys, Delimiters, and Separators {#keys-delimiters-separators}

When working with serialized data, you must specify the characters that separate values *within* and *between* the key-value pairs. 索引鍵值配對中的元素定義如下：

* **索引鍵：** 索引鍵值配對中的唯一識別碼。
* **值分隔字元：** 分隔個別索引鍵值配對。
* **索引鍵值分隔符號：** 將索引鍵與索引鍵值配對內的值分隔。
* **串行分隔符號：** 分隔序列化索引鍵值配對中的個別值。

## Standard and Serialized Key-Value Elements {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 類型 </th> 
   <th colname="col2" class="entry"> 範例 </th> 
   <th colname="col3" class="entry"> 金鑰 </th> 
   <th colname="col4" class="entry"> 索引鍵值分隔符號 </th> 
   <th colname="col5" class="entry"> 索引鍵值分隔字元 </th> 
   <th colname="col6" class="entry"> 序列分隔符號 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>單一按鍵</b> <p>(標準) </p> </td> 
   <td colname="col2"> <code> x=1&amp; x=2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> 不適用 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>索引鍵值配對</b> <p>(標準) </p> </td> 
   <td colname="col2"> <code> x=1&amp; x=2&amp; y=3&amp; y=4 </code> </td> 
   <td colname="col3"> x，y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>單一按鍵</b> <p>(序號) </p> </td> 
   <td colname="col2"> <code> x=1；2；3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> 不適用 </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>索引鍵值配對</b> (序號) </td> 
   <td colname="col2"> <code> x=1；&amp; y=3；4 </code> </td> 
   <td colname="col3"> x，y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

