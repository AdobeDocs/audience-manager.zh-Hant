---
description: 有關在運算式產生器程式碼編輯器中建立運算式的範例，請參閱。
seo-description: 有關在運算式產生器程式碼編輯器中建立運算式的範例，請參閱。
seo-title: 具有布林運算子和比較運算子的範例運算式
solution: Audience Manager
title: 具有布林運算子和比較運算子的範例運算式
uuid: ee74c376-2099-4816-8694-43f58845a0ac
translation-type: tm+mt
source-git-commit: 92b75773d2bbe2f635d84bd5bffe625d2023b6cf

---


# 具有布林運算子和比較運算子的範例運算式 {#sample-expressions-with-boolean-and-comparison-operators}

有關在代碼編輯器中建立表達式的示例， [!UICONTROL Expression Builder] 請參閱。

## 程式碼範例概觀 {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

使用程式碼編輯器建立您自己的 [!UICONTROL Expression Builder] 特徵規則。 下列範例可協助您開始使用。 有些範例會在變數前面加上 *`key`* ，以 `c_` 將其識別為使用者定義的變數。 如果您的 `c_` 事件呼叫使用該語法傳送資料 *`key`* 給，請加入變數的首碼(或任何其 [!DNL Audience Manager] 他命名慣例)。

## 布林運算式 {#boolean-expressions}

### AND範例

規則使用布林運算子建立特徵資格 [!UICONTROL AND] 要求。

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 若要符合資格，訪客必須 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A")AND(c_model=="B")AND(c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">尋找特定的品牌和型號。 </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">從搜尋結果頁面尋找產品（搜尋= "1"或"true"）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### OR範例

此規則使用和運算子建立特徵 [!DNL Boolean] 資 [!UICONTROL OR] 格 [!UICONTROL AND] 要求。

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 若要符合資格，訪客必須 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>（a== "1"或b=="1"）AND(c=="new")</code> </td> 
   <td colname="col2"> 符合變數a或 <code><i>b和 </i></code> c所設 <code><i>定的 </i></code> 條件 <code><i></i></code>。 </td> 
  </tr> 
 </tbody> 
</table>

## 範圍示例，其大於、小於、等於

此規則使用範圍建立特徵資格要求。

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 若要符合資格，訪客必須 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>（價格&gt;= 1.00，價格&lt;= 100.00）</code> </td> 
   <td colname="col2"> 符合1.00到100.00之間的任何價格條件。 </td> 
  </tr> 
 </tbody> 
</table>