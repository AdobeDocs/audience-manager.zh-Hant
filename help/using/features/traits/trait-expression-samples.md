---
description: 在運算式產生器程式碼編輯器中建立運算式時，可參考的範例。
seo-description: 在運算式產生器程式碼編輯器中建立運算式時，可參考的範例。
seo-title: 使用布林值和比較運算子的運算式範例
solution: Audience Manager
title: 使用布林值和比較運算子的運算式範例
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: 特徵
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 13%

---

# 使用布林值和比較運算子的運算式範例 {#sample-expressions-with-boolean-and-comparison-operators}

有關在[!UICONTROL Expression Builder]代碼編輯器中建立運算式的資訊，請參閱的示例。

## 程式碼範例概述{#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

使用[!UICONTROL Expression Builder]程式碼編輯器建立您自己的特徵規則。 下列範例可協助您快速上手。 有些範例在&#x200B;*`key`*&#x200B;變數前面加上`c_`，將其識別為使用者定義的變數。 如果您的事件呼叫使用該語法將資料傳送至[!DNL Audience Manager]，請加入`c_`變數的&#x200B;*`key`*&#x200B;首碼（或任何其他命名慣例）。

## 布爾表達式{#boolean-expressions}

### 和範例

規則使用布林值[!UICONTROL AND]運算子來建立特徵資格要求。

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 訪客必須符合資格 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">尋找特定品牌和型號。 </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">從搜尋結果頁面尋找產品（search = "1"或"true"）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### OR範例

此規則使用[!DNL Boolean] [!UICONTROL OR]和[!UICONTROL AND]運算子建立特徵資格要求。

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 訪客必須符合資格 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> 滿足變數<code><i>a </i></code>或<code><i>b </i></code>和<code><i>c </i></code>設定的條件。 </td> 
  </tr> 
 </tbody> 
</table>

## 範圍示例，其大於、小於、等於

此規則會使用範圍來建立特徵資格要求。

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 訪客必須符合資格 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> 在1.00到100.00之間滿足任何價格條件。 </td> 
  </tr> 
 </tbody> 
</table>
