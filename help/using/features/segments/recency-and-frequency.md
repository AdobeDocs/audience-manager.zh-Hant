---
description: 在「區段產生器」中，最近一次和頻率可讓您根據在設定每日間隔內發生或重複的動作來區隔訪客。
seo-description: 在「區段產生器」中，最近一次和頻率可讓您根據在設定每日間隔內發生或重複的動作來區隔訪客。
seo-title: 使用間隔和頻率
solution: Audience Manager
title: 使用間隔和頻率
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 3%

---


# 使用間隔和頻率 {#recency-and-frequency}

在[!UICONTROL Segment Builder]中，最近一次和頻率可讓您根據在設定每日間隔內發生或重複的動作來劃分訪客。

Audience Manager定義[!DNL recency]和[!DNL frequency]如下：

* **[!UICONTROL Recency]：使** 用者最近檢視或符合一（或多）項資格的時間 [!UICONTROL traits]。
* **[!UICONTROL Frequency]：使** 用者檢視或符合一（或多）個使用者資格的比率 [!UICONTROL traits]。

[!UICONTROL Recency] 而設 [!UICONTROL Frequency] 定可協助您根據訪客對網站、區段或特定創意素材的實際（或察覺）興趣程度來劃分訪客。例如，符合最近／頻度需求較高群體的使用者，較之較少或較不常造訪的使用者，可能更感興趣網站或產品。

## [!UICONTROL Recency and Frequency]設定{#location}的位置

在[!UICONTROL Segment Builder]中，[!UICONTROL Recency]和[!UICONTROL Frequency]設定位於[!UICONTROL Traits]面板的[!UICONTROL Basic View]部分。 按一下時鐘圖示以公開這些控制項。

![](assets/recency_frequency.png)

## 限制和規則{#limitations-rules}

當您想要將時近和頻率套用至區段中的特徵時，請檢閱並瞭解這些限制和規則。

### [!UICONTROL Recency] {#recency}

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 限制或規則 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>最小值</b> </p> </td> 
   <td colname="col2"> <p>最近一次必須大於0。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>特徵類型</b> </p> </td> 
   <td colname="col2"> <p>您只能將時近控制項套用至規則型和資料夾特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>協力廠商特徵</b> </p> </td> 
   <td colname="col2"> <p>您無法針對個別的第三方特徵或包含第三方特徵的特徵群組設定最近一次的規則。 時近和頻率僅適用於您自己的特徵。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Frequency] {#frequency}

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 限制或規則 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>協力廠商特徵</b> </p> </td> 
   <td colname="col2"> <p>您無法針對包含第三方特徵的個別第三方特徵或特徵群組設定頻率規則。 時近和頻率僅適用於您自己的特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>特徵類型</b> </p> </td> 
   <td colname="col2"> <p>您只能將頻率控制套用至規則型和資料夾特性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>時近要求</b> </p> </td> 
   <td colname="col2"> <p>您可以設定頻率要求<i>而不設定最近的要求。 </i>只要設定一個頻率值，並將時近欄位留空即可。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>設定檔合併規則</b> </p> </td> 
   <td colname="col2"> <p>請參閱<a href="../../faq/faq-profile-merge.md#trait-freq-device-rules">特徵頻率、外部裝置圖形和描述檔合併規則</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 時近範例{#recency-examples}

以下是兩種最近一次如何運作的範例，視您在UI中的選擇而定：

### 使用小於或等於運算子(&lt;=)

![小於等於](assets/less-than-equal-to.png)

在此範例中，您選取&lt;=運算子，如螢幕擷取所示。 如果使用者在過去5天內至少有3次符合[!UICONTROL traits]中任何一個的資格，則此選項可讓使用者符合[!UICONTROL segment]資格。 以下時間軸顯示在[!UICONTROL segment]建立時的[!UICONTROL segment]資格，日期是10月1日，十天後。

![最近5天](assets/last-5-days.png)

### 使用大於或等於運算子(=>)

![大於等於](assets/greater-than-equal-to.png)

在此範例中，您選取=>運算子，如螢幕擷取所示。 如果使用者在Audience Manager平台上的首次資格認證和五天前的中斷時間之間，至少有三次符合[!UICONTROL segment]中任何一個[!UICONTROL traits]的資格，這可讓他們符合&lt;a0/>資格。 以下時間軸顯示在[!UICONTROL segment]建立時的[!UICONTROL segment]資格，日期是10月1日，十天後。

![舊版資格](assets/earlier-qualification.png)


## 頻率封頂範例{#frequency-capping}

頻率封頂運算式包含[!UICONTROL trait]實現次數低於所需值的所有使用者。 以下是幾個正確和錯誤的示例：

* 錯誤——表達式`frequency([1000T]) <= 5`包含已實現ID為&quot;1000&quot;的[!UICONTROL trait]的所有用戶，但也包含尚未實現[!UICONTROL trait]的用戶。 因此，Audience Manager不會基於效能原因來驗證此運算式，因為它會讓太多使用者符合[!UICONTROL segment]的資格。

* 右——如果要包含已實現ID為&quot;1000&quot;的[!UICONTROL trait]且最多5次的所有用戶，請向表達式添加另一個條件，以確保用戶至少符合[!UICONTROL trait]的條件： `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* 右——當您需要的時近／頻率要求少於特定次數或天數時，請使用`AND`運算子將[!UICONTROL trait]連結至另一個。 使用第一個項目符號點中的示例，此表達式在與另一個[!UICONTROL trait]連接時變為有效，如下所示：`frequency([1000T]) <= 5 AND isSiteVisitorTrait`。

* 右——對於廣告限頻使用案例，您可以建立類似以下的[!UICONTROL segment]規則：`(frequency([1000T] <= 2D) >= 5)`。 此運算式包含在過去2天中至少5次以ID為&quot;1000&quot;實現[!UICONTROL trait]的所有使用者。 將此[!UICONTROL segment]傳送至廣告伺服器，並在廣告伺服器的[!UICONTROL segment]上設定`NOT`，以設定頻率上限。 此方法在[!DNL Audience Manager]中實現了更高的效能，同時仍為頻率封頂提供相同的用途。

>[!MORELIKETHIS]
>
>* [區段產生器控制：特徵區段](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [區段運算式編輯器中使用的程式碼語法](../../features/segments/segment-code-syntax.md)

