---
description: 在進行呼叫時，DCS接受標準或序列化格式的鍵值資料。 有關如何格式化標準值和序列化鍵值資料的資訊，請查看本節。
seo-description: When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.
seo-title: Formatting Key-Value Pairs in DCS Calls
solution: Audience Manager
title: 格式化 DCS 呼叫中的索引鍵值配對
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
exl-id: ff2d9ff6-7d5b-4a0d-b831-5d9bc79b32a1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 11%

---

# 格式化 DCS 呼叫中的索引鍵值配對 {#formatting-key-value-pairs-in-dcs-calls}

打電話時， [!DNL DCS] 接受標準或序列化格式的鍵值資料。 有關如何格式化標準值和序列化鍵值資料的資訊，請查看本節。

## 標準和序列化鍵值對 {#standard-serialized}

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
   <td colname="col2"> <p>標準鍵值對由單個鍵和值組成。 此結構將資料組織為單獨的鍵值對。 每個鍵都被明確地表示，即使它再次用於定義不同的值。 這是將資料發送到DCS的最常見方法。 </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>序列化</b> </td> 
   <td colname="col2"> <p>序列化鍵值對由單個鍵和多個值組成。 這可以是組織資料的一種有效方法，但序列化的鍵值對需要特定的符號來分隔每個鍵和每個鍵值集。 </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## 序列化鍵值對的分隔符和分隔符 {#delimiters-separators}

對於序列化的鍵值對，必須指定這些變數內和變數之間分隔值的標籤。 Audience Manager需要以下分隔符和分隔符：

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 對 </th> 
   <th colname="col2" class="entry"> 符號 </th> 
   <th colname="col3" class="entry"> 分隔 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>分隔符</b> </td> 
   <td colname="col2"> &amp;和號 </td> 
   <td colname="col3"> <p>鍵值對： </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>分隔符號</b> </td> 
   <td colname="col2"> 逗號 , </td> 
   <td colname="col3"> <p>鍵值對中的值： </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [將資料傳送至 DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [DCS支援的鍵值前置詞和變數](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [索引鍵值配對說明](../../../reference/key-value-pairs-explained.md)

