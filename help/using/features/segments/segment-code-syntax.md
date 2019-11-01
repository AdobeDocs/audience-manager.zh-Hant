---
description: 「區段產生器」可讓您使用程式碼編輯器建立區段的特徵規則。 按一下「特徵」面板中的「區段運算式（程式碼檢視）」標籤以存取此功能。
seo-description: 「區段產生器」可讓您使用程式碼編輯器建立區段的特徵規則。 按一下「特徵」面板中的「區段運算式（程式碼檢視）」標籤以存取此功能。
seo-title: 區段運算式編輯器中使用的程式碼語法
solution: Audience Manager
title: 區段運算式編輯器中使用的程式碼語法
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 區段運算式編輯器中使用的程式碼語法 {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] 可讓您使用程式碼編輯器建立區段的特徵規則。 按一下面 **[!UICONTROL Segment Expressions (Code View)]** 板中的標 [!UICONTROL Traits] 簽以存取此功能。

## 運算式產生器程式碼語法

您可以使用程式碼將特徵規則新增至區段，而不是使用拖放功能。 編碼時，請用實際的運算式或值取代範例中的斜體元素。 基本程式碼使用下列語法：

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>依預設， [!DNL Boolean] 條件會 [!UICONTROL OR] 套用至運算式 *中的多* 個特徵。

### 使用布林運算子連結區段

若要建立區段群組，請以括弧括住頻率函式，並使用運算子( *、* 和)設定每個運算式 [!DNL Boolean] 之間的關[!UICONTROL AND][!UICONTROL OR][!UICONTROL NOT]系。

### 參數

>[!NOTE]
>
>除非另有說明，否則所有參數皆為必要參數。

| 名稱或變數 | 說明 |
|---|---|
| `FREQUENCY` | 必須位於運算式前方的常值。 |
| ` [`&lt;`traitID`&gt;`T]` | 一組特徵ID，後面接著字母 `T`。 以逗號分隔多個特徵。 例如, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *（可選）* ，設定區段中特徵的時近規則。 信以天 `D` 為單位表示最近一次。 |
| ` <Frequency Operator><Numeric Value>` | 設定區段中特徵的頻率規則。 |

### 允許的時近和頻率運算子

使用 [比較運算子和整數](../../features/segments/recency-and-frequency.md) ，設定時近和頻率間隔。 [!UICONTROL Segment Builder] 使用標準運算式，例如&lt;（小於）、&gt;（大於）、==（等於）等。 不過，當您設定時近或頻率時，允許的運算子類型會有所不同。 下表列出了允許的時近／頻率運算子。

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
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;=（大於／等於） </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;=（小於／等於） </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;=（大於／等於） </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;=（小於／等於） </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">==（等於） </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [時近與頻率](../../features/segments/recency-and-frequency.md)
>* [特徵和區段產生器中的布林運算式](../../reference/boolean-expressions-tsb.md)
>* [在TraitBuilder中使用比較運算子](../../features/traits/trait-comparison-operators.md)
>* [TraitBuilder運算式中的運算順序](../../features/traits/trait-operator-precedence.md)

