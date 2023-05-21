---
description: 在段構建器中添加和刪除特徵，以查看實際特徵群體以及實際和估計的段群體資料。 估計的人口規模資料有助於您為市場活動構建正確的細分。
seo-description: Add and remove traits in Segment Builder to see actual trait populations along with actual and estimated segment population data. The estimated population size data helps you build the right segment for your campaign.
seo-title: Trait and Segment Population Data in Segment Builder
solution: Audience Manager
title: 區段產生器的特徵和區段母體資料
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 1%

---

# [!UICONTROL Trait] 和 [!UICONTROL Segment] 中的填充資料 [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

添加和刪除 [!UICONTROL traits] 在 [!UICONTROL Segment Builder] 查看實際 [!UICONTROL trait] 人口與實際和估計的段人口資料。 估計的人口規模資料有助於您為市場活動構建正確的細分。

## [!UICONTROL Trait] 人口資料 {#trait-population-data}

[!UICONTROL Segment Builder] 顯示 [!UICONTROL Total Trait Population] 在您添加 [!UICONTROL trait] 段。 此資料顯示在所選區域周圍的藍色欄位中 [!UICONTROL trait] 的 [!UICONTROL Basic View] 的子菜單。

![](assets/trait-size.png)

下表定義了特徵群體度量：


| 量度 | 說明 |
|---------|----------|
| [!UICONTROL Total Trait Population] | 在其配置檔案中具有選定特性的唯一ID的數量。 |


## 計算實部和估計部分總體 {#calculating-real-estimated-populations}

建立新段或更改現有段時，Audience Manager最多需要24小時來顯示實際即時段和總段總數的結果。

但是，Audience Manager可以立即估計資料段的即時和總人口大小。 這些估計是基於95%置信區間的抽樣歷史資料和返回結果。

![](assets/confidence-interval.png)

在 [!UICONTROL Segment Builder]，估計總體圖上的藍條表示段大小的可能上下限範圍。 雖然過去的效能不能保證將來的結果，但估計的資料可以幫助您瞭解新段或已編輯段的潛在大小。

## 段填充資料概述 {#segment-populations}

[!UICONTROL Segment Builder] 顯示在建立和編輯段時段填充資料。

* 對於估計的段總數資料（即時和總數）, [!UICONTROL Segment Builder] 在段中添加或刪除特徵時不會自動更新圖形。 按一下 **[!UICONTROL Calculate Estimates]** 查看（或刷新）估計的人口數。

* 對於實際（即時）段總體資料（即時和總數）, [!UICONTROL Segment Builder] 載入現有段時，會自動更新段圖。 對於新段，或在現有段中添加新特徵時，實際人口資料在建立段後24小時才更新。

![](assets/segment-data.png)

有關估計和實際段填充資料的詳細資訊，請參閱以下定義。

## 估計段填充資料已定義 {#estimated-segment-population}

下表定義了估計的人口度量。

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 估計即時人口（潛在） </span> </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時看到的、在Audience Manager看到時符合該段條件的唯一訪問者的估計數。 </p> <p>在 <span class="wintitle"> 段生成器</span>最後30天的性狀群體(<span class="wintitle"> 特質總數</span>)，對於即時評估的特徵和片段可以不同。 </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">對於特徵，最後30天的指標計算過去30天內符合該特徵的獨特用戶數。 </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">對於即時評估的段，最後30天度量將計算過去某個時點（在該段中）具有某個特性的合格用戶數，並在過去30天內通過Audience Manager再次看到這些用戶數。 例如，假設你的用戶在60天前就具備了某種特質，10天前又被再次看到。 在資料中，此用戶不會被添加到特徵計數中，因為他們在30多天前首次對特徵進行了限定。 但是，它們將包括在即時評估的段的最後30天計數中。 這是因為他們在30天的時間間隔內符合該段的要求。 </li>
     </ul> </p> <p> <p>注：的 <span class="wintitle"> 估計即時人口</span> 度量不包括基於由提供的連接符合段條件的設備 <span class="wintitle"> 配置檔案合併規則</span> 使用 <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> 設備圖形選項</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 估計總人口（潛在）</span> </p> </td> 
   <td colname="col2"> <p>可能位於新段或修改段中的唯一訪問者的估計數。 與幾乎任何估計一樣，過去的業績並不保證將來的結果，但您可以使用估計的總數： </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">查看在構建段時新段或修訂段可能會到達的人數。 </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">根據目標調整段。 例如，大型部門對品牌意識活動非常有用，而較小的部門對於重點定位或重新定位活動非常有用。 </li> 
     </ul> </p> <p> <p>注：的 <span class="wintitle"> 估計總人口</span> 度量不包括基於由提供的連接符合段條件的設備 <span class="wintitle"> 配置檔案合併規則</span> 使用 <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> 設備圖形選項</a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 已定義現有（實際）段填充資料 {#existing-segment-population}

[!UICONTROL Profile Merge Rules] 影響實際即時和總人口數。 這些合計會根據 [!UICONTROL Profile Merge Rule] 段屬於是否使用設備圖形選項。 另請參見 [配置檔案合併規則選項已定義](../../features/profile-merge-rules/merge-rule-definitions.md)。

### 段填充資料 [!UICONTROL Merge Rules] 沒有 [!UICONTROL Device Graph Option]

下表定義了段被使用時的實際即時和總填充度量 [!UICONTROL Profile Merge Rule] 建立時 [!UICONTROL device graph] 的雙曲餘切值。 這些是設備選項設定 **[!UICONTROL No Device Options]** 和 **[!UICONTROL Current Device Proflie]**。

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 即時人口（現有）</span> </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時看到的、在Audience Manager看到時符合該段條件的唯一訪問者的實際數量。 </p> <p>在 <span class="wintitle"> 段生成器</span>最後30天的性狀群體(<span class="wintitle"> 特質總數</span>)，對於即時評估的特徵和片段可以不同。 </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">對於特徵，最後30天的指標計算過去30天內符合該特徵的獨特用戶數。 </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">對於即時評估的段，最後30天度量將計算過去某個時點（在該段中）具有某個特性的合格用戶數，並在過去30天內通過Audience Manager再次看到這些用戶數。 例如，假設你的用戶在60天前就具備了某種特質，10天前又被再次看到。 在資料中，此用戶不會被添加到特徵計數中，因為他們在30多天前首次對特徵進行了限定。 但是，它們將包括在即時評估的段的最後30天計數中。 這是因為他們在30天的時間間隔內符合該段的要求。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 總人口（現有）</span> </p> </td> 
   <td colname="col2"> <p>截至昨天有資格參加該節的唯一訪問者的實際人數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 段填充資料 [!UICONTROL Merge Rules] 使用 [!UICONTROL Device Graph] 選項

下表定義了段被使用時的實際即時和總填充度量 [!UICONTROL Profile Merge Rule] 用 [!DNL device graph] 的雙曲餘切值。 這些是 [!UICONTROL Profile Link Device Graph]，也請參見Wiki頁。 [!DNL Adobe] [!DNL device graph]、及其他第三方 [!DNL device graph] 可供您選擇的。


| 列A | 列B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | 即時查看的設備數與當前配置檔案(當與通過設備圖形連接的多達100個其它設備配置檔案合併時，這些配置檔案包含在Audience Manager看到的瞬間符合該段的特徵。 |
| [!UICONTROL Total Population (Existing)] | 具有配置檔案的設備總數，當與通過設備圖形連接的多達100個其它設備配置檔案合併時，這些配置檔案均符合該段的條件。 |

### 估計段總體時由於頻率和頻率表達式的限制

[!UICONTROL Segment Builder] 支援包含最多4個頻率和頻率表達式的段規則的段大小估計。 在構建段規則時選擇4個以上的頻率和頻率表達式會導致在估計總體時段估計器顯示錯誤。

### 限制 [!UICONTROL Merge Rules] 估計段總體時

目前，由於我們的分段大小估計器沒有考慮 [!UICONTROL profile merge rules]。 例如，使用 **[!UICONTROL No Authenticated Profile + Current Device Profile]** [合併規則](../../features/profile-merge-rules/merge-rule-definitions.md)。 由於目前計算分段估計數的方法，估計的種群將包括經過認證的概貌。 但是，現有段群將正確忽略經過驗證的配置檔案。

>[!MORELIKETHIS]
>
>* [設定檔合併規則與裝置圖表常見問題集](../../faq/faq-profile-merge.md)
>* [設定檔連結](../profile-merge-rules/merge-rules-overview.md)

