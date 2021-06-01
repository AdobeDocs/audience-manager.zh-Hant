---
description: 「最上層未使用的特徵」會根據特徵類型、資料來源和效能，以散布圖的形式呈現，內含尚未成為區段成員的特徵。
seo-description: 「最上層未使用的特徵」會根據特徵類型、資料來源和效能，以散布圖的形式呈現，內含尚未成為區段成員的特徵。
seo-title: 最常見的未使用特徵
solution: Audience Manager
title: 最常見的未使用特徵
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: 受眾最佳化報表
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 2%

---

# 最常見的未使用特徵{#top-unused-traits}

「最上層未使用的特徵」會根據特徵類型、資料來源和效能，以散布圖的形式呈現，內含尚未成為區段成員的特徵。

## 使用案例 {#use-cases}

透過[!UICONTROL Top Unused Traits]報表，您可以分析並比較目前未對應至區段的第一方和第三方特徵的效能。 此檢視可指出受眾區段中用於促銷活動最佳化或淨新商機的最佳特徵。

## 使用前幾名未使用的特徵報表{#using-the-report}

使用&#x200B;**[!UICONTROL Data Provider Type]**&#x200B;控制項，在第一方和第三方特徵之間切換。 選取&#x200B;**[!UICONTROL All]**&#x200B;以在報表中傳回第一方和第三方特徵。

使用&#x200B;**[!UICONTROL Impressions]**&#x200B;滑桿，您可以為傳回曝光次數選取最小值和最大值。 任何導致的特徵數量低於或超過您設定的限制數量，都不會顯示在報表中。

使用&#x200B;**[!UICONTROL Day Range]**&#x200B;和&#x200B;**[!UICONTROL Date Through]**&#x200B;控制項來調整回顧範圍。 請注意，此報表僅提供30天回顧期間。

使用&#x200B;**[!UICONTROL Order]**&#x200B;下拉框選擇要返回資訊的產品組合中的Web屬性。

在&#x200B;**[!UICONTROL Data Provider]**&#x200B;下拉式方塊中，選取包含您要在報表中查看之特徵的資料來源。

使用&#x200B;**[!UICONTROL Traits]**&#x200B;下拉式方塊，選取您要在報表中查看哪些特徵。

>[!IMPORTANT]
>
>啟用[!UICONTROL Audience Optimization for Publishers]時，您必須包含[!UICONTROL Order IDs]的描述性中繼資料，如[將Google Ad Manager（前身為DFP）資料檔案匯入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步驟3所述。 通過執行此操作，您可以確保報告將Web屬性詳細資訊為[!UICONTROL Order]，而不是[!UICONTROL Order ID]。

## 解釋結果{#interpreting-results}

**範例報表**

您的[!UICONTROL Top Unused Traits]報表看起來可能類似於下列報表。 在報表中，按一下泡泡以檢視基礎資料。

如需詳細資訊，請參閱範例報表下表的說明。

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
   <td colname="col1"> <p><span class="wintitle"> 資料提供者類型</span> </p> </td> 
   <td colname="col2"> <p>指定所選資料來源包含第一方或第三方特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特徵ID</span> </p> </td> 
   <td colname="col2"> <p>此特徵的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特徵名稱</span> </p> </td> 
   <td colname="col2"> <p>您或指派給此特徵的資料提供者的字母數字名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 訂購</span> </p> </td> 
   <td colname="col2"> <p>您看到此報表的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 曝光數</span> </p> </td> 
   <td colname="col2"> <p>此特徵的成員接觸到您詳細目錄的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特徵不重複值</span> </p> </td> 
   <td colname="col2"> <p>過去30天內的特徵成員數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

特徵在報表中的位置可告訴您許多可用來最佳化現有受眾區段的特徵。

位於「曝光數」軸上較高的特徵是您要用於行銷活動的特徵。 對於曝光次數較低的特徵，根據您的[!DNL Google Ad Manager]資料，您不太可能在Web屬性上找到此對象。

查看[!UICONTROL Unique Trait Realizations]軸左側是否有高度精確的特徵，右側是否有可推動縮放的特徵。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 放置指示 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上角</b> </p> </td> 
   <td colname="col2"> <p>曝光次數多、特徵實現次數少。 </p> <p>這是尚未成為區段成員的高度精確受眾。 請考慮定位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下角</b> </p> </td> 
   <td colname="col2"> <p>曝光次數少、特徵實現次數少。 </p> <p> 排除這些特徵，因為成員不會對Web屬性上的曝光數有所貢獻。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上角</b> </p> </td> 
   <td colname="col2"> <p>曝光次數多、特徵實現次數多。 </p> <p>對尚未在區段中表示的對象的高觸及。 由於曝光次數和規模高，此對象是鎖定目標的主要候選對象。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下角</b> </p> </td> 
   <td colname="col2"> <p>曝光次數少、特徵實現次數多。 </p> <p> 您可以排除這些特徵，因為成員不會對Web屬性上的曝光數有所貢獻。 </p> </td> 
  </tr> 
 </tbody> 
</table>
