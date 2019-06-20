---
description: 區段產生器可讓您使用程式碼編輯器建立區段的特徵規則。按一下「特徵」面板中的「區段運算式(代碼檢視)」索引標籤，即可存取此功能。
seo-description: 區段產生器可讓您使用程式碼編輯器建立區段的特徵規則。按一下「特徵」面板中的「區段運算式(代碼檢視)」索引標籤，即可存取此功能。
seo-title: 區段運算式編輯器中使用的程式碼語法
solution: Audience Manager
title: 區段運算式編輯器中使用的程式碼語法
uuid: 7b4b06ca-7879-4501-8ba7-b2 b6467 b8 a3 b
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Code Syntax Used in the Segment Expression Editor {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] 可讓您使用程式碼編輯器建立區段的特徵規則。Click the **[!UICONTROL Segment Expressions (Code View)]** tab in the [!UICONTROL Traits] panel to access this feature.

## 運算式產生器代碼語法

您可以使用程式碼新增特徵規則至區段，而非使用拖放功能。在編碼時，以實際運算式或值取代範例中的斜體元素。基本程式碼使用下列語法：

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>By default, [!DNL Boolean] [!UICONTROL OR] conditions apply to multiple traits *within* an expression.

### 使用布林運算元加入區段

To build groups of segments, wrap the frequency function in parenthesis and set the relationship *between* each expression with a [!DNL Boolean] operator ([!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]).

### 參數

>[!NOTE]
>
>除非另行聲明，否則需要所有參數。

| 名稱或變數 | 說明 |
|---|---|
| `FREQUENCY` | 必須先於運算式的常值。 |
| ` [`&lt;`traitID`&gt;`T]` | An array of trait IDs followed by the letter `T`. 以逗號分隔多個特徵。例如, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(可選)* 設定區段特徵的最近一個時近規則。The letter `D` indicates recency in days. |
| ` <Frequency Operator><Numeric Value>` | 設定區段特徵的頻率規則。 |

### 允許的最近一次與頻率運算子

Set [recency and frequency](../../features/segments/recency-and-frequency.md) intervals with a comparison operator and an integer. [!UICONTROL Segment Builder] 使用標準運算式，例如&lt;(小於)、&gt;(大於)、==(等號)等。不過，允許的運算元類型會在您設定時近或頻率。下表列出允許的最近/頻率運算子。

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 最近一次運算子 </th> 
   <th colname="col2" class="entry"> 頻率運算子 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;=(大於/等於) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;=(小於/等於) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;=(大於/等於) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;=(小於/等於) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">==(等於) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_贊_ this]
>
>* [最近一次與頻率](../../features/segments/recency-and-frequency.md)
>* [特徵和區段產生器中的布林運算式](../../reference/boolean-expressions-tsb.md)
>* [使用TraitBuilder中的比較運算子](../../features/traits/trait-comparison-operators.md)
>* [TraitBuilder運算式中的操作順序](../../features/traits/trait-operator-precedence.md)

