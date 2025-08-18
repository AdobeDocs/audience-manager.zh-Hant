---
description: 進行呼叫時，DCS會接受標準或序列化格式的機碼值資料。 如需有關如何格式化標準與序列化鍵值資料的資訊，請參閱本節。
seo-description: When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.
seo-title: Formatting Key-Value Pairs in DCS Calls
solution: Audience Manager
title: 格式化DCS呼叫中的索引鍵值配對
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
exl-id: ff2d9ff6-7d5b-4a0d-b831-5d9bc79b32a1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# 格式化DCS呼叫中的索引鍵值配對 {#formatting-key-value-pairs-in-dcs-calls}

進行呼叫時，[!DNL DCS]會接受標準或序列化格式的機碼值資料。 如需有關如何格式化標準與序列化鍵值資料的資訊，請參閱本節。

## 標準和序列化的索引鍵值配對 {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 索引鍵值型別 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>標準</b> </td> 
   <td colname="col2"> <p>標準索引鍵/值組包含單一索引鍵和值。 此結構會將資料整理到單獨的索引鍵/值配對中。 每個鍵都會明確指出，即使再次用來定義不同的值。 這是將資料傳送至DCS的最常見方式。 </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>已序列化</b> </td> 
   <td colname="col2"> <p>序列化的索引鍵/值組包含單一索引鍵和多個值。 這是組織資料的有效方式，但序列化的索引鍵值配對需要特定符號來分隔每個索引鍵和每個索引鍵值集。 </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## 序列化索引鍵值配對的分隔符號和分隔符號 {#delimiters-separators}

使用序列化索引鍵值配對，您必須指定標籤來分隔這些變數內和之間的值。 Audience Manager需要下列分隔符號和分隔符號：

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 需求 </th> 
   <th colname="col2" class="entry"> 符號 </th> 
   <th colname="col3" class="entry"> 分隔個人 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>分隔符號</b> </td> 
   <td colname="col2"> &amp;符號&amp; </td> 
   <td colname="col3"> <p>索引鍵值配對： </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>分隔符號</b> </td> 
   <td colname="col2"> 逗號， </td> 
   <td colname="col3"> <p>機碼值組內的值： </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [將資料傳送至 DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [DCS支援的索引鍵值首碼和變數](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [索引鍵值配對說明](../../../reference/key-value-pairs-explained.md)
