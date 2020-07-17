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

在時 [!UICONTROL Segment Builder]近和頻率中，可讓您根據在設定每日間隔內發生或重複的動作來劃分訪客。

Audience Manager定義 [!DNL recency] 及 [!DNL frequency] 定義如下：

* **[!UICONTROL Recency]:**使用者最近檢視或符合一（或多）個人資格的時間[!UICONTROL traits]。
* **[!UICONTROL Frequency]:**使用者檢視或符合一（或多）項資格的比率[!UICONTROL traits]。

[!UICONTROL Recency] 而設 [!UICONTROL Frequency] 定可協助您根據訪客對網站、區段或特定創意素材的真實（或感知）興趣程度來劃分訪客。 例如，符合最近／頻度需求較高群體的使用者，較之較少或較不常造訪的使用者，可能更感興趣網站或產品。

## 設定位 [!UICONTROL Recency and Frequency] 置 {#location}

在中 [!UICONTROL Segment Builder], [!UICONTROL Recency] 和設定位於 [!UICONTROL Frequency] 面板的部 [!UICONTROL Basic View][!UICONTROL Traits] 分。 按一下時鐘圖示以公開這些控制項。

![](assets/recency_frequency.png)

## 限制與規則 {#limitations-rules}

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
   <td colname="col2"> <p>您可以設定頻率需求， <i>而不需</i> 設定最近一次的需求。 只要設定一個頻率值，並將時近欄位留空即可。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>設定檔合併規則</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Trait Frequency, External Device Graphs, and Profile Merge Rules</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最近一次的範例 {#recency-examples}

以下是兩種最近一次如何運作的範例，視您在UI中的選擇而定：

### 使用小於或等於運算子(&lt;=)

![小於等於](assets/less-than-equal-to.png)

在此範例中，您選取&lt;=運算子，如螢幕擷取所示。 如果使用者在過 [!UICONTROL segment] 去5天內至少有3次符合這3 [!UICONTROL traits] 種選擇的資格，即符合此資格。 以下時間軸顯 [!UICONTROL segment] 示建立時的資 [!UICONTROL segment] 格，日期是10月1日，十天後。

![最近5天](assets/last-5-days.png)

### 使用大於或等於運算子(=>)

![大於等於](assets/greater-than-equal-to.png)

在此範例中，您選取=>運算子，如螢幕擷取所示。 如果使用者在 [!UICONTROL segment] Audience Manager平台上的首次資格認證到五天前的中斷時間之間，至少 [!UICONTROL traits] 有三次符合三者中任一者的資格，即可符合此資格。 以下時間軸顯 [!UICONTROL segment] 示建立時的資 [!UICONTROL segment] 格，日期是10月1日，十天後。

![舊版資格](assets/earlier-qualification.png)


## 頻率封頂範例 {#frequency-capping}

頻率封頂運算式包含實現數低於所需值 [!UICONTROL trait] 的所有使用者。 以下是幾個正確和錯誤的示例：

* 錯誤——表達 `frequency([1000T]) <= 5` 式包含所有已實現ID為 [!UICONTROL trait] &quot;1000&quot;的用戶，最多5次，但也包括尚未實現的用戶 [!UICONTROL trait]。 因此，Audience Manager不會基於效能原因來驗證此運算式，因為它可讓太多使用者符合此運算式的資格 [!UICONTROL segment]。

* 對——如果您想要包含所有已實現ID為 [!UICONTROL trait] &quot;1000&quot;且最多為5次的使用者，請新增另一個條件至運算式，以確定使用者已符合至少一次 [!UICONTROL trait] 資格：  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* 右——當您需要的時近／頻率需求少於特定次數或天數時，請使用運算子將其連 [!UICONTROL trait] 結至另一 `AND` 個。 使用第一個項目符號點中的示例，此表達式在與另一個項目符號連接時會 [!UICONTROL trait] 生效，如下所示： `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* 右側——對於廣告限頻使用案例，您可以建立類似 [!UICONTROL segment] 下列的規則： `(frequency([1000T] <= 2D) >= 5)`. 此運算式包含在過去2天 [!UICONTROL trait] 中，至少5次已實現ID為&quot;1000&quot;的所有使用者。 將此設定傳送至廣告伺服 [!UICONTROL segment] 器，並在廣告伺服器中設定 `NOT` 頻率上限， [!UICONTROL segment] 以設定頻率上限。 該方法在保持頻率封 [!DNL Audience Manager] 閉的相同目的的同時，實現了更高的效能。

>[!MORELIKETHIS]
>
>* [區段產生器控制： 特徵區段](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [區段運算式編輯器中使用的程式碼語法](../../features/segments/segment-code-syntax.md)

