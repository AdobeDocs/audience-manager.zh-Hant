---
description: 您可以參照在運算式產生器程式碼編輯器中建立運算式的範例。
seo-description: 您可以參照在運算式產生器程式碼編輯器中建立運算式的範例。
seo-title: 使用布林和比較運算子的運算式範例
solution: Audience Manager
title: 使用布林和比較運算子的運算式範例
uuid: ee74c376-2099-4816-8694-43f58845a0ac
translation-type: tm+mt
source-git-commit: 92b75773d2bbe2f635d84bd5bffe625d2023b6cf

---


# Sample Expressions With Boolean and Comparison Operators {#sample-expressions-with-boolean-and-comparison-operators}

Examples you can refer to for creating expressions in the [!UICONTROL Expression Builder] code editor.

## Code Samples Overview {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Create your own trait rules with the [!UICONTROL Expression Builder] code editor. 下列範例可協助您開始使用。Some of the examples preface the *`key`* variable with `c_` to identify it as a user-defined variable. Include the `c_` prefix (or any other naming convention) for *`key`* variable if your event calls send data to [!DNL Audience Manager] using that syntax.

## Boolean Expressions {#boolean-expressions}

### AND範例

The rule establishes trait qualification requirements using Boolean [!UICONTROL AND] operators.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 若要符合資格，訪客必須符合 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_ make==「A」) AND(c_ model==「B」) AND AND(c_ search==1)</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">尋找特定的製作和模型。 </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">從搜尋結果頁面尋找產品(search=「1」或「true」)。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### OR範例

This rule establishes trait qualification requirements using [!DNL Boolean] [!UICONTROL OR] and [!UICONTROL AND] operators.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 若要符合資格，訪客必須符合 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a==「1」OR b==1) AND(c==new)</code> </td> 
   <td colname="col2"> Meet the conditions set by variables <code><i>a </i></code> or <code><i>b </i></code> and <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## 大於、小於、等於等範圍範例

此規則會使用範圍建立特徵資格要求。

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 若要符合資格，訪客必須符合 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(價格&gt;=1.00AND&lt;=100.00)</code> </td> 
   <td colname="col2"> 符合1.00與100.00之間的任何價格條件。 </td> 
  </tr> 
 </tbody> 
</table>