---
description: 在「區段產生器」中，「造訪間隔」和「頻率」可讓您根據在設定每日間隔內發生或重複的動作來劃分訪客。
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: 造訪間隔和頻率
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 1%

---

# 造訪間隔和頻率 {#recency-and-frequency}

在[!UICONTROL Segment Builder]中，造訪間隔和頻率可讓您根據在設定的每日間隔內發生或重複的動作來劃分訪客。

Audience Manager定義[!DNL recency]和[!DNL frequency]如下：

* **[!UICONTROL Recency]：**&#x200B;使用者最近檢視過或符合一個（或多個） [!UICONTROL traits]的資格。
* **[!UICONTROL Frequency]：**&#x200B;使用者檢視或符合一個（或多個） [!UICONTROL traits]資格的速率。

[!UICONTROL Recency]和[!UICONTROL Frequency]設定可協助您根據訪客在網站、區段或特定創意內容中的實際（或感知的）興趣層級來劃分訪客。 例如，符合高造訪間隔/頻率需求區段資格的使用者，可能會比造訪頻率較低或不常造訪的使用者對網站或產品更感興趣。

## [!UICONTROL Recency and Frequency]設定的位置 {#location}

在[!UICONTROL Segment Builder]中，[!UICONTROL Recency]和[!UICONTROL Frequency]設定位於[!UICONTROL Traits]面板的[!UICONTROL Basic View]區段中。 按一下時鐘圖示以公開這些控制項。

![](assets/recency_frequency.png)

## 限制和規則 {#limitations-rules}

當您想要將造訪間隔和頻率套用至區段中的特徵時，請檢閱並瞭解這些限制和規則。

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
   <td colname="col2"> <p>造訪間隔必須大於0。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>特徵型別</b> </p> </td> 
   <td colname="col2"> <p>您只能將造訪間隔控制項套用至規則型和資料夾特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>協力廠商特徵</b> </p> </td> 
   <td colname="col2"> <p>您無法針對個別第三方特徵或包含第三方特徵的特徵群組設定造訪間隔規則。 造訪間隔和頻率僅適用於您自己的特徵。 </p> </td> 
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
   <td colname="col2"> <p>您無法針對個別協力廠商特徵或包含協力廠商特徵的特徵群組設定頻率規則。 造訪間隔和頻率僅適用於您自己的特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>特徵型別</b> </p> </td> 
   <td colname="col2"> <p>您只能將頻率控制項套用至規則型和資料夾特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>造訪間隔需求</b> </p> </td> 
   <td colname="col2"> <p>您可以設定頻率需求<i>，而不需要</i>設定造訪間隔需求。 只要設定頻率值並將「造訪間隔」欄位保留空白即可。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>設定檔合併規則</b> </p> </td> 
   <td colname="col2"> <p>檢視<a href="../../faq/faq-profile-merge.md#trait-freq-device-rules">特徵頻率、外部裝置圖表和設定檔合併規則</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 造訪間隔範例 {#recency-examples}

以下是兩個造訪間隔的運作範例，視您在UI中的選取而定：

### 使用小於或等於運運算元(&lt;=)

![小於等於](assets/less-than-equal-to.png)

在此範例中，您選取&lt;=運運算元，如熒幕擷圖所示。 如果使用者在過去五天內符合三個[!UICONTROL traits]中的任何一個的資格，這至少會符合三次[!UICONTROL segment]的資格。 以下時間表顯示[!UICONTROL segment]建立時、10月1日及十天後的[!UICONTROL segment]資格。

![最近5天](assets/last-5-days.png)

### 使用大於或等於運運算元(=>)

![大於等於](assets/greater-than-equal-to.png)

在此範例中，您選取=>運運算元，如熒幕擷圖所示。 若您的使用者符合三個[!UICONTROL traits]中的任一個，這將使其符合在Audience Manager平台上的第一個資格與五天前的截止時間之間至少三次的[!UICONTROL segment]資格。 以下時間表顯示[!UICONTROL segment]建立時、10月1日及十天後的[!UICONTROL segment]資格。

![先前資格](assets/earlier-qualification.png)


## 頻率限定範例 {#frequency-capping}

頻率限定運算式包含[!UICONTROL trait]實現次數低於所需值的所有使用者。 以下是一些正確和錯誤的範例：

* 錯誤 — 運算式`frequency([1000T]) <= 5`包含識別碼為「1000」且最多可實現5次之[!UICONTROL trait]的所有使用者，但也包含尚未實現[!UICONTROL trait]的使用者。 因此，基於效能原因，Audience Manager不會驗證此運算式，因為它將使[!UICONTROL segment]的太多使用者符合資格。

* 權利 — 如果您想要包含識別碼為&quot;1000&quot;且已實現[!UICONTROL trait]最多五次的所有使用者，請在運算式中新增其他條件，以確定使用者至少符合一次[!UICONTROL trait]： `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* 右 — 當您需要時近/頻率要求小於特定次數或天數時，請使用`AND`運運算元將該[!UICONTROL trait]加入另一個中。 使用第一個專案符號點中的範例，此運算式在與其他[!UICONTROL trait]連結時變成有效，如下所示： `frequency([1000T]) <= 5 AND isSiteVisitorTrait`。

* 右 — 針對廣告頻率限定使用案例，您可以建立類似以下的[!UICONTROL segment]規則： `(frequency([1000T] <= 2D) >= 5)`。 此運算式包含在過去2天內至少實現5次ID為&quot;1000&quot;的[!UICONTROL trait]的所有使用者。 將此[!UICONTROL segment]傳送至廣告伺服器，並在廣告伺服器的[!UICONTROL segment]上設定`NOT`，以設定頻率上限。 此方法在[!DNL Audience Manager]中取得更優異的效能，同時仍提供相同的頻率上限用途。

>[!MORELIKETHIS]
>
>* [區段產生器控制項：特徵區段](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [區段運算式編輯器中使用的程式碼語法](../../features/segments/segment-code-syntax.md)
