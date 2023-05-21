---
description: 有關在表達式生成器代碼編輯器中建立表達式的示例，請參閱。
seo-description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-title: Sample Expressions With Boolean and Comparison Operators
solution: Audience Manager
title: 使用布林值和比較運算子的運算式範例
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 10%

---

# 使用布林值和比較運算子的運算式範例 {#sample-expressions-with-boolean-and-comparison-operators}

有關在中建立表達式的示例，請參閱 [!UICONTROL Expression Builder] 代碼編輯器。

## 代碼示例概述 {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

建立您自己的特質規則 [!UICONTROL Expression Builder] 代碼編輯器。 以下示例可幫助您開始。 序 *`key`* 變數 `c_` 將其標識為用戶定義的變數。 包括 `c_` 前置詞（或任何其他命名約定） *`key`* 變數(如果事件調用將資料發送到 [!DNL Audience Manager] 用那句語法。

## 布爾表達式 {#boolean-expressions}

### 和示例

該規則使用布爾值確定特徵資格要求 [!UICONTROL AND] 運算子。

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 要獲得資格，訪客必須 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">查找特定的品牌和型號。 </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">從搜索結果頁面查找產品（搜索=「1」或「true」）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### OR示例

此規則使用 [!DNL Boolean] [!UICONTROL OR] 和 [!UICONTROL AND] 運算子。

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 要獲得資格，訪客必須 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> 滿足由變數設定的條件 <code><i>a </i></code> 或 <code><i>b </i></code> 和 <code><i>c </i></code>。 </td> 
  </tr> 
 </tbody> 
</table>

## 大於、小於、等於的範圍示例

此規則使用範圍確定特質資格要求。

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 要獲得資格，訪客必須 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> 滿足1.00到100.00之間的任何價格條件。 </td> 
  </tr> 
 </tbody> 
</table>
