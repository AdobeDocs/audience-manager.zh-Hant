---
description: 本文說明Audience Manager特徵和區段工具如何使用布林運算式AND、OR和NOT。
seo-description: 本文說明Audience Manager特徵和區段工具如何使用布林運算式AND、OR和NOT。
seo-title: 特徵和區段產生器中的布林運算式
solution: Audience Manager
title: 特徵和區段產生器中的布林運算式
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: 參考
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# 特徵和區段產生器中的布林運算式{#boolean-expressions-in-trait-and-segment-builder}

本文說明Audience Manager特徵和區段工具如何使用布林運算式AND、OR和NOT。

<!-- 

c_tb_boolean.xml

 -->

**布林運算式**

布爾邏輯是代數的一個分支，它使用一些基本表達式（或運算子）來確定語句是真還是假。 最常見的運算子是[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]。 這些運算式的組合可協助您將重點突出的特徵或區段資格規則特別適合您的資料需求。 下圖顯示基本布林運算式的運作方式。

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT]運算子使用默示的「and」條件，有時寫入為[!UICONTROL AND NOT]。

**如何在特徵和區段產生器中使用布林運算式**

您可使用布林運算式建立特徵和區段資格規則。 下表說明使用[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]建立資格標準的一般最佳做法。

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 運算式 </th> 
   <th colname="col2" class="entry"> 使用它建立 </th> 
   <th colname="col3" class="entry"> 若要符合 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 和</span></b> </p> </td> 
   <td colname="col2"> <p>縮小、重點明確的受眾資格要求。 </p> </td> 
   <td colname="col3"> <p>使用者<i>必須</i>屬於所有指定的特徵或區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 或</span></b> </p> </td> 
   <td colname="col2"> <p>廣泛、重點較少的受眾資格要求。 </p> </td> 
   <td colname="col3"> <p>使用者<i>可以</i>屬於任何指定的特徵或區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>縮小、重點明確的受眾資格要求。 </p> <p>當有多個條件導致難以或效率低下地定義對象資格要求時，此功能相當實用。 有時候，根據排除而非包含的要求來驗證會較為容易。 </p> </td> 
   <td colname="col3"> <p>使用者<i>不得</i>屬於排除的特徵或區段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]使用案例範例**

如果您有輕鬆列舉的特徵成員資格要求，[!UICONTROL AND]運算子就很實用。 例如，假設您需要建立「昂貴的相機購物者」的受眾。 使用像素模型時，您必須在頁面上建立並放置相機的像素以及數值價格值。 相較之下，針對特徵，您可以套用布林運算子來處理兩個條件（相機[!UICONTROL AND]價格）。 如此一來，您就能以較少的HTTP呼叫來有效收集資料，進而有助於保留您網站上的使用者體驗。

**[!UICONTROL OR]使用案例範例**

如果您想要建立具有廣泛受眾資格要求的訊號，[!UICONTROL OR]運算子就十分實用。 如果您有數個特徵或區段資格要求，當您的網站訪客顯示這些特徵的&#x200B;*任何*&#x200B;時，[!UICONTROL OR]運算子將評估為true。 [!UICONTROL OR] 當您想要快速建立合格網站訪客的廣泛受眾時，可能最有用。

**[!UICONTROL AND NOT]使用案例範例**

如果透過&#x200B;*exclusion*&#x200B;而非&#x200B;*inclusion*&#x200B;更容易定義對象，[!UICONTROL AND NOT]運算子就很實用。 例如，假設您有銷售，且想要將訪客細分為只查看完整價格項目的客戶。 如果訪客&#x200B;*未*&#x200B;看見銷售價格項目，可能更容易符合訪客的資格，而非為所有合格的完整或銷售價格項目建立訊號清單。 這在管理上很有效，因為與以全價提供的價格相比，通常銷售價格項目較少。 若使用布林值[!UICONTROL NOT]，訪客&#x200B;*不得*&#x200B;顯示銷售訊號以符合全價受眾成員資格的資格。 相反地，[!UICONTROL AND NOT]與[!UICONTROL AND]使用案例相反，後者顯示如何透過包含來判斷對象成員資格（亦即，訪客根據2個明確指出的訊號符合資格）。

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用比較運算子](../features/traits/trait-comparison-operators.md)
* [TraitBuilder運算式中的作業順序](../features/traits/trait-operator-precedence.md)

