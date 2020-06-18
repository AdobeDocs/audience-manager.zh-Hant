---
description: 進行呼叫時，DCS會接受標準或序號格式的金鑰值資料。 請檢閱本節，以瞭解如何設定標準和序號關鍵值資料的格式。
seo-description: 進行呼叫時，DCS會接受標準或序號格式的金鑰值資料。 請檢閱本節，以瞭解如何設定標準和序號關鍵值資料的格式。
seo-title: 格式化 DCS 呼叫中的索引鍵值配對
solution: Audience Manager
title: 格式化 DCS 呼叫中的索引鍵值配對
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 12%

---


# 格式化 DCS 呼叫中的索引鍵值配對 {#formatting-key-value-pairs-in-dcs-calls}

進行呼叫時，會接 [!DNL DCS] 受標準或序號格式的金鑰值資料。 請檢閱本節，以瞭解如何設定標準和序號關鍵值資料的格式。

## Standard and Serialized Key-Value Pairs {#standard-serialized}

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
   <td colname="col2"> <p>標準鍵值對由單鍵和值組成。 此結構將資料組織成個別的索引鍵值對。 每個金鑰都會明確指定，即使再次用來定義不同的值亦然。 這是傳送資料至DCS的最常見方式。 </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>序列化</b> </td> 
   <td colname="col2"> <p>序列化鍵值對由單鍵和多個值組成。 這可以是組織資料的有效方式，但序號的索引鍵值配對需要特定符號來分隔每個索引鍵和每個索引鍵值集。 </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## 序列化鍵值對的分隔符和分隔符 {#delimiters-separators}

對於序列化的鍵值配對，您必須指定這些變數內和之間分隔值的標籤。 Audience Manager需要下列分隔字元和分隔符號：

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 需求 </th> 
   <th colname="col2" class="entry"> 符號 </th> 
   <th colname="col3" class="entry"> 分離個人 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>分隔字元</b> </td> 
   <td colname="col2"> &amp;符號與 </td> 
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
>* [DCS支援的關鍵值字首碼和變數](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [索引鍵值配對說明](../../../reference/key-value-pairs-explained.md)

