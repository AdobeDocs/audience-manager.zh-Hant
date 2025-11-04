---
description: 區段產生器可讓您使用程式碼編輯器為區段建立特徵規則。 按一下「特徵」面板中的「區段運算式（程式碼檢視）」索引標籤，即可存取此功能。
seo-description: Segment Builder lets you build trait rules for a segment using a code editor. Click the Segment Expressions (Code View) tab in the Traits panel to access this feature.
seo-title: Code Syntax Used in the Segment Expression Editor
solution: Audience Manager
title: 區段運算式編輯器中使用的程式碼語法
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
exl-id: 64fa6f03-cef9-4187-866f-28c54f45f72e
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 4%

---

# 區段運算式編輯器中使用的程式碼語法 {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder]可讓您使用程式碼編輯器建立區段的特徵規則。 按一下「**[!UICONTROL Segment Expressions (Code View)]**」面板中的「[!UICONTROL Traits]」索引標籤以存取此功能。

## 運算式產生器程式碼語法

您可以使用程式碼將特徵規則新增至區段，而不使用拖放功能。 編碼時，將範例中的斜體元素替換為實際運算式或值。 基底程式碼會使用以下語法：

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>根據預設，[!DNL Boolean] [!UICONTROL OR]條件套用至運算式&#x200B;*內的多個特徵*。

### 使用布林運運算元連線區段

若要建立區段群組，請將頻率函式括在括弧中，並使用&#x200B;*運運算元（*、[!DNL Boolean]和[!UICONTROL AND]）設定每個運算式之間[!UICONTROL OR]的關係[!UICONTROL NOT]。

### 參數

>[!NOTE]
>
>除非另有說明，否則所有引數都是必要的。

| 名稱或變數 | 說明 |
|---|---|
| `FREQUENCY` | 必須在運算式前面的常值。 |
| `[`&lt;`traitID`>`T]` | 特徵ID的陣列，後面接著字母`T`。 請使用逗號分隔多個特徵。 例如，`[123T, 456T]`。 |
| `<Recency Operator><Numeric Value>D` | *（選擇性）*&#x200B;針對區段中的特徵設定造訪間隔規則。 字母`D`代表造訪間隔（以天為單位）。 |
| `<Frequency Operator><Numeric Value>` | 設定區段中特徵的頻率規則。 |

### 允許的造訪間隔和頻率運運算元

使用比較運運算元和整數設定[造訪間隔和頻率](../../features/segments/recency-and-frequency.md)間隔。 [!UICONTROL Segment Builder]使用&lt; （小於）、> （大於）、== （等於）等標準運算式。 不過，當您設定造訪間隔或頻率時，允許的運運算元型別會有所不同。 下表列出允許的造訪間隔/頻率運運算元。

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 造訪間隔運運算元 </th> 
   <th colname="col2" class="entry"> 頻率運運算元 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= （大於/等於） </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;= （小於/等於） </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= （大於/等於） </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;= （小於/等於） </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">== （等於） </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用間隔和頻率](../../features/segments/recency-and-frequency.md)
>* [特徵和區段產生器中的布林運算式](../../reference/boolean-expressions-tsb.md)
>* [在TraitBuilder中使用比較運運算元](../../features/traits/trait-comparison-operators.md)
>* TraitBuilder運算式中的[運算順序](../../features/traits/trait-operator-precedence.md)
