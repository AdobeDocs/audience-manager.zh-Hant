---
description: 在區段產生器中新增及移除特徵，以檢視實際特徵母體以及實際和預估的區段母體資料。 預估母體大小資料可協助您為行銷活動建立正確的區段。
seo-description: Add and remove traits in Segment Builder to see actual trait populations along with actual and estimated segment population data. The estimated population size data helps you build the right segment for your campaign.
seo-title: Trait and Segment Population Data in Segment Builder
solution: Audience Manager
title: 區段產生器的特徵和區段母體資料
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 1%

---

# [!UICONTROL Segment Builder]中的[!UICONTROL Trait]和[!UICONTROL Segment]母體資料 {#trait-and-segment-population-data-in-segment-builder}

新增和移除[!UICONTROL Segment Builder]中的[!UICONTROL traits]，以檢視實際[!UICONTROL trait]母體以及實際和預估的區段母體資料。 預估母體大小資料可協助您為行銷活動建立正確的區段。

## [!UICONTROL Trait]母體資料 {#trait-population-data}

當您將[!UICONTROL trait]新增至區段時，[!UICONTROL Segment Builder]會顯示最後一天的[!UICONTROL Total Trait Population]。 此資料會出現在[!UICONTROL Basic View]區段中選定[!UICONTROL trait]周圍的藍色欄位中。

![](assets/trait-size.png)

下表定義特徵母體量度：


| 量度 | 說明 |
|---------|----------|
| [!UICONTROL Total Trait Population] | 在其個人資料中具有所選特徵的唯一ID數量。 |


## 計算實際和預估的區段母體 {#calculating-real-estimated-populations}

建立新區段或變更現有區段時，Audience Manager最多需要24小時才能顯示實際即時和區段總母體的結果。

不過，Audience Manager可以立即估計區段的即時和總母體大小。 這些估計值是根據取樣的歷史資料和95%信賴區間的傳回結果。

![](assets/confidence-interval.png)

在[!UICONTROL Segment Builder]中，預估母體圖表上的藍色長條表示區段大小的上限和下限範圍。 雖然過去的效能無法保證未來的結果，但預估資料可協助您瞭解新區段或已編輯區段的潛在大小。

## 區段母體資料概述 {#segment-populations}

[!UICONTROL Segment Builder]會在您建立和編輯區段時顯示區段母體資料。

* 針對預估的區段母體資料（即時和總計），[!UICONTROL Segment Builder]不會在您新增或移除區段中的特徵時自動更新圖表。 按一下&#x200B;**[!UICONTROL Calculate Estimates]**&#x200B;以檢視（或重新整理）預估的母體數目。

* 若為實際（即時）區段母體資料（即時與總計），[!UICONTROL Segment Builder]會在您載入現有區段時自動更新區段圖表。 如果是新區段，或是在現有區段新增新特徵時，實際母體資料要在區段建立後24小時才會更新。

![](assets/segment-data.png)

請參閱下列定義，以取得預估和實際區段母體資料的詳細資訊。

## 已定義的預估區段母體資料 {#estimated-segment-population}

下表定義預估母體量度。

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">預估的即時母體（潛在） </span> </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時檢視的不重複訪客的預估數量，以及在Audience Manager看到符合區段資格的人。 </p> <p>在<span class="wintitle">區段產生器</span>中，特徵的最後30天母體（<span class="wintitle">個總特徵母體</span>）可能會因為即時評估的特徵和區段而有所不同。 </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">針對特徵，過去30天的量度會計算過去30天內符合該特徵的不重複使用者人數。 </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">對於即時評估的區段，過去30天的量度會計算過去某個時間點符合某個特徵（在該區段中）的使用者人數，以及過去30天內被Audience Manager再次檢視的使用者人數。 例如，假設您的使用者符合60天前的特徵資格，但10天前再次出現。 在資料中，此使用者將不會新增至特徵計數，因為他們在30多天前才首次符合特徵。 不過，對於即時評估的區段，這些將被納入最後30天的計數。 這是因為他們已在30天時間間隔內符合區段的資格。 </li>
     </ul> </p> <p> <p>注意： <span class="wintitle">預估即時母體</span>量度不包含根據使用<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">裝置圖表選項</a>的<span class="wintitle">設定檔合併規則</span>所提供的連線符合區段資格的裝置。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">估計總母體（潛在）</span> </p> </td> 
   <td colname="col2"> <p>可能位於您新區段或修改的區段中的不重複訪客預估數量。 和幾乎任何預估一樣，過去的效能無法保證未來的結果，但您可以將預估總計用於： </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">瞭解當您建立區段時，新區段或修訂區段可以影響多少人。 </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">根據您的目標調整區段。 例如，大型區段對品牌認知度行銷活動相當實用，而小型區段對重點鎖定目標或重新鎖定目標行銷活動相當實用。 </li> 
     </ul> </p> <p> <p>注意： <span class="wintitle">預估總母體</span>量度不包含根據使用<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">裝置圖表選項</a>的<span class="wintitle">設定檔合併規則</span>所提供的連線符合區段資格的裝置。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 已定義的現有（實際）區段母體資料 {#existing-segment-population}

[!UICONTROL Profile Merge Rules]會影響實際的即時和母體總數。 這些總計會依區段所屬的[!UICONTROL Profile Merge Rule]是否使用裝置圖表選項而有所不同。 另請參閱[定義的設定檔合併規則選項](../../features/profile-merge-rules/merge-rule-definitions.md)。

### 不含[!UICONTROL Device Graph Option]的[!UICONTROL Merge Rules]區段母體資料

下表定義當您的區段由不含[!UICONTROL device graph]選項而建立的[!UICONTROL Profile Merge Rule]使用時，實際的即時和總母體量度。 這些是裝置選項設定&#x200B;**[!UICONTROL No Device Options]**&#x200B;和&#x200B;**[!UICONTROL Current Device Proflie]**。

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">即時母體（現有）</span> </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時檢視的實際不重複訪客數量，以及在Audience Manager看到符合區段資格的人數。 </p> <p>在<span class="wintitle">區段產生器</span>中，特徵的最後30天母體（<span class="wintitle">個總特徵母體</span>）對於即時評估的特徵和區段可能不同。 </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">針對特徵，過去30天的量度會計算過去30天內符合該特徵的不重複使用者人數。 </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">對於即時評估的區段，過去30天的量度會計算過去某個時間點符合某個特徵（在該區段中）的使用者人數，以及過去30天內被Audience Manager再次檢視的使用者人數。 例如，假設您的使用者符合60天前的特徵資格，但10天前再次出現。 在資料中，此使用者將不會新增至特徵計數，因為他們在30多天前才首次符合特徵。 不過，對於即時評估的區段，這些將被納入最後30天的計數。 這是因為他們已在30天時間間隔內符合區段的資格。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">總母體（現有）</span> </p> </td> 
   <td colname="col2"> <p>截至昨天符合區段資格的實際不重複訪客數量。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 使用[!UICONTROL Device Graph]選項的[!UICONTROL Merge Rules]區段母體資料

當以[!DNL device graph]選項建立的[!UICONTROL Profile Merge Rule]使用您的區段時，下表定義實際的即時和母體總數量度。 這些是[!UICONTROL Profile Link Device Graph]、[!DNL Adobe] [!DNL device graph]和其他協力廠商[!DNL device graph]選項可供您使用的裝置選項設定。


| 欄A | 欄B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing)] | 使用目前設定檔即時檢視的實際裝置數，這些設定檔與最多透過裝置圖表連線的100個其他裝置設定檔合併時，包含在Audience Manager看到區段時符合資格的特徵。 |
| [!UICONTROL Total Population (Existing)] | 包含設定檔的裝置總數，這些設定檔與最多透過裝置圖表連線的100個其他裝置設定檔合併時，都符合區段的資格。 |

### 估算區段母體時，造訪間隔和頻率運算式造成的限制

[!UICONTROL Segment Builder]支援區段規則的區段大小估計，這些區段規則包含最多4個造訪間隔和頻率運算式。 建立區段規則時，選擇超過4個造訪間隔和頻率運算式，會導致區段估算器在估算母體時顯示錯誤。

### 估算區段母體時由於[!UICONTROL Merge Rules]的限制

目前已知限制，因為我們的區段大小估算程式未考慮[!UICONTROL profile merge rules]。 例如，檢視具有&#x200B;**[!UICONTROL No Authenticated Profile + Current Device Profile]** [合併規則](../../features/profile-merge-rules/merge-rule-definitions.md)的區段。 由於我們目前計算區段估計數字的方式，估計母體將包含已驗證的設定檔。 不過，現有的區段母體將正確地忽略已驗證的設定檔。

>[!MORELIKETHIS]
>
>* [設定檔合併規則與裝置圖表常見問題集](../../faq/faq-profile-merge.md)
>* [設定檔連結](../profile-merge-rules/merge-rules-overview.md)
