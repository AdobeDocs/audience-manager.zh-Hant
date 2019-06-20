---
description: 本文說明Audience Manager特徵和區段工具如何使用布林運算式AND、OR和NOT。
seo-description: 本文說明Audience Manager特徵和區段工具如何使用布林運算式AND、OR和NOT。
seo-title: 特徵和區段產生器中的布林運算式
solution: Audience Manager
title: 特徵和區段產生器中的布林運算式
uuid: 14f02d3f-4c84-41Fe-bc91-b34 f0 d49574 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Boolean Expressions in Trait and Segment Builder{#boolean-expressions-in-trait-and-segment-builder}

本文說明Audience Manager特徵和區段工具如何使用布林運算式AND、OR和NOT。

<!-- 

c_tb_boolean.xml

 -->

**布林運算式**

布林邏輯是使用一些基本運算式(或運算子)來判斷陳述式是否為true或false的代數分支。The most common operators are [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]. 這些運算式組合可協助您建立特別適合您資料需求的特徵或區段資格規則。下圖顯示基本布林運算式如何運作。

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT] 運算元使用隱含的「和」條件，有時會寫入為 [!UICONTROL AND NOT]。

**如何在特徵和區段產生器中使用布林運算式**

您可以使用布林運算式建立特徵和區段資格規則。The table below describes general best practices for creating qualification criteria with [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 運算式 </th> 
   <th colname="col2" class="entry"> 使用它來建立 </th> 
   <th colname="col3" class="entry"> 若要符合資格 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> AND</span></b> </p> </td> 
   <td colname="col2"> <p>縮小、聚焦受眾資格需求。 </p> </td> 
   <td colname="col3"> <p>Users <i>must</i> belong to all specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OR OR</span></b> </p> </td> 
   <td colname="col2"> <p>更廣泛、更專注的受眾資格要求。 </p> </td> 
   <td colname="col3"> <p>Users <i>can</i> belong to any specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>縮小、聚焦受眾資格需求。 </p> <p>有多項條件可讓定義受眾資格要求困難或不有效率。有時候，驗證排除(而非包括)的需求比較容易。 </p> </td> 
   <td colname="col3"> <p>Users <i>must not</i> belong to an excluded trait or segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]使用個案範例**

[!UICONTROL AND] 當您輕鬆列舉特徵會籍需求時，此運算子十分有用。例如，假設您需要建立「昂貴的相機購物者」。」使用像素模型，您就必須建立並放置相機的像素和數值價格值。By contrast, with traits you can apply Boolean operators to handle both conditions (cameras [!UICONTROL AND] price). 結果就是以較少的HTTP呼叫來提高資料收集效率，進而有助於維持網站上的使用者體驗。

**[!UICONTROL OR]使用個案範例**

[!UICONTROL OR] 當您想要建立具有廣泛對象資格要求的訊號時，此運算子十分有用。If you have several trait or segment qualification requirements, the [!UICONTROL OR] operator will evaluate to true when your site visitors exhibit *any* of those characteristics. [!UICONTROL OR] 在您想要快速建立大量符合資格的網站訪客時最有用。

**[!UICONTROL AND NOT]使用個案範例**

[!UICONTROL AND NOT] 當 *透過排除* 而非 *包含來定義觀眾時，運算元很有用*。例如，假設您進行了銷售，想要將訪客劃分為僅限查看完整版商品價格的客戶。Rather than create a list of signals for all qualifying full or sale-price items, it may be easier to qualify visitors if they have *not* seen a sale price item. 這種方式非常有效率，因為您的銷售價格通常較優惠價格少。With a Boolean [!UICONTROL NOT], visitors *must not* exhibit the sale signal to qualify for full-price audience membership. By contrast, [!UICONTROL AND NOT] is the opposite of the [!UICONTROL AND] use case, which showed how audience membership is determined by inclusion (i.e., the visitor qualified based on 2 explicitly stated signals).

>[!MORE_贊_ this]
>
>* [使用TraitBuilder中的比較運算子](../features/traits/trait-comparison-operators.md)
>* [TraitBuilder運算式中的操作順序](../features/traits/trait-operator-precedence.md)

