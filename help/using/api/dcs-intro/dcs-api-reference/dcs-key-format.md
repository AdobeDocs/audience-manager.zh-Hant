---
description: 發出呼叫時，DCS會接受標準或序列化格式的機碼值資料。 請參閱本節，了解如何格式化標準和序列化鍵值資料的資訊。
seo-description: 發出呼叫時，DCS會接受標準或序列化格式的機碼值資料。 請參閱本節，了解如何格式化標準和序列化鍵值資料的資訊。
seo-title: 格式化 DCS 呼叫中的索引鍵值配對
solution: Audience Manager
title: 格式化 DCS 呼叫中的索引鍵值配對
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
exl-id: ff2d9ff6-7d5b-4a0d-b831-5d9bc79b32a1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 12%

---

# 格式化 DCS 呼叫中的索引鍵值配對 {#formatting-key-value-pairs-in-dcs-calls}

進行呼叫時，[!DNL DCS]會接受標準或序列化格式的機碼值資料。 請參閱本節，了解如何格式化標準和序列化鍵值資料的資訊。

## 標準和序列化鍵值對{#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 鍵值類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>標準</b> </td> 
   <td colname="col2"> <p>標準索引鍵值組包含單一索引鍵和值。 此結構會將資料組織為個別的索引鍵值配對。 每個鍵都會明確指出，即使再次用來定義不同的值亦然。 這是將資料傳送至DCS的最常見方式。 </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>序列化</b> </td> 
   <td colname="col2"> <p>序列化的鍵值對由單一鍵和多個值組成。 這可以是組織資料的有效方式，但序列化的鍵值值配對需要特定符號，以分隔每個鍵值和每個鍵值集。 </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## 序列化鍵值對{#delimiters-separators}的分隔符和分隔符

使用序列化鍵值配對時，必須指定在這些變數內和之間分隔值的標籤。 Audience Manager需要下列分隔字元和分隔符號：

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 的需求 </th> 
   <th colname="col2" class="entry"> 符號 </th> 
   <th colname="col3" class="entry"> 分隔個人 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>分隔字元</b> </td> 
   <td colname="col2"> &amp;符號 </td> 
   <td colname="col3"> <p>機碼值組： </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>分隔符號</b> </td> 
   <td colname="col2"> 逗號 , </td> 
   <td colname="col3"> <p>機碼值組內的值： </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [將資料傳送至 DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
* [DCS支援的機碼值前置詞和變數](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
* [索引鍵值配對說明](../../../reference/key-value-pairs-explained.md)

