---
description: 在段生成器中，頻率和頻率允許您根據在設定的每日間隔內發生或重複的操作對訪問者進行分段。
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: 使用間隔和頻率
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 2%

---

# 使用間隔和頻率 {#recency-and-frequency}

在 [!UICONTROL Segment Builder]、頻率和頻率，允許您根據在設定的每日間隔內發生或重複的操作對訪問者進行分段。

Audience Manager定義 [!DNL recency] 和 [!DNL frequency] 如下：

* **[!UICONTROL Recency]:** 用戶最近查看或限定一個（或多個） [!UICONTROL traits]。
* **[!UICONTROL Frequency]:** 用戶查看或限定一個（或多個）的速率 [!UICONTROL traits]。

[!UICONTROL Recency] 和 [!UICONTROL Frequency] 設定可幫助您根據訪問者對網站、部分或特定創意的真實（或感知）興趣程度對訪問者進行分類。 例如，符合高頻/頻率要求的網段的用戶可能對網站或產品更感興趣，而不是訪問頻率較低或訪問頻率較低的用戶。

## 位置 [!UICONTROL Recency and Frequency] 設定 {#location}

在 [!UICONTROL Segment Builder]。 [!UICONTROL Recency] 和 [!UICONTROL Frequency] 設定位於 [!UICONTROL Basic View] 的下界 [!UICONTROL Traits] 的子菜單。 按一下時鐘錶徵圖以公開這些控制項。

![](assets/recency_frequency.png)

## 限制和規則 {#limitations-rules}

當要將頻率和頻率應用於段中的特徵時，請查看並瞭解這些限制和規則。

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
   <td colname="col2"> <p>頻率必須大於0。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>特性類型</b> </p> </td> 
   <td colname="col2"> <p>您只能將頻率控制應用於基於規則和資料夾的特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>第三方特徵</b> </p> </td> 
   <td colname="col2"> <p>不能針對包含第三方特徵的個人第三方特徵或特徵組設定頻率規則。 頻率和頻率僅適用於您自己的特徵。 </p> </td> 
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
   <td colname="col2"> <p>不能對包含第三方特徵的個人第三方特徵或特徵組設定頻率規則。 頻率和頻率僅適用於您自己的特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>特性類型</b> </p> </td> 
   <td colname="col2"> <p>您只能將頻率控制應用於基於規則和資料夾的特性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>頻率要求</b> </p> </td> 
   <td colname="col2"> <p>您可以配置頻率要求 <i>無</i> 配置頻率要求。 只需設定一個頻率值，並將頻率欄位留空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>設定檔合併規則</b> </p> </td> 
   <td colname="col2"> <p>請參閱 <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> 特性頻率、外部設備圖形和配置檔案合併規則</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 近似示例 {#recency-examples}

下面是兩個示例，說明如何根據您在UI中的選擇來操作頻率：

### 使用小於或等於運算子(&lt;=)

![小於等於](assets/less-than-equal-to.png)

在此示例中，您選擇&lt;=運算子，如螢幕截圖所示。 這符合您的用戶 [!UICONTROL segment] 如果他們符合三項條件中的任何一項 [!UICONTROL traits] 在過去五天內至少三次。 下面的時間軸顯示 [!UICONTROL segment] 當時的資格 [!UICONTROL segment] 10月1日和10天後建立。

![最後五天](assets/last-5-days.png)

### 使用大於或等於運算子(=>)

![大於等於](assets/greater-than-equal-to.png)

在此示例中，您選擇了=>運算子，如螢幕截圖所示。 這符合您的用戶 [!UICONTROL segment] 如果他們符合三項條件中的任何一項 [!UICONTROL traits] 在他們在Audience Manager平台上獲得的首次資格與五天前的截止時間之間，至少要三次。 下面的時間軸顯示 [!UICONTROL segment] 當時的資格 [!UICONTROL segment] 10月1日和10天後建立。

![提前資格](assets/earlier-qualification.png)


## 頻率封蓋示例 {#frequency-capping}

頻率上限表達式包括其數目 [!UICONTROL trait] 實現值低於所需值。 以下是幾個正確和錯誤的示例：

* 錯誤 — 表達式 `frequency([1000T]) <= 5` 包括已實現 [!UICONTROL trait] ID為「1000」的用戶最多為5次，但也包括尚未實現 [!UICONTROL trait]。 因此，Audience Manager不會出於效能原因驗證此表達式，因為它將限定太多用戶 [!UICONTROL segment]。

* 對 — 如果要包括已實現 [!UICONTROL trait] ID為「1000」時，最多可以添加五次，向表達式添加其他條件，以確保用戶符合 [!UICONTROL trait] 至少一次：  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* 右 — 當您需要頻率/頻率要求小於特定次數或天數時，請加入 [!UICONTROL trait] 到另一個 `AND` 運算子。 使用第一個項目符號點中的示例，此表達式在與另一個項目符號點聯接時變為有效 [!UICONTROL trait] 如下所示： `frequency([1000T]) <= 5 AND isSiteVisitorTrait`。

* 右 — 對於廣告限頻使用案例，您可以建立 [!UICONTROL segment] 規則類似： `(frequency([1000T] <= 2D) >= 5)`。 此表達式包括已實現 [!UICONTROL trait] ID為&quot;1000&quot;的人至少5次。 通過發送此設定頻率上限 [!UICONTROL segment] 到ad伺服器 `NOT` 在 [!UICONTROL segment] 在ad伺服器中。 此方法在以下方面獲得了更高的效能： [!DNL Audience Manager] 同時仍為頻率封頂服務。

>[!MORELIKETHIS]
>
>* [段生成器控制項：Traits節](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [區段運算式編輯器中使用的程式碼語法](../../features/segments/segment-code-syntax.md)

