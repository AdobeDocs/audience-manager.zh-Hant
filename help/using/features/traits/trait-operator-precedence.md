---
description: 特徵產生器會根據下列作業順序評估運算式，從高優先順序到低優先順序。 系統會先評估由高優先順序運運算元定義的特徵元素，然後再評估其他優先順序運運算元。 本節會根據優先順序（從高到低）來排列每個運運算元。
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
ht-degree: 3%

---

# 特徵產生器中的作業順序 {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder]會根據下列運算順序評估運算式，從高優先順序到低優先順序。 系統會先評估由高優先順序運運算元定義的特徵元素，然後再評估其他優先順序運運算元。 本節會根據優先順序（從高到低）來排列每個運運算元。

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 運運算元優先順序 </th> 
   <th colname="col2" class="entry"> 符號 </th> 
   <th colname="col3" class="entry"> 意見 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 括弧 </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> 括弧中的運算式一律會先計算並遵循優先順序。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 比較運運算元 </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> 接下來會評估「小於」、「大於」、「小於/等於」、「大於/等於」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 相等運運算元 </td> 
   <td colname="col2"> ==！= </td> 
   <td colname="col3"> 等於、不等於會在先前的運運算元之後評估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1">布林值<span class="wintitle">和</span> </td> 
   <td colname="col2"><span class="wintitle">和</span> </td> 
   <td colname="col3" morerows="1"> 不適用 </td> 
  </tr> 
  <tr> 
   <td colname="col1">布林值<span class="wintitle">或</span> </td> 
   <td colname="col2"><span class="wintitle">或</span> </td> 
   <td colname="col3" morerows="1"> 不適用 </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [在TraitBuilder](../../reference/boolean-expressions-tsb.md)中使用布林運算式(AND、OR、NOT)
>* [在TraitBuilder中使用比較運運算元](../../features/traits/trait-comparison-operators.md)
