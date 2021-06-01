---
description: 在區段產生器中，造訪間隔和頻率可讓您根據在設定的每日間隔內發生或重複的動作來劃分訪客。
seo-description: 在區段產生器中，造訪間隔和頻率可讓您根據在設定的每日間隔內發生或重複的動作來劃分訪客。
seo-title: 使用間隔和頻率
solution: Audience Manager
title: 使用間隔和頻率
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: 區段
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 3%

---

# 使用間隔和頻率 {#recency-and-frequency}

在[!UICONTROL Segment Builder]中，造訪間隔和頻率可讓您根據在設定的每日間隔內發生或重複的動作來劃分訪客。

Audience Manager定義[!DNL recency]和[!DNL frequency]如下：

* **[!UICONTROL Recency]:** 使用者檢視或符合一（或多個）的資格的最近時間 [!UICONTROL traits]。
* **[!UICONTROL Frequency]:** 使用者檢視或符合一（或多個）的比率 [!UICONTROL traits]。

[!UICONTROL Recency] 和設 [!UICONTROL Frequency] 定可協助您根據訪客對網站、區段或特定創意的實際（或感知）興趣程度，來劃分訪客。例如，符合最近/頻度高需求區段的使用者，可能對網站或產品較有興趣，而不是瀏覽頻率較低或頻率較低的使用者。

## [!UICONTROL Recency and Frequency]設定的位置 {#location}

在[!UICONTROL Segment Builder]中，[!UICONTROL Recency]和[!UICONTROL Frequency]設定位於[!UICONTROL Traits]面板的[!UICONTROL Basic View]部分。 按一下時鐘圖示以公開這些控制項。

![](assets/recency_frequency.png)

## 限制和規則{#limitations-rules}

如果您想要將造訪間隔和頻率套用至區段中的特徵，請檢閱並了解這些限制和規則。

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
   <td colname="col1"> <p> <b>特徵類型</b> </p> </td> 
   <td colname="col2"> <p>您只能將造訪間隔控制套用至規則型特徵和資料夾特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>第三方特徵</b> </p> </td> 
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
   <td colname="col1"> <p> <b>第三方特徵</b> </p> </td> 
   <td colname="col2"> <p>您無法針對個別第三方特徵或包含第三方特徵的特徵群組設定頻率規則。 造訪間隔和頻率僅適用於您自己的特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>特徵類型</b> </p> </td> 
   <td colname="col2"> <p>您只能將頻率控制套用至規則型特徵和資料夾特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>造訪間隔需求</b> </p> </td> 
   <td colname="col2"> <p>您可以設定頻率要求<i>而不需</i>設定時近要求。 只需設定頻率值，並將「造訪間隔」欄位留空即可。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>設定檔合併規則</b> </p> </td> 
   <td colname="col2"> <p>請參閱<a href="../../faq/faq-profile-merge.md#trait-freq-device-rules">特徵頻率、外部裝置圖表和設定檔合併規則</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 時近範例{#recency-examples}

根據您在UI中的選取，以下是造訪間隔的兩個運作範例：

### 使用小於或等於運算子(&lt;=)

![Less-than-equal-to](assets/less-than-equal-to.png)

在此示例中，您選擇&lt;=運算子，如螢幕截圖所示。 如果使用者在過去5天內符合三個[!UICONTROL traits]中任一個的資格，這至少會有三次符合[!UICONTROL segment]資格。 以下時間軸顯示[!UICONTROL segment]建立時（10月1日和10天後）的[!UICONTROL segment]資格。

![最近5天](assets/last-5-days.png)

### 使用大於或等於運算子(=>)

![大於等於](assets/greater-than-equal-to.png)

在此範例中，您選取=>運算子，如螢幕擷取所示。 如果使用者在Audience Manager平台上的首次資格認證與五天前的截止時間之間，至少三次符合這三個[!UICONTROL traits]中任何一個的資格，即符合[!UICONTROL segment]資格。 以下時間軸顯示[!UICONTROL segment]建立時（10月1日和10天後）的[!UICONTROL segment]資格。

![較早資格](assets/earlier-qualification.png)


## 頻率限定範例{#frequency-capping}

頻率限定運算式包含其[!UICONTROL trait]實現數量低於所需值的所有使用者。 以下是一些正確和錯誤的範例：

* 錯誤 — 表達式`frequency([1000T]) <= 5`包括ID為&quot;1000&quot;的所有已實現[!UICONTROL trait]的用戶，最多為5次，但也包括尚未實現[!UICONTROL trait]的用戶。 因此，Audience Manager不會基於效能原因來驗證此運算式，因為它會讓太多使用者符合[!UICONTROL segment]的資格。

* 右 — 如果要包括ID為&quot;1000&quot;的所有已實現[!UICONTROL trait]且最多為5次的用戶，請向表達式添加其他條件，以確保用戶至少符合[!UICONTROL trait]的資格一次： `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* 右 — 當您需要的時近/頻度要求小於特定次數或天數時，請使用`AND`運算子將該[!UICONTROL trait]連結到另一個。 使用第一個項目符號點中的範例，此運算式在與另一個[!UICONTROL trait]連結時就會生效，如下所示：`frequency([1000T]) <= 5 AND isSiteVisitorTrait`。

* 右 — 若是廣告限定頻率的使用案例，您可以建立類似以下的[!UICONTROL segment]規則：`(frequency([1000T] <= 2D) >= 5)`。 此運算式包含過去2天中已實現ID為「1000」的[!UICONTROL trait]的所有使用者，至少5次。 將此[!UICONTROL segment]傳送至廣告伺服器，並在廣告伺服器的[!UICONTROL segment]上設定`NOT`，以設定頻率上限。 此方法在[!DNL Audience Manager]中實現了更高的效能，同時仍在頻率限定方面具有相同的用途。

>[!MORELIKETHIS]
>
>* [區段產生器控制項：特徵區段](../../features/segments/segment-builder.md#segment-builder-controls-traits)
* [區段運算式編輯器中使用的程式碼語法](../../features/segments/segment-code-syntax.md)

