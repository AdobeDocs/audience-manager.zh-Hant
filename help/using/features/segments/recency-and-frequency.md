---
description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: 時近與頻率
solution: Audience Manager
title: 時近與頻率
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: c7e8b67ccad4479487b471668462937c5be6be34

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder], recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.

Audience Manager defines [!DNL recency] and [!DNL frequency] as follows:

* **[!UICONTROL Recency]** : How recently a user viewed or qualified for one (or more) traits.
* **[!UICONTROL Frequency]:** The rate at which a user viewed or qualified for one (or more) traits.

[!UICONTROL Recency] and  settings help you segment visitors based on their real (or perceived) level of interest in a site, section, or particular creative. [!UICONTROL Frequency]例如，符合最近／頻度需求較高群體的使用者，較之較少或較不常造訪的使用者，可能更感興趣網站或產品。

## 時近和頻率設定的位置 {#location}

在中 [!UICONTROL Segment Builder], [!UICONTROL Recency] 和設定位於 [!UICONTROL Frequency] 面板的部 [!UICONTROL Basic View][!UICONTROL Traits] 分。 Click the clock icon to expose these controls.

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
   <td colname="col1"> <p> <b>協力廠商特徵</b> </p> </td> 
   <td colname="col2"> <p>您無法針對個別的第三方特徵或包含第三方特徵的特徵群組設定最近一次的規則。 時近和頻率僅適用於您自己的特徵。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 頻率

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limit or Rule </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>協力廠商特徵</b> </p> </td> 
   <td colname="col2"> <p>You cannot set frequency rules on individual third-party traits or trait groups that contain third-party traits. Recency and frequency applies to your own traits only. </p> </td> 
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

在此範例中，您選取=&gt;運算子，如螢幕擷取所示。 如果使用者在Audience manager平台上的首次資格認證到五天前的中斷時間之間，至少有三次符合這三種特性中任何一種的資格，這將使他們符合區段資格。 The timeline below shows the segment qualification at the time the segment is created, on October 1st, and ten days later.

![舊版資格](assets/earlier-qualification.png)


## 頻率封頂範例 {#frequency-capping}

Frequency-capping expressions include all the users whose number of trait realizations is below a desired value. Here are a few examples:

* The expression  includes all users that have realized the trait with the ID "1000" a maximum of five times, including users who have not realized the trait.`frequency([1000T]) <= 5`
* 當您需要的時近／頻率需求少於特定次數或天數時，請使用運算子將該特徵連結至另一個特 `AND` 徵。 Using the example above, this expression becomes valid when joined with another trait as shown here: .`frequency([1000T]) <= 5 AND isSiteVisitorTrait`

* For advertising frequency-capping use cases, you could create a segment rule similar to this: . `(frequency([1000T] <= 2D) >= 5)`This expression includes all users that have realized the trait with the ID "1000" in the past 2 days at least five times. Set frequency capping by sending this segment to the ad server with a  set on the segment in the ad server. `NOT`This approach achieves greater performance in  while still serving the same purpose for frequency capping.[!DNL Audience Manager]

>[!MORE_LIKE_THIS]
>
>* [Segment Builder Controls: Traits Section](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [區段運算式編輯器中使用的程式碼語法](../../features/segments/segment-code-syntax.md)

