---
description: 在「區段產生器」中，最近一次和頻率可讓您根據在設定每日間隔內發生或重複的動作來區隔訪客。
seo-description: 在「區段產生器」中，最近一次和頻率可讓您根據在設定每日間隔內發生或重複的動作來區隔訪客。
seo-title: 時近與頻率
solution: Audience Manager
title: 時近與頻率
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Recency and Frequency {#recency-and-frequency}

在時 [!UICONTROL Segment Builder]近和頻率中，可讓您根據在設定每日間隔內發生或重複的動作來劃分訪客。

Audience manager定義 [!DNL recency] 及 [!DNL frequency] 如下：

* **[!UICONTROL Recency]** :使用者最近檢視或符合一（或多個）特徵的次數。
* **[!UICONTROL Frequency]** :使用者檢視或符合一（或多個）特徵的比率。

[!UICONTROL Recency] 而設 [!UICONTROL Frequency] 定可協助您根據訪客對網站、區段或特定創意素材的真實（或感知）興趣程度來劃分訪客。 例如，符合最近／頻度需求較高群體的使用者，較之較少或較不常造訪的使用者，可能更感興趣網站或產品。

## 時近和頻率設定的位置 {#location}

在中 [!UICONTROL Segment Builder], [!UICONTROL Recency] 和設定位於 [!UICONTROL Frequency] 面板的部 [!UICONTROL Basic View][!UICONTROL Traits] 分。 按一下時鐘圖示以公開這些控制項。

![](assets/recency_frequency.png)

## 限制與規則 {#limitations-rules}

當您想要將時近和頻率套用至區段中的特徵時，請檢閱並瞭解這些限制和規則。

### 最近一次

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

### 頻率

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
   <td colname="col2"> <p>您可以設定頻率需求， <i>而不需</i> 設定最近一次的需求。 只要設定一個頻率值，並將時近欄位留空即可。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>描述檔合併規則</b> </p> </td> 
   <td colname="col2"> <p>請參閱 <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> 特徵頻率、外部裝置圖形和描述檔合併規則</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最近一次的範例 {#recency-examples}

以下是兩種最近一次如何運作的範例，視您在UI中的選擇而定：

### 使用小於或等於運算子(&lt;=)

![小於等於](assets/less-than-equal-to.png)

在此範例中，您選取&lt;=運算子，如螢幕擷取所示。 如果使用者在過去5天內至少有3次符合這3項特徵的資格，即可符合區段資格。 以下時間軸顯示建立區段時的區段資格，日期為10月1日，而日期為10天後。

![最近5天](assets/last-5-days.png)

### 使用大於或等於運算子(=&gt;)

![大於等於](assets/greater-than-equal-to.png)

在此範例中，您選取=&gt;運算子，如螢幕擷取所示。 如果使用者在Audience manager平台上的首次資格認證到五天前的中斷時間之間，至少有三次符合這三種特性中任何一種的資格，這將使他們符合區段資格。 以下時間軸顯示建立區段時的區段資格，日期為10月1日，而日期為10天後。

![舊版資格](assets/earlier-qualification.png)


## 頻率封頂範例 {#frequency-capping}

頻率封頂運算式包含特徵實現數目低於所需值的所有使用者。 以下是幾個正確和錯誤的示例：

* 錯誤——運算 `frequency([1000T]) <= 5` 式包含所有已實現ID為"1000"的特徵的使用者，最多可達5次，但也包含尚未實現該特徵的使用者。 因此，Audience manager不會基於效能原因來驗證此運算式，因為它會限定太多使用者進入區段。

* 對——如果您想要包含所有已實現ID為"1000"的特徵（最多5次）的使用者，請新增另一個條件至運算式，以確定使用者已至少符合該特徵一次：  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* 右——當您需要的時近／頻率需求少於特定次數或天數時，請使用運算子將該特徵連結至另一個特 `AND` 徵。 使用第一個項目符號點中的範例，此運算式在與另一個特徵連結時會生效，如下所示： `frequency([1000T]) <= 5 AND isSiteVisitorTrait`。

* 右側——對於廣告限頻使用案例，您可以建立類似下列的區段規則： `(frequency([1000T] <= 2D) >= 5)`。 此運算式包含在過去2天中，至少5次以ID「1000」實現該特徵的所有使用者。 將此區段傳送至廣告伺服器，並在廣告伺服器的 `NOT` 區段上設定頻率上限。 該方法在保持頻率封 [!DNL Audience Manager] 閉的相同目的的同時，實現了更高的效能。

>[!MORELIKETHIS]
>
>* [區段產生器控制：特徵區段](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [區段運算式編輯器中使用的程式碼語法](../../features/segments/segment-code-syntax.md)

