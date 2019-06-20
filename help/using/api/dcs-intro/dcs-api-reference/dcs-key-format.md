---
description: 在進行呼叫時，DCS會接受標準或序列化格式的機碼值資料。請參閱本節以瞭解如何格式化標準和序列化關鍵值資料的相關資訊。
seo-description: 在進行呼叫時，DCS會接受標準或序列化格式的機碼值資料。請參閱本節以瞭解如何格式化標準和序列化關鍵值資料的相關資訊。
seo-title: 在DCS呼叫中格式化索引鍵值配對
solution: Audience Manager
title: 在DCS呼叫中格式化索引鍵值配對
uuid: af02f2a1-4388-4074-ab4 e-66ee82023 f1 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Formatting Key-Value Pairs in DCS Calls {#formatting-key-value-pairs-in-dcs-calls}

When making a call, the [!UICONTROL DCS] accepts key-value data in standard or serialized format. 請參閱本節以瞭解如何格式化標準和序列化關鍵值資料的相關資訊。

## Standard and Serialized Key-Value Pairs {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 索引鍵值類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>標準</b> </td> 
   <td colname="col2"> <p>標準索引鍵值對包含單一索引鍵和值。此結構可將資料組織成個別的索引鍵值配對。每個索引鍵都會明確表述，即使再次使用它也能定義不同的值。這是傳送資料至DCS最常見的方式。 </p> </td>
   <td colname="col3"> <code> key1= val1&amp; key2= val&amp; key3= val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>序列化序列化</b> </td> 
   <td colname="col2"> <p>序列化索引鍵值組包含單一索引鍵和多個值。這可以是組織資料的有效方式，但是序列化索引鍵值對需要特定符號來分隔每個索引鍵和每個索引鍵值集。 </p> </td> 
   <td colname="col3"> <code> key1= val1，val2，val3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimiters and Separators for Serialized Key-Value Pairs {#delimiters-separators}

使用序列化索引鍵值配對，您必須指定在這些變數內和之間分隔值的標記。Audience Manager需要下列分隔字元和分隔符號：

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 需求 </th> 
   <th colname="col2" class="entry"> 符號符號 </th> 
   <th colname="col3" class="entry"> 區隔個別區隔 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>分隔符號</b> </td> 
   <td colname="col2"> Amperand&amp;&amp; </td> 
   <td colname="col3"> <p>索引鍵值配對： </p> <p><code> key1= val1&amp; key2= val2，val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>分隔符號</b> </td> 
   <td colname="col2"> 逗號 , </td> 
   <td colname="col3"> <p>索引鍵值配對中的值： </p> <p><code> key1= val1，val2，val&amp; key2= ValA，ValB，ValC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_贊_ this]
>
>* [傳送資料至DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [DCS支援的索引鍵值首碼和變數](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [索引鍵值對說明](../../../reference/key-value-pairs-explained.md)

