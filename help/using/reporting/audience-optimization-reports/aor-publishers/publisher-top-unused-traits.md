---
description: 「最上方未使用的特徵」會根據特徵類型、資料來源和效能，以尚未成為群體成員的特徵散布圖表示。
seo-description: 「最上方未使用的特徵」會根據特徵類型、資料來源和效能，以尚未成為群體成員的特徵散布圖表示。
seo-title: 最常見的未使用特徵
solution: Audience Manager
title: 最常見的未使用特徵
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 2%

---


# 最常見的未使用特徵{#top-unused-traits}

「最上方未使用的特徵」會根據特徵類型、資料來源和效能，以尚未成為群體成員的特徵散布圖表示。

## 使用案例 {#use-cases}

透過報 [!UICONTROL Top Unused Traits] 表，您可以分析並比較目前未對應至區段的第一方和第三方特徵的效能。 此檢視可指出受眾群體中用於促銷活動最佳化或淨化新商機的最佳特徵。

## 使用排名最前的未使用特徵報表 {#using-the-report}

使用控 **[!UICONTROL Data Provider Type]** 制項在第一方和第三方特徵之間切換。 選取 **[!UICONTROL All]** 以傳回報表中的第一方和第三方特徵。

使用滑 **[!UICONTROL Impressions]** 桿，您可以為傳回的印象選取最小和最大值。 任何對您設定的限制負責或超過的特徵，都不會顯示在報表中。

使用 **[!UICONTROL Day Range]** 和 **[!UICONTROL Date Through]** 控制項來調整回顧範圍。 請注意，此報表僅提供30天回顧期。

使用下 **[!UICONTROL Order]** 拉式方塊，在您要傳回資訊的作品集中選取Web屬性。

在下拉 **[!UICONTROL Data Provider]** 式方塊中，選取包含您要在報表中查看之特徵的資料來源。

使用下 **[!UICONTROL Traits]** 拉式方塊來選取您要在報表中看到哪些特徵。

>[!IMPORTANT]
>
>啟用時， [!UICONTROL Audience Optimization for Publishers]您必須包含描述性中繼資料 [!UICONTROL Order IDs]，如 [Import Google Ad Manager（舊稱DFP）Data Files Into Audience Manager的步驟3所述](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 執行此動作後，您可確保報表會以Web屬性而非 [!UICONTROL Order] Web屬性的形式詳細說明 [!UICONTROL Order ID]。

## 解讀結果 {#interpreting-results}

**範例報表**

您 [!UICONTROL Top Unused Traits] 的報表看起來可能類似以下。 在報表中，按一下泡泡以檢視基礎資料。

請參閱範例報表下表格中的其他資訊說明。

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
   <td colname="col2"> <p>指定所選資料源是包含第一方特徵還是包含第三方特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特徵ID</span> </p> </td> 
   <td colname="col2"> <p>此特徵的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特徵名稱</span> </p> </td> 
   <td colname="col2"> <p>您或指派給此特徵的資料提供者的英數字名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 訂購</span> </p> </td> 
   <td colname="col2"> <p>您正看到此報表的Web屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 曝光數</span> </p> </td> 
   <td colname="col2"> <p>此特徵的成員接觸庫存的次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 特徵獨特值</span> </p> </td> 
   <td colname="col2"> <p>過去30天內的特徵成員數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

您的特徵在報表中的位置可以告訴您許多關於哪些特徵可用於最佳化現有受眾細分的資訊。

位於「印象」軸上方的特徵是您要在促銷活動中使用的特徵。 對於印象少的特徵，根據您的資料，您不太可能在Web屬性上觸及到此受眾 [!DNL Google Ad Manager] 。

請向左看軸以取得高 [!UICONTROL Unique Trait Realizations] 度精確的特徵，向右看可驅動比例的特徵。

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 位置 </th> 
   <th colname="col2" class="entry"> 位置指示 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>左上角</b> </p> </td> 
   <td colname="col2"> <p>曝光次數多、特徵實現次數少。 </p> <p>此為非區段成員的高精確受眾。 考慮定位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>左下角</b> </p> </td> 
   <td colname="col2"> <p>印象少，特徵實現少。 </p> <p> 排除這些特徵，因為成員不會對您的Web屬性上的印象產生影響。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右上方</b> </p> </td> 
   <td colname="col2"> <p>印象多、特徵實現多。 </p> <p>對尚未在區段中標示的觀眾的高覆蓋率。 由於曝光次數和規模龐大，此對象是鎖定目標的最佳候選對象。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>右下角</b> </p> </td> 
   <td colname="col2"> <p>印象少，特徵實現多。 </p> <p> 您可以排除這些特徵，因為成員不會對Web屬性上的印象有所貢獻。 </p> </td> 
  </tr> 
 </tbody> 
</table>
