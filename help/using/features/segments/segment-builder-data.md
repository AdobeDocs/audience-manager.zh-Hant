---
description: 在「區段產生器」中新增和移除特徵，以查看實際特徵人口族群以及實際和估計的區段人口資料。 預計的人口大小資料可協助您為促銷活動建立正確的群體。
seo-description: 在「區段產生器」中新增和移除特徵，以查看實際特徵人口族群以及實際和估計的區段人口資料。 預計的人口大小資料可協助您為促銷活動建立正確的群體。
seo-title: 區段產生器的特徵和區段母體資料
solution: Audience Manager
title: 區段產生器的特徵和區段母體資料
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 2%

---


# [!UICONTROL Trait] 和 [!UICONTROL Segment] 人口資料  [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

新增並移除[!UICONTROL Segment Builder]中的[!UICONTROL traits]，以查看實際的[!UICONTROL trait]人口族群以及實際和估計的區段人口族群資料。 預計的人口大小資料可協助您為促銷活動建立正確的群體。

## [!UICONTROL Trait] 人口資料  {#trait-population-data}

[!UICONTROL Segment Builder] 顯示 [!UICONTROL Total Trait Population] 您新增至區段的 [!UICONTROL trait] 最後一天。此資料會出現在您選取之[!UICONTROL trait]的[!UICONTROL Basic View]區段周圍的藍色欄位中。

![](assets/trait-size.png)

下表定義特徵人口量度：


| 量度 | 說明 |
---------|----------|
| [!UICONTROL Total Trait Population] | 在其描述檔中具有選取特徵的唯一ID數。 |


## 計算實際和估計的段總體{#calculating-real-estimated-populations}

當您建立新區段或變更現有區段時，Audience Manager最多需要24小時來顯示實際即時和總區段人口的結果。

不過，Audience Manager可立即估計您區段的即時和總人口大小。 這些估計是以取樣的歷史資料和95%信賴區間的回報結果為基礎。

![](assets/confidence-interval.png)

在[!UICONTROL Segment Builder]中，預計人口族群圖形上的藍色列，表示區段大小的可能上限和下限範圍。 雖然過去的效能無法保證未來的結果，但估計的資料可協助您瞭解新區段或已編輯區段的潛在大小。

## 區段人口資料概觀{#segment-populations}

[!UICONTROL Segment Builder] 顯示您建立和編輯區段時的區段人口資料。

* 對於估計的區段人口資料（即時和總計）,[!UICONTROL Segment Builder]不會在您新增或移除區段中的特徵時自動更新圖形。 按一下&#x200B;**[!UICONTROL Calculate Estimates]**&#x200B;查看（或刷新）估計的人口數。

* 對於實際（實際）的區段人口資料（即時和總計）,[!UICONTROL Segment Builder]會在您載入現有區段時自動更新區段圖表。 若是新區段，或當您新增特徵至現有區段時，實際人口資料在建立區段後24小時才會更新。

![](assets/segment-data.png)

請參閱以下定義，以取得有關估計和實際區段人口資料的詳細資訊。

## 預計區段人口資料定義{#estimated-segment-population}

下表定義預計的人口量度。

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
   <td colname="col2"> <p>Audience Manager在指定時間範圍內即時檢視的獨特訪客預估數量，以及在看到區段時符合資格的訪客。 </p> <p>在<span class="wintitle">區段產生器</span>中，特徵的最後30天人口族群（<span class="wintitle">總特徵人口數</span>）對於特徵和即時評估的區段可能不同。 </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">對於特徵，最近30天量度會計算在過去30天內符合該特徵的獨特使用者人數。 </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">對於即時評估的區段，最近30天量度會計算過去某個時間點符合某個特徵（在該區段中）的使用者數目，而Audience Manager在過去30天內再次檢視這些使用者。 例如，假設您有位使用者在60天前符合某個特徵的資格，而且在10天前再次被看到。 在資料中，此使用者不會新增至特徵計數，因為他們在30天前第一次符合特徵。 但是，這些變數將會納入即時評估之區段的最近30天計數中。 這是因為他們在30天的時間間隔內符合區段的資格。 </li>
     </ul> </p> <p> <p>注意：<span class="wintitle">估計即時人口</span>量度不包括根據使用<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">裝置圖形選項</a>的<span class="wintitle">描述檔合併規則</span>提供的連線符合區段條件的裝置。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 估計總人口（潛在）</span> </p> </td> 
   <td colname="col2"> <p>新區段或修改區段中可能存在的獨特訪客預估數目。 和幾乎任何估計一樣，過去的績效並不保證未來的結果，但您可以使用估計的總計： </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">瞭解建立區段時，新區段或修訂區段可能觸及多少人。 </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">視您的目標調整區段。 例如，大型群體對品牌認知促銷活動有用，而較小的群體對於目標鎖定或重新定位促銷活動有用。 </li> 
     </ul> </p> <p> <p>注意：<span class="wintitle">估計總人口</span>量度不包括根據使用<a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">裝置圖形選項</a>的<span class="wintitle">描述檔合併規則</span>所提供的連線符合區段條件的裝置。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 已定義的現有（實際）段人口資料{#existing-segment-population}

[!UICONTROL Profile Merge Rules] 影響實際的即時和總人口數。這些總計會依區段的[!UICONTROL Profile Merge Rule]是否使用裝置圖形選項而異。 另請參閱[配置檔案合併規則選項定義](../../features/profile-merge-rules/merge-rule-definitions.md)。

### [!UICONTROL Merge Rules]沒有[!UICONTROL Device Graph Option]的區段人口資料

下表定義當您的區段由未使用[!UICONTROL device graph]選項而建立的[!UICONTROL Profile Merge Rule]使用時，實際的即時和總人口量度。 這些是設備選項設定&#x200B;**[!UICONTROL No Device Options]**&#x200B;和&#x200B;**[!UICONTROL Current Device Proflie]**。

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
   <td colname="col2"> <p>Audience Manager在指定時間範圍內即時檢視的獨特訪客數，以及當他們看到區段時符合資格的訪客數。 </p> <p>在<span class="wintitle">區段產生器</span>中，特徵的最後30天人口族群（<span class="wintitle">特徵總人口數</span>）對於特徵和即時評估的區段可能不同。 </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">對於特徵，最近30天量度會計算在過去30天內符合該特徵的獨特使用者人數。 </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">對於即時評估的區段，最近30天量度會計算過去某個時間點符合某個特徵（在該區段中）的使用者數目，而Audience Manager在過去30天內再次檢視這些使用者。 例如，假設您有位使用者在60天前符合某個特徵的資格，而且在10天前再次被看到。 在資料中，此使用者不會新增至特徵計數，因為他們在30天前第一次符合特徵。 但是，這些變數將會納入即時評估之區段的最近30天計數中。 這是因為他們在30天的時間間隔內符合區段的資格。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 總人口（現有）</span> </p> </td> 
   <td colname="col2"> <p>截至昨日符合區段資格的實際獨特訪客數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 具有[!UICONTROL Device Graph]選項的[!UICONTROL Merge Rules]區段人口資料

下表定義當使用[!DNL device graph]選項建立的[!UICONTROL Profile Merge Rule]使用區段時，實際的即時和總人口量度。 這些是可供您使用的[!UICONTROL Profile Link Device Graph]、[!DNL Adobe] [!DNL device graph]和其他協力廠商[!DNL device graph]選項的裝置選項設定。


| 欄A | 欄B |
---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | 即時檢視的裝置數目與目前的設定檔，當與裝置圖形連接的多達100個其他裝置設定檔合併時，這些設定檔包含Audience Manager檢視時符合區段的特性。 |
| [!UICONTROL Total Population (Existing)] | 具有設定檔的裝置總數，當與裝置圖形連接的多達100個其他裝置設定檔合併時，這些設定檔都符合區段的資格。 |

### 估計區段族群時，由於時近和頻率表達的限制

[!UICONTROL Segment Builder] 支援區段規則的區段大小估計，其中最多包含4個時近和頻率運算式。在建立區段規則時選擇4個以上的時近和頻率表達式，會造成區段估計器在估計人口族群時顯示錯誤。

### [!UICONTROL Merge Rules]在估計區段人口族群時的限制

目前，已知的限制是因為我們的區段大小估計器不包含[!UICONTROL profile merge rules]。 例如，查看具有&#x200B;**[!UICONTROL No Authenticated Profile + Current Device Profile]** [合併規則](../../features/profile-merge-rules/merge-rule-definitions.md)的區段。 由於我們目前計算分段估計數的方式，所以估計的人口族群將包含已驗證的描述檔。 不過，現有區段人口族群會正確忽略已驗證的個人檔案。

>[!MORELIKETHIS]
>
>* [設定檔合併規則與裝置圖表常見問題集](../../faq/faq-profile-merge.md)
>* [設定檔連結](../profile-merge-rules/merge-rules-overview.md)

