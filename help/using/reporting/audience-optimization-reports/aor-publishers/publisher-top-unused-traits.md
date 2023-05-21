---
description: Top Unused Traits表示為一個散點圖，表示的是尚未成為段成員的特性，這些特徵基於特性類型、資料源和效能。
seo-description: Top Unused Traits are represented as a scatter diagram of traits that are not yet members of a segment, based on trait type, data source, and performance.
seo-title: Top Unused Traits
solution: Audience Manager
title: 最常見的未使用特徵
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Audience Optimization Reports
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 1%

---

# 最常見的未使用特徵{#top-unused-traits}

Top Unused Traits表示為一個散點圖，表示的是尚未成為段成員的特性，這些特徵基於特性類型、資料源和效能。

## 使用案例 {#use-cases}

使用 [!UICONTROL Top Unused Traits] 報告中，您可以分析和比較當前未映射到段的第一和第三方特徵的效能。 此視圖可以指出受眾部分用於市場活動優化或淨化新機會的最佳特徵。

## 使用「Top Unused Traits」報告 {#using-the-report}

使用 **[!UICONTROL Data Provider Type]** 控制項在第一方和第三方特徵之間切換。 選擇 **[!UICONTROL All]** 在報告中返回第一和第三方特徵。

使用 **[!UICONTROL Impressions]** 滑塊，可為返回的印象選擇一個最小值和最大值。 報告中不顯示任何小於或大於您設定的限制的特徵。

使用 **[!UICONTROL Day Range]** 和 **[!UICONTROL Date Through]** 控制項來調整回顧範圍。 請注意，此報告只有30天的回顧期可用。

使用 **[!UICONTROL Order]** 下拉框，選擇要返回其資訊的產品組合中的Web屬性。

在 **[!UICONTROL Data Provider]** 下拉框中，選擇包含要在報告中查看的特徵的資料源。

使用 **[!UICONTROL Traits]** 下拉框，以選擇要在報表中查看的特徵。

>[!IMPORTANT]
>
>啟用時 [!UICONTROL Audience Optimization for Publishers]，必須包括描述性元資料 [!UICONTROL Order IDs]，如第3步中所述 [將GoogleAd Manager（以前叫DFP）資料檔案導入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 通過執行此操作，您可以確保報告將Web屬性的詳細資訊 [!UICONTROL Order] 而不是 [!UICONTROL Order ID]。

## 解釋結果 {#interpreting-results}

**示例報告**

您 [!UICONTROL Top Unused Traits] 報告可能與下面的報告相似。 在報告中，按一下一個氣泡來查看基礎資料。

有關示例報告下表中的附加資訊，請參閱說明。

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
   <td colname="col1"> <p><span class="wintitle"> 資料提供程式類型</span> </p> </td> 
   <td colname="col2"> <p>指定所選資料源是包含第一方特徵還是包含第三方特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特性ID</span> </p> </td> 
   <td colname="col2"> <p>這個特徵的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特性名稱</span> </p> </td> 
   <td colname="col2"> <p>您或分配給該特性的資料提供程式的字母數字名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 訂購</span> </p> </td> 
   <td colname="col2"> <p>您正在查看此報告的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 曝光數</span> </p> </td> 
   <td colname="col2"> <p>此特性的成員接觸您的清單的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特萊烏尼克斯</span> </p> </td> 
   <td colname="col2"> <p>過去30天內的特質成員數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

在報告中，你的特徵所處的位置，可以告訴你很多關於哪些特徵可以用於優化現有受眾群體。

在「印象」軸上位置較高的特徵是您希望在市場活動中使用的特徵。 對於印象較少的特徵，基於您的Web屬性，您不太可能接觸到這些受眾 [!DNL Google Ad Manager] 資料。

左側 [!UICONTROL Unique Trait Realizations] 軸用於高精度的特徵，右側用於可驅動比例的特徵。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 放置指示 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上</b> </p> </td> 
   <td colname="col2"> <p>印象多，特質實現少。 </p> <p>這是一個非常準確的受眾，但尚未加入該網段。 考慮瞄準。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下</b> </p> </td> 
   <td colname="col2"> <p>印象少，實現特質少。 </p> <p> 排除這些特徵，因為成員不會對您的Web屬性上的印象做出貢獻。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上</b> </p> </td> 
   <td colname="col2"> <p>印象多，特質實現多。 </p> <p>對尚未在段中標籤的受眾進行高覆蓋。 由於觀眾印象多，規模大，因此是最佳目標。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下</b> </p> </td> 
   <td colname="col2"> <p>印象少，實現特質多。 </p> <p> 您可以排除這些特徵，因為成員不會對Web屬性上的印象做出貢獻。 </p> </td> 
  </tr> 
 </tbody> 
</table>
