---
description: 新增和移除「區段產生器」中的特徵，以查看實際特徵人口族群以及實際和預計的群體人口資料。預估的人口大小資料可協助您建立促銷活動的正確區段。
seo-description: 新增和移除「區段產生器」中的特徵，以查看實際特徵人口族群以及實際和預計的群體人口資料。預估的人口大小資料可協助您建立促銷活動的正確區段。
seo-title: 區段產生器中的特徵和區段人口資料
solution: Audience Manager
title: 區段產生器中的特徵和區段人口資料
uuid: e1e59c0a-b4 c7-4dap-8485-3667e0 a95 e83
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Trait and Segment Population Data in Segment Builder {#trait-and-segment-population-data-in-segment-builder}

Add and remove traits in [!UICONTROL Segment Builder] to see actual trait populations along with actual and estimated segment population data. 預估的人口大小資料可協助您建立促銷活動的正確區段。

## Trait Population Data {#trait-population-data}

[!UICONTROL Segment Builder] 顯示 [!UICONTROL Total Trait Population] 您在新增特徵至區段時的最後一天。This data appears in the blue field around your selected trait in the [!UICONTROL Basic View] section.

![](assets/trait-size.png)

下表定義特徵人口度量

<table id="table_9D837CF9ACA04D04BEE5925EC0B4A5D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 特徵總人數</span> </p> </td>
   <td colname="col2"> <p>在其描述檔中具有所選特徵的唯一ID數目。 </p> </td>
  </tr> 
 </tbody> 
</table>

## Calculating Real and Estimated Segment Populations {#calculating-real-estimated-populations}

當您建立新區段或變更現有區段時，Audience Manager最多需要24小時來顯示實際即時和區段人口族群的結果。

不過，Audience Manager可立即估計您區段的即時和總人口大小。這些估計是根據取樣歷史資料，並在95%信賴區間傳回結果。

![](assets/confidence-interval.png)

In [!UICONTROL Segment Builder], a blue bar on the estimated population graphs indicates the possible upper and lower ranges for segment size. 雖然過去的效能不保證未來的結果，但預估的資料可協助您瞭解新的或編輯區段的潛在大小。

## Segment Population Data Overview {#segment-populations}

[!UICONTROL Segment Builder] 顯示您建立和編輯區段時區段人口資料。

* For estimated segment population data (real-time and total), [!UICONTROL Segment Builder] does not update the graphs automatically as you add or remove traits in a segment. Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers.

* For actual (real) segment population data (real-time and total), [!UICONTROL Segment Builder] updates the segment graph automatically when you load an existing segment. 對於新區段，或新增特徵至現有區段，在建立區段後24小時內，實際人口資料才會更新。

![](assets/segment-data.png)

如需預估和實際區段人口資料的詳細資訊，請參閱下列定義。

## Estimated Segment Population Data Defined {#estimated-segment-population}

下表定義預計的人口度量。

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 預計的即時人口(潛在) </span> </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時看到的獨特訪客數目，以及Audience Manager看到區段時的合格訪客人數。 </p> <p><span class="wintitle"> 在區段產生器</span>中，特徵(特徵總人口族群<span class="wintitle"></span>)的最近30天人口族群，對於即時評估的特徵和區段可能不同。 </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">對於特徵，前30天量度會計入過去30天內符合該特徵之獨特使用者的數目。 </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">對於即時評估的區段，最近30天量度會計算過去在某個時間點內符合特徵的使用者人數，並在過去30天內再次被Audience Manager看到。例如，假設有位使用者符合60天試用版，在10天前再次看見。在資料中，此使用者不會新增至特徵，因為他們在30天前首次符合特徵資格。但是，它們將會納入即時評估區段的最近30天計數中。這是因為他們在30天的時間間隔內符合區段資格。 </li>
     </ul> </p> <p> <p>Note: The <span class="wintitle"> Estimated Real-Time Population</span> metric does not include devices that have qualified for a segment based on connections provided by a <span class="wintitle"> Profile Merge Rule</span> that uses a <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> device graph option</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 預計總人口人數(潛在)</span> </p> </td> 
   <td colname="col2"> <p>可能在新區段或修改後區段中的獨特訪客數。幾乎有任何估計，過去的效能並不保證未來的結果，但您可以使用預估總計來： </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">瞭解當您建立區段時，新或修訂區段可能會覆蓋多少人。 </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">視您的目標調整區段。例如，大型區段對於品牌感知促銷活動和較小群體很有用，對於目標鎖定或重新定位促銷活動很有用。 </li> 
     </ul> </p> <p> <p>Note: The <span class="wintitle"> Estimated Total Population</span> metric does not include devices that have qualified for a segment based on connections provided by a <span class="wintitle"> Profile Merge Rule</span> that uses a <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> device graph option</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Existing (Actual) Segment Population Data Defined {#existing-segment-population}

[!UICONTROL Profile Merge Rules] 會影響實際的即時和總人口數。These totals vary depending on if the [!UICONTROL Profile Merge Rule] a segment belongs to uses a device graph option or not. See also, [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md).

### 不含裝置圖表選項的合併規則區段人口資料

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created without a device graph option. These are the device options settings **[!UICONTROL No Device Options]** and **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 即時人口(現有)</span> </p> </td> 
   <td colname="col2"> <p>實際訪客在指定時間範圍內即時看到的實際數目，以及Audience Manager看到區段時的符合資格。 </p> <p><span class="wintitle"> 在區段產生器</span>中，特徵和區段的最近30天<span class="wintitle"> 人口族群(總特徵人口數</span>)可能不同於即時評估的特徵和區段。 </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">對於特徵，前30天量度會計入過去30天內符合該特徵之獨特使用者的數目。 </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">對於即時評估的區段，最近30天量度會計算過去在某個時間點內符合特徵的使用者人數，並在過去30天內再次被Audience Manager看到。例如，假設有位使用者符合60天試用版，在10天前再次看見。在資料中，此使用者不會新增至特徵，因為他們在30天前首次符合特徵資格。但是，它們將會納入即時評估區段的最近30天計數中。這是因為他們在30天的時間間隔內符合區段資格。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 總人口人數(現有)</span> </p> </td> 
   <td colname="col2"> <p>截至昨天符合區段資格的實際訪客數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 使用裝置圖表選項合併規則的區段人口資料

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created with a device graph option. These are the device options settings for the [!UICONTROL Profile Link Device Graph], the [!DNL Adobe] device graph, and other third-party device graph choices that are available to you.

<table id="table_157EC6E5B5C44EB899854CA10B090F60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 即時人口(現有)</span> </p> </td> 
   <td colname="col2"> <p>The actual number of devices seen in real-time with current profiles that, when merged with up to 3-other device profiles connected by the device graph, contains the traits to qualify for the segment the moment it was seen by <span class="keyword"> Audience Manager</span>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 總人口人數(現有)</span> </p> </td> 
   <td colname="col2"> <p>具有設定檔的裝置總數，並與裝置圖表連接的多達個其他裝置設定檔合併，這些設定檔都符合區段的資格。 </p> </td>
  </tr>
 </tbody>
</table>

### 預估區段人口族群時，由於最近一次的等待時間和頻率運算式

[!UICONTROL Segment Builder] 支援區段規則的區段大小，其中包含最多個最近一次和頻率陳述式。建立區段規則時選擇超過個最近時和頻率陳述式，會導致區段估計器在預估人口時顯示錯誤。

### 估計區段人口族群時，合併規則的限制

目前有已知的限制，因為我們的區段大小估計器不會計入描述檔合併規則。For example, look at segments with the **No Authenticated Profile + Current Device Profile** [merge rule](../../features/profile-merge-rules/merge-rule-definitions.md). 由於我們目前計算細分預估數字的方式，估計的人口族群將包含驗證的個人檔案。不過，現有區段人口族群將會正確忽略已驗證的設定檔。

>[!MORE_贊_ this]
>
>* [描述檔合併規則與裝置圖表常見問題](../../faq/faq-profile-merge.md)
>* [個人資料連結](../../features/profile-merge-rules/merge-rules-overview.md)

