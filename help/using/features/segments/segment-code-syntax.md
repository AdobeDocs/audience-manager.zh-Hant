---
description: 段生成器允許您使用代碼編輯器為段生成特性規則。 按一下「特徵」面板中的段表達式（代碼視圖）頁籤以訪問此功能。
seo-description: Segment Builder lets you build trait rules for a segment using a code editor. Click the Segment Expressions (Code View) tab in the Traits panel to access this feature.
seo-title: Code Syntax Used in the Segment Expression Editor
solution: Audience Manager
title: 區段運算式編輯器中使用的程式碼語法
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
exl-id: 64fa6f03-cef9-4187-866f-28c54f45f72e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 10%

---

# 區段運算式編輯器中使用的程式碼語法 {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] 允許您使用代碼編輯器為段生成特性規則。 按一下 **[!UICONTROL Segment Expressions (Code View)]** 的 [!UICONTROL Traits] 訪問此功能的面板。

## Expression Builder代碼語法

可以將特徵規則添加到帶代碼的段，而不是使用拖放特徵。 編碼時，請用實際表達式或值替換示例中的斜體元素。 基本代碼使用以下語法：

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>預設情況下， [!DNL Boolean] [!UICONTROL OR] 條件適用於多個特徵 *內* 表達式。

### 使用布爾運算子連接段

要構建段組，請在括弧中括起頻率函式並設定關係 *間* 每個表達式 [!DNL Boolean] 運算子([!UICONTROL AND]。 [!UICONTROL OR], [!UICONTROL NOT])。

### 參數

>[!NOTE]
>
>除非另有說明，否則所有參數都是必需的。

| 名稱或變數 | 說明 |
|---|---|
| `FREQUENCY` | 必須位於表達式之前的文本。 |
| ` [`&lt;`traitID`>`T]` | 一組特徵ID，後面跟字母 `T`。 用逗號分隔多個特徵。 例如, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *（可選）* 設定段中特徵的頻率規則。 信 `D` 表示以天為單位的最近。 |
| ` <Frequency Operator><Numeric Value>` | 設定段中特徵的頻率規則。 |

### 允許的頻率和頻率運算子

設定 [頻率](../../features/segments/recency-and-frequency.md) 間隔為比較運算子和整數。 [!UICONTROL Segment Builder] 使用標準表達式，如&lt;（小於）、>（大於）、==（等於）等。 但是，當設定頻率或頻率時，允許的運算子類型會有所不同。 下表列出了允許的頻率/頻率運算子。

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 頻率運算子 </th> 
   <th colname="col2" class="entry"> 頻率運算子 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;=（大於/等於） </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;=（小於/等於） </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;=（大於/等於） </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;=（小於/等於） </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">==（等於） </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用間隔和頻率](../../features/segments/recency-and-frequency.md)
>* [特徵和區段產生器中的布林運算式](../../reference/boolean-expressions-tsb.md)
>* [在TraitBuilder中使用比較運算子](../../features/traits/trait-comparison-operators.md)
>* [TraitBuilder表達式中的操作順序](../../features/traits/trait-operator-precedence.md)

