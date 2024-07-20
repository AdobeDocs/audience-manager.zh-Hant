---
description: 本文說明Audience Manager特徵和區段工具如何使用布林運算式AND、OR及NOT。
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: 特徵和區段產生器中的布林運算式
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# 特徵和區段產生器中的布林運算式{#boolean-expressions-in-trait-and-segment-builder}

本文說明Audience Manager特徵和區段工具如何使用布林運算式AND、OR及NOT。

<!-- 

c_tb_boolean.xml

 -->

**布林運算式**

布林邏輯是代數的分支，會使用一些基本運算式（或運運算元）來判斷陳述式是true或false。 最常見的運運算元是[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]。 這些運算式的組合，可協助您製作特別適合您資料需求的重點特徵或區段資格規則。 下圖顯示基本布林值運算式的運作方式。

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT]運運算元使用隱含的&quot;and&quot;條件，而且有時候會寫成[!UICONTROL AND NOT]。

**如何在特徵和區段產生器中使用布林運算式**

您可以使用布林運算式建立特徵和區段資格規則。 下表說明使用[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]建立資格條件的一般最佳實務。

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 運算式 </th> 
   <th colname="col2" class="entry"> 使用它來建立 </th> 
   <th colname="col3" class="entry"> 取得資格 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle">和</span></b> </p> </td> 
   <td colname="col2"> <p>狹窄、集中的對象資格要求。 </p> </td> 
   <td colname="col3"> <p>使用者<i>必須</i>屬於所有指定的特徵或區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle">或</span></b> </p> </td> 
   <td colname="col2"> <p>廣泛、重點較低的對象資格要求。 </p> </td> 
   <td colname="col3"> <p>使用者<i>可以</i>屬於任何指定的特徵或區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>狹窄、集中的對象資格要求。 </p> <p>當有多個條件導致定義對象資格要求困難或效率較低時，這項功能相當實用。 有時，根據排除而不是包含的需求進行驗證會比較容易。 </p> </td> 
   <td colname="col3"> <p>使用者<i>不得</i>屬於排除的特徵或區段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]使用案例範例**

當您輕鬆列舉特徵成員資格要求時，[!UICONTROL AND]運運算元就相當實用。 例如，假設您需要建立「昂貴相機購買者」的受眾。 使用畫素模型時，您必須建立並放置相機的畫素，以及頁面上的數值價格值。 相反地，透過特徵，您可以套用布林運運算元來處理兩個條件（相機[!UICONTROL AND]價格）。 如此一來，就能以較少的HTTP呼叫有效率地收集資料，進而協助保留網站上的使用者體驗。

**[!UICONTROL OR]使用案例範例**

當您想要建立具有廣泛對象資格要求的訊號時，[!UICONTROL OR]運運算元很有用。 如果您有數個特徵或區段資格要求，當您的網站訪客展現這些特徵中的&#x200B;*任何*&#x200B;時，[!UICONTROL OR]運運算元將會評估為true。 當您想要快速建立合格網站訪客的廣泛對象時，[!UICONTROL OR]可能最有用。

**[!UICONTROL AND NOT]使用案例範例**

當[!UICONTROL AND NOT]運運算元更容易透過&#x200B;*排除*&#x200B;而非&#x200B;*包含*&#x200B;來定義對象時，會很有用。 例如，假設您正在進行銷售，且想要將訪客區隔為僅檢視全價專案的客戶。 與其為所有合格的完整或售價專案建立訊號清單，如果訪客&#x200B;*未*&#x200B;看到售價專案，則可能更容易讓訪客符合資格。 這在管理上相當有效率，因為與全價優惠相比，您通常只有較少的售價專案。 使用布林值[!UICONTROL NOT]，訪客&#x200B;*不得*&#x200B;展示銷售訊號，以符合全價對象會籍資格。 相較之下，[!UICONTROL AND NOT]則與[!UICONTROL AND]使用案例相反，後者顯示受眾成員資格如何由包含專案決定（亦即訪客根據2個明確指出的訊號而符合資格）。

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用比較運運算元](../features/traits/trait-comparison-operators.md)
>* TraitBuilder運算式中的[運算順序](../features/traits/trait-operator-precedence.md)
