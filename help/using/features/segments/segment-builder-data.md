---
description: 在區段產生器中新增和移除特徵，以查看實際特徵母體以及實際和預估的區段母體資料。 預估人口大小資料可協助您為促銷活動建立正確的群體。
seo-description: 在區段產生器中新增和移除特徵，以查看實際特徵母體以及實際和預估的區段母體資料。 預估人口大小資料可協助您為促銷活動建立正確的群體。
seo-title: 區段產生器的特徵和區段母體資料
solution: Audience Manager
title: 區段產生器的特徵和區段母體資料
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: 區段
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1251'
ht-degree: 2%

---

# [!UICONTROL Trait] 和母 [!UICONTROL Segment] 體資料  [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

在[!UICONTROL Segment Builder]中新增並移除[!UICONTROL traits]，以查看實際的[!UICONTROL trait]母體，以及實際和估計的區段母體資料。 預估人口大小資料可協助您為促銷活動建立正確的群體。

## [!UICONTROL Trait] 母體資料  {#trait-population-data}

[!UICONTROL Segment Builder] 顯示 [!UICONTROL Total Trait Population] 您新增至區段的最 [!UICONTROL trait] 後一天。此資料會顯示在[!UICONTROL Basic View]區段中您選取之[!UICONTROL trait]周圍的藍色欄位中。

![](assets/trait-size.png)

下表定義特徵母體量度：


| 量度 | 說明 |
|---------|----------|
| [!UICONTROL Total Trait Population] | 設定檔中含有選取特徵的不重複ID數量。 |


## 計算實際和估計的區段母體{#calculating-real-estimated-populations}

建立新區段或變更現有區段時，Audience Manager最多需要24小時才會顯示實際即時和總區段母體的結果。

不過，Audience Manager可立即估計您區段的即時總母體大小。 這些估計是以95%信賴區間的取樣歷史資料和傳回結果為基礎。

![](assets/confidence-interval.png)

在[!UICONTROL Segment Builder]中，預估母體圖表上的藍條表示區段大小的可能上限和下限。 雖然過去的效能無法保證未來的結果，但預估資料可協助您了解新區段或已編輯區段的潛在大小。

## 區段母體資料概述{#segment-populations}

[!UICONTROL Segment Builder] 在您建立和編輯區段時顯示區段母體資料。

* 對於預計的區段母體資料（即時和總計），當您在區段中新增或移除特徵時，[!UICONTROL Segment Builder]不會自動更新圖形。 按一下&#x200B;**[!UICONTROL Calculate Estimates]**&#x200B;查看（或刷新）估計的人口數。

* 對於實際（即時）區段母體資料（即時和總計）,[!UICONTROL Segment Builder]會在您載入現有區段時自動更新區段圖表。 若為新區段，或您將新特徵新增至現有區段時，實際母體資料要等到區段建立後24小時才會更新。

![](assets/segment-data.png)

請參閱下列定義，以取得估計和實際區段母體資料的詳細資訊。

## 預計的區段母體資料定義{#estimated-segment-population}

下表定義了預估母體量度。

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 估計即時人口（潛在）  </span> </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時檢視的預估獨特訪客數，以及在Audience Manager看到區段時符合區段資格的訪客數。 </p> <p>在<span class="wintitle">區段產生器</span>中，特徵的最近30天母體（<span class="wintitle">特徵母體總數</span>）可能會因特徵而有所不同，且會即時評估。 </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">針對特徵，最近30天量度會計算過去30天內符合該特徵資格的不重複使用者人數。 </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">對於即時評估的區段，最近30天量度會計算過去某個時間點符合特徵資格（在該區段中），且在過去30天內經Audience Manager再次看見的使用者人數。 例如，假設您有一個使用者在60天前符合特徵資格，並在10天前再次被看到。 在資料中，此使用者不會新增至特徵計數，因為他們在30天前首次符合特徵資格。 不過，這些量度會包含在即時評估之區段的最近30天計數中。 這是因為他們在30天的時間間隔內符合區段資格。 </li>
     </ul> </p> <p> <p>注意：<span class="wintitle">預估即時母體</span>量度不包含根據<span class="wintitle">設定檔合併規則</span>所提供的連線符合區段資格的裝置，該規則使用<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">裝置圖表選項</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 估計總人口（潛在）</span> </p> </td> 
   <td colname="col2"> <p>新區段或修改區段中可能包含的預估獨特訪客數。 與幾乎任何估計一樣，過去績效不能保證將來結果，但您可以將估計總計用於： </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">查看在您建立區段時，新區段或修訂區段可能觸及的人數。 </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">根據您的目標調整區段。 例如，大型區段對品牌認知度促銷活動很有用，而較小的區段對於重點鎖定目標或重新定位促銷活動很有用。 </li> 
     </ul> </p> <p> <p>注意：「<span class="wintitle">預計總母體</span>」量度不包含根據<span class="wintitle">設定檔合併規則</span>所提供的連線符合區段資格的裝置，該規則使用<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">裝置圖表選項</a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 定義的現有（實際）區段母體資料{#existing-segment-population}

[!UICONTROL Profile Merge Rules] 會影響實際的即時和總人口數。這些總計會依區段所屬的[!UICONTROL Profile Merge Rule]是否使用裝置圖表選項而有所不同。 另請參閱[定義的配置檔案合併規則選項](../../features/profile-merge-rules/merge-rule-definitions.md)。

### [!UICONTROL Merge Rules]不含[!UICONTROL Device Graph Option]的區段母體資料

下表定義當您的區段由未使用[!UICONTROL device graph]選項建立的[!UICONTROL Profile Merge Rule]使用時，實際的即時和總母體量度。 這些是設備選項設定&#x200B;**[!UICONTROL No Device Options]**&#x200B;和&#x200B;**[!UICONTROL Current Device Proflie]**。

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 即時母體（現有）</span> </p> </td> 
   <td colname="col2"> <p>指定時間範圍內即時檢視的實際不重複訪客數，以及在Audience Manager看到區段時符合區段資格的訪客數。 </p> <p>在<span class="wintitle">區段產生器</span>中，特徵的最近30天母體（<span class="wintitle">特徵母體總數</span>）可能因即時評估的特徵和區段而有所不同。 </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">針對特徵，最近30天量度會計算過去30天內符合該特徵資格的不重複使用者人數。 </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">對於即時評估的區段，最近30天量度會計算過去某個時間點符合特徵資格（在該區段中），且在過去30天內經Audience Manager再次看見的使用者人數。 例如，假設您有一個使用者在60天前符合特徵資格，並在10天前再次被看到。 在資料中，此使用者不會新增至特徵計數，因為他們在30天前首次符合特徵資格。 不過，這些量度會包含在即時評估之區段的最近30天計數中。 這是因為他們在30天的時間間隔內符合區段資格。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 總人口（現有）</span> </p> </td> 
   <td colname="col2"> <p>截至昨天符合區段資格的實際不重複訪客數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 使用[!UICONTROL Device Graph]選項劃分[!UICONTROL Merge Rules]的母體資料

下表定義使用[!DNL device graph]選項建立的[!UICONTROL Profile Merge Rule]使用區段時的實際即時和總母體量度。 這些是可供您使用的[!UICONTROL Profile Link Device Graph]、[!DNL Adobe] [!DNL device graph]和其他協力廠商[!DNL device graph]選項的裝置選項設定。


| 欄A | 欄B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | 具有目前設定檔的即時實際裝置數量，當與由裝置圖表連結的最多100個其他裝置設定檔合併時，這些設定檔會包含在Audience Manager看到區段時符合區段資格的特徵。 |
| [!UICONTROL Total Population (Existing)] | 具有設定檔的裝置總數，在與由裝置圖表連線的最多100個其他裝置設定檔合併時，皆符合區段資格。 |

### 預估區段母體時，時近和頻率運算式所造成的限制

[!UICONTROL Segment Builder] 支援對包含最多4個時近和頻率運算式的區段規則進行區段大小估計。在建立區段規則時選擇超過4個時近和頻率運算式，會導致區段估計器在估計母體時顯示錯誤。

### [!UICONTROL Merge Rules]在預估區段母體時的限制

目前，已知存在限制，因為我們的區段大小估計器不考慮[!UICONTROL profile merge rules]。 例如，查看具有&#x200B;**[!UICONTROL No Authenticated Profile + Current Device Profile]** [合併規則](../../features/profile-merge-rules/merge-rule-definitions.md)的區段。 由於目前計算區段估計數的方式，估計的母體將包含已驗證的設定檔。 不過，現有的區段母體會正確忽略已驗證的設定檔。

>[!MORELIKETHIS]
>
>* [設定檔合併規則與裝置圖表常見問題集](../../faq/faq-profile-merge.md)
* [設定檔連結](../profile-merge-rules/merge-rules-overview.md)

