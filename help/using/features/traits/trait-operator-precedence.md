---
description: 特性生成器根據下面列出的從高到低的優先順序計算表達式。 由高優先順序運算子定義的特徵元素首先被評估，而不是其它優先順序運算子。 此部分按優先順序從高到低對每個運算子進行排序。
seo-description: Trait Builder evaluates expressions according to the order-of-operations listed below, from high to low precedence. Trait elements defined by high-precedence operators are evaluated first, before other precedence operators. This section ranks each operator according to precedence, from high to low.
seo-title: Order of Operations in Trait Builder
solution: Audience Manager
title: 特徵產生器中的作業順序
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
exl-id: 90700479-4a8e-4a07-81ef-2e9d8a1d9f15
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 13%

---

# 特徵產生器中的作業順序 {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] 根據下面列出的操作順序（從高到低優先順序）計算表達式。 由高優先順序運算子定義的特徵元素首先被評估，而不是其它優先順序運算子。 此部分按優先順序從高到低對每個運算子進行排序。

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 運算子優先順序 </th> 
   <th colname="col2" class="entry"> 符號 </th> 
   <th colname="col3" class="entry"> 意見 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 圓括弧 </td> 
   <td colname="col2"> () </td> 
   <td colname="col3"> 括弧中的表達式總是先計算，然後按優先順序排列。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 比較運算子 </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> 接下來計算小於、大於、小於/等於、大於/等於。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 等式運算子 </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> 等於、不等於在前面的運算子後計算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1">布爾型 <span class="wintitle"> 和</span> </td> 
   <td colname="col2"><span class="wintitle"> 和</span> </td> 
   <td colname="col3" morerows="1"> 不適用 </td> 
  </tr> 
  <tr> 
   <td colname="col1">布爾型 <span class="wintitle"> 或</span> </td> 
   <td colname="col2"><span class="wintitle"> 或</span> </td> 
   <td colname="col3" morerows="1"> 不適用 </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用布爾表達式(AND、OR、NOT)](../../reference/boolean-expressions-tsb.md)
>* [在TraitBuilder中使用比較運算子](../../features/traits/trait-comparison-operators.md)

