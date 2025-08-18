---
description: 排名最前的未使用特徵會根據特徵型別、資料來源和效能，以區段成員的特徵散佈圖表示。
seo-description: Top Unused Traits are represented as a scatter diagram of traits that are not yet members of a segment, based on trait type, data source, and performance.
seo-title: Top Unused Traits
solution: Audience Manager
title: 最常見的未使用特徵
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Audience Optimization Reports
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 0%

---

# 最常見的未使用特徵{#top-unused-traits}

排名最前的未使用特徵會根據特徵型別、資料來源和效能，以區段成員的特徵散佈圖表示。

## 使用案例 {#use-cases}

透過[!UICONTROL Top Unused Traits]報表，您可以分析和比較目前未對應至區段的第一方和第三方特徵的效能。 此檢視可指出要用於對象區段的最佳特徵，以便用於行銷活動最佳化或全新商機。

## 使用「排名最前的未使用特徵報表」 {#using-the-report}

使用&#x200B;**[!UICONTROL Data Provider Type]**&#x200B;控制項在第一方和第三方特徵之間切換。 選取&#x200B;**[!UICONTROL All]**&#x200B;以傳回報表中的第一方和第三方特徵。

使用&#x200B;**[!UICONTROL Impressions]**&#x200B;滑桿，您可以選取傳回曝光的最小值和最大值。 任何造成限制數量小於或大於您設定上限的特徵都不會顯示在報表中。

使用&#x200B;**[!UICONTROL Day Range]**&#x200B;和&#x200B;**[!UICONTROL Date Through]**&#x200B;控制項來調整您的回顧範圍。 請注意，此報表僅提供30天回顧期間。

使用&#x200B;**[!UICONTROL Order]**&#x200B;下拉式方塊選取投資組合中您要傳回資訊的Web屬性。

在&#x200B;**[!UICONTROL Data Provider]**&#x200B;下拉式方塊中，選取包含您要在報表中看到之特徵的資料來源。

使用&#x200B;**[!UICONTROL Traits]**&#x200B;下拉式方塊來選取您要在報表中檢視哪些特徵。

>[!IMPORTANT]
>
>啟用[!UICONTROL Audience Optimization for Publishers]時，您必須包含[!UICONTROL Order IDs]的描述性中繼資料，如[將Google Ad Manager （前身為DFP）資料檔案匯入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步驟3中所述。 透過這樣做，您可以確保報告將Web屬性詳細資料顯示為[!UICONTROL Order]，而不是[!UICONTROL Order ID]。

## 解譯結果 {#interpreting-results}

**範例報告**

您的[!UICONTROL Top Unused Traits]報告可能類似於下面的報告。 在報表中，按一下泡泡圖以檢視基礎資料。

如需範例報表下表中其他資訊的說明，請參閱。

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
   <td colname="col1"> <p><span class="wintitle">資料提供者型別</span> </p> </td> 
   <td colname="col2"> <p>指定選取的資料來源是否包含第一方或第三方特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">特徵ID</span> </p> </td> 
   <td colname="col2"> <p>此特徵的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">特徵名稱</span> </p> </td> 
   <td colname="col2"> <p>您或指派給此特徵的資料提供者的英數字元名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">訂單</span> </p> </td> 
   <td colname="col2"> <p>您要檢視此報表的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">曝光次數</span> </p> </td> 
   <td colname="col2"> <p>此特徵的成員已向您的詳細目錄公開的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">特徵不重複</span> </p> </td> 
   <td colname="col2"> <p>過去30天內的特徵成員數量。 </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

特徵在報表中的位置可告知您可用來將現有受眾區段最佳化的特徵。

位於曝光數軸上較高位置的特徵是您想在行銷活動中使用的特徵。 針對曝光次數較少的特徵，根據您的[!DNL Google Ad Manager]資料，您不太可能會透過Web屬性觸及此對象。

請向[!UICONTROL Unique Trait Realizations]軸左邊檢視高精確度特徵，向右邊檢視可推動縮放的特徵。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 位置指示 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上方</b> </p> </td> 
   <td colname="col2"> <p>曝光次數高、特徵實現次數低。 </p> <p>這是尚未成為區段成員的高精確度對象。 考慮進行目標定位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下方</b> </p> </td> 
   <td colname="col2"> <p>曝光次數低、特徵實現次數低。 </p> <p> 排除這些特徵，因為成員不會貢獻您網頁屬性的曝光數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上方</b> </p> </td> 
   <td colname="col2"> <p>高曝光次數、高特徵實現次數。 </p> <p>針對尚未在區段中標示的受眾的高觸及率。 由於曝光次數和規模龐大，此對象是目標定位的主要候選對象。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下方</b> </p> </td> 
   <td colname="col2"> <p>曝光次數低、特徵實現次數高。 </p> <p> 您可以排除這些特徵，因為成員不會對Web屬性的曝光數產生影響。 </p> </td> 
  </tr> 
 </tbody> 
</table>
