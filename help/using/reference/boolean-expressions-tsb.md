---
description: 本文說明Audience Manager特徵和區段工具如何使用布林運算式AND、OR和NOT。
seo-description: 本文說明Audience Manager特徵和區段工具如何使用布林運算式AND、OR和NOT。
seo-title: 特徵和區段產生器中的布林運算式
solution: Audience Manager
title: 特徵和區段產生器中的布林運算式
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
translation-type: tm+mt
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

布爾邏輯是代數的一個分支，它使用一些基本表達式（或運算子）來確定語句是真還是假。 最常見的運算子是[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]。 這些運算式的組合可協助您建立獨特的特定特徵或區段資格規則，以符合您的資料需求。 下圖顯示基本布林運算式的運作方式。

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT]運算子使用默示的&quot;and&quot;條件，有時寫成[!UICONTROL AND NOT]。

**如何在特徵和區段產生器中使用布林運算式**

您可使用布林運算式來建立特徵和區段限定規則。 下表說明建立具有[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]之資格標準的一般最佳實務。

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
   <td colname="col1"> <p><b><span class="wintitle"> 和</span></b> </p> </td> 
   <td colname="col2"> <p>縮小重點受眾資格要求。 </p> </td> 
   <td colname="col3"> <p>使用者<i>必須</i>屬於所有指定的特徵或區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 或</span></b> </p> </td> 
   <td colname="col2"> <p>廣泛、較不集中的受眾資格要求。 </p> </td> 
   <td colname="col3"> <p>使用者<i>可</i>屬於任何指定的特徵或區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>縮小重點受眾資格要求。 </p> <p>當有多種條件使定義受眾資格要求變得困難或效率不彰時，就很有用。 有時候，針對排除而非包含的需求進行驗證會比較容易。 </p> </td> 
   <td colname="col3"> <p>使用者<i>不得</i>屬於已排除的特徵或區段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]使用案例範例**

當您輕鬆列舉特徵成員資格要求時，[!UICONTROL AND]運算子很實用。 例如，假設您需要建立「昂貴的相機購物者」的觀眾。 使用像素模型時，您必須在頁面上建立並放置相機的像素和數值價格值。 相反地，您可以利用特性，套用布林運算子來處理這兩種條件（相機[!UICONTROL AND]價格）。 如此，只需較少的HTTP呼叫，即可有效收集資料，進而有助於保留您網站上的使用者體驗。

**[!UICONTROL OR]使用案例範例**

當您想要建立具有廣泛受眾資格要求的訊號時，[!UICONTROL OR]運算子很實用。 如果您有數個特徵或區段資格要求，當您的網站訪客顯示這些特徵的&#x200B;*any*&#x200B;時，[!UICONTROL OR]運算子會評估為true。 [!UICONTROL OR] 當您想要快速建立廣大合格網站訪客的讀者群時，可能最有用。

**[!UICONTROL AND NOT]使用案例範例**

當透過&#x200B;*exclusion*&#x200B;而非&#x200B;*inclusion*&#x200B;更容易定義觀眾時，[!UICONTROL AND NOT]運算子會很有用。 例如，假設您正在進行銷售，並想將訪客細分為只查看完整價格項目的客戶。 如果訪客的&#x200B;*未看到*&#x200B;銷售價格項目，則不必為所有符合資格的完整或銷售價格項目建立訊號清單，而是更容易確認訪客。 這在管理上很有效，因為相較於以完整價格提供的產品，您通常的售價項目較少。 使用布林值[!UICONTROL NOT]時，訪客&#x200B;*不得*&#x200B;顯示銷售訊號以符合全價觀眾會籍的資格。 相反地，[!UICONTROL AND NOT]與[!UICONTROL AND]使用案例相反，後者顯示如何透過包含來判斷觀眾成員資格（亦即，根據2個明確聲明的訊號來判斷訪客是否合格）。

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用比較運算子](../features/traits/trait-comparison-operators.md)
>* [TraitBuilder運算式中的運算順序](../features/traits/trait-operator-precedence.md)

