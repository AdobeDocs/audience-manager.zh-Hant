---
description: 特徵產生器根據下列操作順序評估運算式，從高到低優先順序。由高階運算子定義的特徵元素先被評估，再優先於其他優先運算子。此區域依優先順序(從高到低)排名每個運算子。
seo-description: 特徵產生器根據下列操作順序評估運算式，從高到低優先順序。由高階運算子定義的特徵元素先被評估，再優先於其他優先運算子。此區域依優先順序(從高到低)排名每個運算子。
seo-title: Trait Builder中的操作順序
solution: Audience Manager
title: Trait Builder中的操作順序
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Order of Operations in Trait Builder {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] 根據下列操作順序評估運算式，從高到低優先順序。由高階運算子定義的特徵元素先被評估，再優先於其他優先運算子。此區域依優先順序(從高到低)排名每個運算子。

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 營運商優先順序 </th> 
   <th colname="col2" class="entry"> 符號符號 </th> 
   <th colname="col3" class="entry"> 意見 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 括弧 </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> 括弧中的運算式一律會先評估，並遵循優先順序。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 比較運算子 </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> 小於(小於)小於(小於)小於/等於(大於/等於)下一步評估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 平等運算子 </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> 等於(不等於)則會在先前運算子後評估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> AND</span> </td> 
   <td colname="col3" morerows="1"> 不適用 </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> 或</span> </td> 
   <td colname="col3" morerows="1"> 不適用 </td> 
  </tr> 
 </tbody>
</table>

>[!MORE_贊_ this]
>
>* [在TraitBuilder中使用布林運算式(AND、OR、NOT)](../../reference/boolean-expressions-tsb.md)
>* [使用TraitBuilder中的比較運算子](../../features/traits/trait-comparison-operators.md)

