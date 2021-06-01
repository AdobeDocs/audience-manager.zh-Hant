---
description: 特徵產生器會根據下列作業順序，從高到低優先順序來評估運算式。 由高優先順序運算子定義的特徵元素會先評估，再評估其他優先順序運算子。 本節根據優先順序，從高到低對每個運算子進行排名。
seo-description: 特徵產生器會根據下列作業順序，從高到低優先順序來評估運算式。 由高優先順序運算子定義的特徵元素會先評估，再評估其他優先順序運算子。 本節根據優先順序，從高到低對每個運算子進行排名。
seo-title: 特徵產生器中的作業順序
solution: Audience Manager
title: 特徵產生器中的作業順序
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: 特徵
exl-id: 90700479-4a8e-4a07-81ef-2e9d8a1d9f15
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 13%

---

# 特徵產生器中的作業順序 {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] 根據下列作業順序，從高到低優先順序評估運算式。由高優先順序運算子定義的特徵元素會先評估，再評估其他優先順序運算子。 本節根據優先順序，從高到低對每個運算子進行排名。

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
   <td colname="col1"> 括弧 </td> 
   <td colname="col2"> () </td> 
   <td colname="col3"> 括弧中的運算式一律會先計算，並遵循優先順序。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 比較運算子 </td> 
   <td colname="col2"> &lt;&gt; &lt;&gt;= </td> 
   <td colname="col3"> 接下來評估小於、大於、小於/等於、大於/等於。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 相等運算子 </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> 在前一個運算子後，會評估等於、不等於。 </td> 
  </tr> 
  <tr> 
   <td colname="col1">布林值<span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> 和</span> </td> 
   <td colname="col3" morerows="1"> 不適用 </td> 
  </tr> 
  <tr> 
   <td colname="col1">布林值<span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> 或</span> </td> 
   <td colname="col3" morerows="1"> 不適用 </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用布林運算式(AND、OR、NOT)](../../reference/boolean-expressions-tsb.md)
* [在TraitBuilder中使用比較運算子](../../features/traits/trait-comparison-operators.md)

