---
description: 常見描述檔合併規則與裝置圖形問題的解答。
keywords: 組織 ID
seo-description: 常見描述檔合併規則與裝置圖形問題的解答。
seo-title: 描述檔合併規則與裝置圖表常見問答集
solution: Audience Manager
title: 描述檔合併規則與裝置圖表常見問答集
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# 描述檔合併規則與裝置圖表常見問答集{#profile-merge-rules-and-device-graph-faq}

常見描述檔合併規則與裝置圖形問題的解答。

<!-- profile-merge-faq.xml -->

## 裝置圖形基礎 {#device-graph-basics}

**什麼是裝置圖表？**

裝置圖表是一組ID映射，用於定義匿名裝置群組。 它根據從每個設備收集的信號中的公共元素，將這些設備關聯到個人或家庭。 這些信號有助於識別個人或家庭層級的設備。

 

**什麼是外部裝置圖表？**

外部裝置圖表是指並非只由 [!DNL Audience Manager] 您自己的跨裝置資料來源建立的任何裝置圖表。 例如，當您建立描述檔合 [並規則](merge-rules-start.md) ，並選擇 [!UICONTROL Co-op Device Graph] 或協力廠商裝置圖表選項時，就會使用外部裝置圖表。 請參閱 [裝置選項](merge-rule-definitions.md#device-options)。

 

**在中使用外部裝置圖表時，有哪些常見使用案例[!UICONTROL Profile Merge Rule]?**

在裝置中使用裝置圖表的主要目 [!UICONTROL Profile Merge Rule] 的是評估並限定屬於單一個人或家庭的多個裝置的特定區段。 例如，此細分本身可能有多種用途，例如以DSP所提供的廣告鎖定潛在客戶，或透過臨場感個人化平台個人化客戶的臨場感。 See [External Device Graph Use Cases](external-graph-use-cases.md).

 

**Audience manager是否提供外部裝置圖形的全域支援？**

不會。外部裝置圖表僅適用於美國和加拿大。

 

**更新外部裝[!DNL Audience Manager]置圖表資料的頻率為何？**

每週一次。

 

## 裝置圖形和描述檔合併規則 {#device-graph-profile-merge-rules}

**如何使[!DNL Audience Manager]用裝置圖表？**

在中 [!DNL Audience Manager]，當您建立描述檔合併規則時，裝置圖 [形會顯示為設定選項](merge-rules-start.md)。 透過您的 [!UICONTROL Profile Merge Rules]裝置圖表，這些裝置圖表可協助您 [!DNL Audience Manager]:

* 將多個裝置描述檔合併在一起。 這會產生單一的特徵超集。
* 評估區段資格的特徵超集（而不是個別評估每個裝置描述檔）。
* 新增合格裝置至可用區段。

 

**我可以[!UICONTROL Profile Merge Rules]建立多少？**

目前，您最多可以建立4個 [!UICONTROL Profile Merge Rules]。 第四個描述檔合[!UICONTROL All Cross-Device Profiles]並規則()僅適用於購買附加元件 [!UICONTROL People-Based Destinations] 的客戶。

 

**在中使用裝置圖[!DNL Audience Manager]形時，合併和讀取多少裝置描述檔[!UICONTROL Profile Merge Rule]?**

當使用區段來限定裝置時 [!UICONTROL Profile Merge Rule],Audience manager會合併並讀取目前的裝置設定檔，以及最多99個由您選取的裝置圖表選項連結的其他裝置設定檔。

 

**在中使用裝置圖表時，哪些裝置符合區段的資格[!UICONTROL Profile Merge Rule]?**

設備合 [!DNL Audience Manager] 並和讀取是與限定段的設備相同。

 

**哪裡可[!DNL Audience Manager]以傳送使用裝置圖形的[!UICONTROL Profile Merge Rule]符合條件的區段？**

[!DNL Audience Manager] 可以以批次檔案或即時傳送區段至目的地。

 

## 區段、裝置圖形和描述檔合併規則 {#segments-device-graphs-rules}

**當裝[!DNL Audience Manager]置不再符合使用裝置圖表之區段的資格時，如何[!UICONTROL Profile Merge Rule]取消區段？**

當使用裝置圖表來評估區段時，Audience manager會合併多達100 [!UICONTROL Profile Merge Rule] 個裝置。 如果發出未分段信號，則當前設備和最多99個附加設備將從目的地的分段中刪除。 如需取消分段的詳細資訊，請參 [閱描述檔合併規則和裝置取消分段程式](merge-rule-unsegment.md)。

 

**如果目的地可以取消區段裝置，使用裝置圖表的裝置是否[!UICONTROL Profile Merge Rules]會從區段中移除？**

是。請參閱上述說明。

 

**如果我建立的區段使用[!UICONTROL Profile Merge Rule]裝置圖表，且區段同時使用即時和已登入的資料，我的區段是否會隨著已登入的資料變更而更新？**

是。

 

**區段大小估計是否包含符合區段資格的裝置，此裝置是根據使用裝置圖形選[!UICONTROL Profile Merge Rule]項的連線而提供？**

不會。請參閱「區段產生器」 [!UICONTROL Estimated Real-Time Population] 中「特 [!UICONTROL Estimated Total Population] 徵」 [和「區段人口族群資料」的定義](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html)。

 

**是[!UICONTROL Addressable Audiences]否包含符合區段資格的裝置，此裝置是根據使用裝置圖[!UICONTROL Profile Merge Rule]形選項的連線所提供？**

是。

 

**如果區段使用[!UICONTROL Profile Merge Rule]帶[!UICONTROL No Cross-Device Profile]有且符合區段之裝置的特性僅儲存在跨裝置描述檔中，區段的總人口會是0嗎？**

是。當「描述檔合併規則」設為時，Audience manager不會在區段評估中計算跨裝置描述檔上儲存的特徵 [!UICONTROL No Cross-Device Profile]。

 

## 特徵頻率、裝置圖形和描述檔合併規則 {#trait-freq-device-rules}

**如何使[!DNL Audience Manager]用裝置圖表來計算[!UICONTROL Profile Merge Rule]特徵頻率？**

特徵頻率是由多個裝置上特定特徵的資格數目總和所定義。 為協助您瞭解此問題，請檢視下列使用案例。

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>條件</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">裝置A和裝置B由裝置圖形連結。 </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">您有使用 <span class="wintitle"> 裝置圖形選項的</span> 「描述檔合併規則」。 </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">單一區段（區段1），由單一特徵（特徵1）組成，其中特徵1的頻率為8。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>動作</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> 讀取並合併裝置A和裝置B的裝置設定檔。從這裡，我們看到： </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">裝置A已有3次符合特徵1。 特徵1的頻率為3。 </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">裝置B已5次符合特徵1。 特徵1的頻率為5。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager會總結特徵</span> 1的頻率，並使用8(3 + 5 = 8)來決定區段資格。 裝置A和裝置B符合區段1的資格，因為其頻率為8。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## 報表、裝置圖形和描述檔合併規則 {#reports-device-graphs-rules}

**我可以看到使用裝置圖表的裝置可[!UICONTROL Profile Merge Rule]以到達的裝置數嗎？**

是。報表會傳回層級的 [!UICONTROL Profile Merge Rule] 資料。 報告資料會每日更新。 資料是根據您帳戶中看到的裝置，而非由裝置圖表連結的裝置。 請參 [閱描述檔合併規則的報表量度](profile-link-metrics.md)。

 

**我可以即時看到使用裝置圖表的符合特定&#x200B;*區段*[!UICONTROL Profile Merge Rules]的裝置數量嗎？**

是。即時人口量度會使用裝置圖表連結的所有裝置的描述檔，擷取目前裝置（即時檢視的裝置）的區段資格。

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>條件</b> </p> </td> 
   <td colname="col2"> <p>假設我們有： </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">區段1建立在這些特性與資格邏輯之上：區段1 =特徵A、特徵B和特徵C。 </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3個裝置設定檔：裝置1（目前的裝置）、裝置2（裝置圖表）、裝置3（裝置圖表）。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>動作</b> </p> </td> 
   <td colname="col2"> <p>每個可用特徵都與裝置相關聯： </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">裝置1:特徵A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">裝置2:特徵B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">裝置3:特徵C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>在先前的元素中，區段1的總人口為1。 </p> <p>在此情況下，「描述檔 <span class="wintitle"> 合併規則</span> 」會使用所有裝置及其特性來決定區段資格。 這表示裝置1、2和3符合區段1的資格，但如上所述，即時區段人口中僅包含裝置1。 這是因為： </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">裝置1是目前與Audience Manager <span class="wintitle"> Data Collection Servers</span> (<span class="wintitle"> DCS</span>)即時互動的裝置。 </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">設備2和3通過設備圖形與設備1關聯，但它們與設備1不同時與DCS交互。 </li> 
     </ul> </p> <p>因此，裝置2和3不會納入即時區段人口量度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**我是否可以看到使用裝置圖表的特定區段符[!UICONTROL Profile Merge Rule]合的裝置總數？**

是。總區段人口量度包括已根據裝置圖表的連線符合區段資格的其他裝置。

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>條件</b> </p> </td> 
   <td colname="col2"> <p>假設我們有： </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">區段1建立在這些特性與資格邏輯之上：區段1 =特徵A、特徵B和特徵C。 </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3個裝置設定檔：裝置1（目前的裝置）、裝置2（裝置圖表）、裝置3（裝置圖表）。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>關聯</b> </p> </td> 
   <td colname="col2"> <p>每個可用特徵都與裝置相關聯： </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">裝置1:特徵A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">裝置2:特徵B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">裝置3:特徵C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>鑑於先前的元素，區段1的總人口為三(3)。 </p> <p>在此情況下，「描述檔 <span class="wintitle"> 合併規則</span> 」會使用所有裝置及其特性來決定區段資格。 這表示裝置1、2和3符合區段1的資格，而且這三者皆納入總人口。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**報表、報表和報表中是否包含[!UICONTROL Profile Merge Rule]使用裝置圖表的裝置符合區[!UICONTROL Interactive]段[!UICONTROL Overlap]的資[!UICONTROL Audience Optimization]格？**

否。

>[!MORE_LIKE_THIS]
>
>* [個人資料連結](merge-rules-overview.md)

