---
description: 在「區段產生器」中，最近的時間和頻率可讓您根據發生的動作或在設定的每日間隔上重復訪客。
seo-description: 在「區段產生器」中，最近的時間和頻率可讓您根據發生的動作或在設定的每日間隔上重復訪客。
seo-title: 最近一次與頻率
solution: Audience Manager
title: 最近一次與頻率
uuid: faadd18a-cf27-4b73-995e-9809f52 f5350
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder], recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.

Audience Manager defines [!DNL recency] and [!DNL frequency] as follows:

* **[!UICONTROL Recency]：** 使用者檢視或符合一個(或更多)特徵的天數。
* **[!UICONTROL Frequency]：** 使用者檢視或符合一個(或更多)特徵的比率。

[!UICONTROL Recency][!UICONTROL Frequency] 和設定可協助您根據網站、區段或特定創意層級的實際(或感知)層級來劃分訪客。例如，使用高最近/頻度需求的區段使用者對網站或產品的興趣可能比經常或較少造訪的使用者更感興趣。

## Location of Recency and Frequency Settings {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] and [!UICONTROL Frequency] settings are located in the [!UICONTROL Basic View] section of the [!UICONTROL Traits] panel. 按一下時鐘圖示以公開這些控制項。

![](assets/recency_frequency.png)

## Limitations and Rules {#limitations-rules}

當您想要套用最近一段時間和頻率至區段中的特徵時，請檢閱並瞭解這些限制和規則。

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
   <td colname="col1"> <p> <b>第三方特徵</b> </p> </td> 
   <td colname="col2"> <p>您無法針對包含第三方特徵的個別第三方特性或特徵群組設定最近的規則。最近一次與頻率僅適用於您自己的特徵。 </p> </td> 
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
   <td colname="col1"> <p> <b>第三方特徵</b> </p> </td> 
   <td colname="col2"> <p>您無法在包含第三方特徵的個別第三方特性或特徵群組上設定頻率規則。最近一次與頻率僅適用於您自己的特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>最近一次要求</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements <i>without</i> configuring recency requirements. 只需設定頻率值，並將最近的欄位保留空白。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>描述檔合併規則</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Trait Frequency, External Device Graphs, and Profile Merge Rules</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Frequency Capping Examples {#frequency-capping}

頻率旁白運算式包括所有特性實作低於所需值的使用者。以下是一些例子：

* The expression `frequency([1000T]) <= 5` includes all users that have realized the trait with the ID &quot;1000&quot; a maximum of five times, including users who have not realized the trait.
* When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an `AND` operator. Using the example above, this expression becomes valid when joined with another trait as shown here: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* For advertising frequency-capping use cases, you could create a segment rule similar to this: `(frequency([1000T] <= 2D) >= 5)`. 此運算式包含所有已在過去天內，以ID「1000」實現特徵的使用者。Set frequency capping by sending this segment to the ad server with a `NOT` set on the segment in the ad server. This approach achieves greater performance in [!DNL Audience Manager] while still serving the same purpose for frequency capping.

>[!MORE_贊_ this]
>
>* [區段產生器控制項：特徵區段](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [區段運算式編輯器中使用的程式碼語法](../../features/segments/segment-code-syntax.md)

