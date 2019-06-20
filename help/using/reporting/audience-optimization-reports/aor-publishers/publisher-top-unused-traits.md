---
description: 「熱門未使用的特徵」會以特徵類型、資料來源和效能的形式，呈現為尚未成員成員的特徵散布圖。
seo-description: 「熱門未使用的特徵」會以特徵類型、資料來源和效能的形式，呈現為尚未成員成員的特徵散布圖。
seo-title: 未使用的特徵
solution: Audience Manager
title: 未使用的特徵
uuid: 90bcd333-41b8-416e-aa4 e-a8661891 df50
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Top Unused Traits{#top-unused-traits}

「熱門未使用的特徵」會以特徵類型、資料來源和效能的形式，呈現為尚未成員成員的特徵散布圖。

## 使用案例 {#use-cases}

With the [!UICONTROL Top Unused Traits] report, you can analyze and compare the performance of first and third party traits that are currently not mapped to a segment. 此檢視可指出在促銷活動最佳化或新商機中使用受眾群體的最佳特徵。

## Using the Top Unused Traits Report {#using-the-report}

Use the **[!UICONTROL Data Provider Type]** controls to toggle between first party and third party traits. Select **[!UICONTROL All]** to return first and third party traits in the report.

With the **[!UICONTROL Impressions]** slider, you can select a minimum and maximum value for returned impressions. 任何負責小於或超過所設定限制的特徵，都不會顯示在報表中。

Use the **[!UICONTROL Day Range]** and **[!UICONTROL Date Through]** controls to adjust your look-back range. 請注意，此報表只能使用30天回顧期間。

Use the **[!UICONTROL Order]** drop-down box to select the web properties in your portfolio for which you want to return information.

In the **[!UICONTROL Data Provider]** drop-down box, select the data sources containing the traits you want to see in the report.

Use the **[!UICONTROL Traits]** drop-down box to select which traits you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Order IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Order] instead of the [!UICONTROL Order ID].

## Interpreting the Results {#interpreting-results}

**範例報表**

[!UICONTROL Top Unused Traits] 您的報表看起來類似下方的報表。在報表中，按一下泡泡以檢視基礎資料。

如需範例報表下表格中其他資訊的詳細資訊，請參閱說明。

![](assets/publisher_unused_traits.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 資料供應商類型</span> </p> </td> 
   <td colname="col2"> <p>指定選取的資料來源是否包含第一方或第三方特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特徵ID</span> </p> </td> 
   <td colname="col2"> <p>此特徵的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特徵名稱</span> </p> </td> 
   <td colname="col2"> <p>您或指派給此特徵的資料提供者的英數名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 訂購</span> </p> </td> 
   <td colname="col2"> <p>您看到此報表的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 曝光數</span> </p> </td> 
   <td colname="col2"> <p>此特性對您庫存的成員次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特徵獨特</span> </p> </td> 
   <td colname="col2"> <p>特徵成員的數目，在最近30天內。 </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

您在報表中的特性位置可以告訴您哪些特性可用來最佳化現有受眾群體。

位置軸上較高的特徵，就是您要在促銷活動中使用的屬性。對於低曝光次數的特徵，根據您的DFP資料，您不太可能在Web屬性上覆蓋此對象。

Look to the left of the [!UICONTROL Unique Trait Realizations] axis for highly accurate traits and to the right for traits that can drive scale.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 位置指出 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上方</b> </p> </td> 
   <td colname="col2"> <p>曝光次數很多，特徵實實度很低。 </p> <p>這是高精確受眾，目前尚未成為區段成員。考慮定位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下角</b> </p> </td> 
   <td colname="col2"> <p>印象次數偏低，特徵實實度低。 </p> <p> 排除這些特性，因為成員不會對網站屬性的印象造成影響。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上角</b> </p> </td> 
   <td colname="col2"> <p>曝光次數很高，特徵實作數高。 </p> <p>對尚未在區段中表示的對象進行高觸及。由於印象和規模的數目很高，這群對象是定位的主要候選對象。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下方</b> </p> </td> 
   <td colname="col2"> <p>印象次數偏低，特徵實實化。 </p> <p> 您可以排除這些特性，因為成員不會對網站屬性的印象造成影響。 </p> </td> 
  </tr> 
 </tbody> 
</table>
