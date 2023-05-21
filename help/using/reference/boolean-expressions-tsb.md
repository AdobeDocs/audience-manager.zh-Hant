---
description: 本文說明Audience Manager特性和段工具如何使用布爾表達式AND、OR和NOT。
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: 特徵和區段產生器中的布林運算式
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 3%

---

# 特徵和區段產生器中的布林運算式{#boolean-expressions-in-trait-and-segment-builder}

本文說明Audience Manager特性和段工具如何使用布爾表達式AND、OR和NOT。

<!-- 

c_tb_boolean.xml

 -->

**布爾表達式**

布爾邏輯是代數的一個分支，它使用幾個基本表達式（或運算子）來確定語句是真還是假。 最常見的運算子是 [!UICONTROL AND]。 [!UICONTROL OR], [!UICONTROL NOT]。 這些表達式的組合有助於您使重點突出的特性或段限定規則特別適合您的資料要求。 下圖顯示了基本布爾表達式的工作原理。

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>的 [!UICONTROL NOT] 運算子使用隱含的「and」條件，有時寫為 [!UICONTROL AND NOT]。

**如何在特性和段生成器中使用布爾表達式**

使用布爾表達式構建特性和段限定規則。 下表介紹了建立資格標準的一般最佳做法 [!UICONTROL AND]。 [!UICONTROL OR], [!UICONTROL NOT]。

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 運算式 </th> 
   <th colname="col2" class="entry"> 使用它建立 </th> 
   <th colname="col3" class="entry"> 符合條件 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 和</span></b> </p> </td> 
   <td colname="col2"> <p>縮小、重點突出的受眾資格要求。 </p> </td> 
   <td colname="col3"> <p>用戶 <i>必須</i> 屬於所有指定的特徵或段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 或</span></b> </p> </td> 
   <td colname="col2"> <p>廣泛、關注度較低的受眾資格要求。 </p> </td> 
   <td colname="col3"> <p>用戶 <i>能</i> 屬於任何指定的特徵或段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>縮小、重點突出的受眾資格要求。 </p> <p>當存在多種條件使定義受眾資格要求變得困難或效率低下時，此功能非常有用。 有時，根據排除而非包括的要求來驗證會更容易。 </p> </td> 
   <td colname="col3"> <p>用戶 <i>不能</i> 屬於一個被排除的特徵或段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]用例示例**

的 [!UICONTROL AND] 當您具有容易枚舉的特徵成員資格要求時，運算子非常有用。 例如，你需要創造一個&quot;昂貴的相機購物者&quot;的受眾。 對於像素模型，您必須為相機建立和放置像素，並在頁面上設定數字價格值。 相比之下，使用特徵，您可以應用布爾運算子來處理這兩種情況（攝像頭） [!UICONTROL AND] 價格)。 結果是使用較少的HTTP調用高效地收集資料，這反過來又有助於保留您站點上的用戶體驗。

**[!UICONTROL OR]用例示例**

的 [!UICONTROL OR] 當您希望建立具有廣泛受眾資格要求的信號時，操作員會很有用。 如果您有幾個特性或段資格要求， [!UICONTROL OR] 當您的站點訪問者展示時，操作員將評估為true *任何* 這些特徵。 [!UICONTROL OR] 當您希望快速建立大量合格站點訪問者時，可能最有用。

**[!UICONTROL AND NOT]用例示例**

的 [!UICONTROL AND NOT] 當更易於通過 *排除* 而 *包*。 例如，假設您正在進行銷售，希望將訪問者細分為只查看全價商品的客戶。 與其為所有合格的完整或銷售價格項目建立信號清單，如果訪問者有，則更容易獲得資格 *不* 已看到銷售價格項。 這在管理上是高效的，因為與全價銷售的產品相比，您的售價通常要少一些。 帶布爾值 [!UICONTROL NOT]訪問者 *不能* 展示了銷售信號，以獲得全價觀眾會員資格。 相反， [!UICONTROL AND NOT] 是 [!UICONTROL AND] 用例，說明如何通過包含（即訪問者根據2個明確說明的信號獲得資格）來確定受眾的成員。

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用比較運算子](../features/traits/trait-comparison-operators.md)
>* [TraitBuilder表達式中的操作順序](../features/traits/trait-operator-precedence.md)

