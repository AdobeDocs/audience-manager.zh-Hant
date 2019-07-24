---
description: 常見描述檔合併規則和裝置圖表問題的解答。
keywords: 組織 ID
seo-description: 常見描述檔合併規則和裝置圖表問題的解答。
seo-title: 描述檔合併規則與裝置圖表常見問題
solution: Audience Manager
title: 描述檔合併規則與裝置圖表常見問題
uuid: ba7986f1-078f-4162-aef3-b5 c8740 ceff4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rules and Device Graph FAQ{#profile-merge-rules-and-device-graph-faq}

常見描述檔合併規則和裝置圖表問題的解答。

<!-- 

profile-merge-faq.xml

 -->

## Device Graph Basics {#device-graph-basics}

**甚麼是裝置圖表？**

裝置圖表是一組ID映射，用來定義匿名裝置群組。它會根據從每台裝置收集到的訊號，將這些裝置與個人或家庭相關聯。這些訊號可協助識別個別或家庭層級的裝置。

<br> 

**甚麼是外部裝置圖形？**

An external device graph is any device graph in [!DNL Audience Manager] that has not been created exclusively from your own cross-device data sources. For example, when you create a [Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md) and choose the [!UICONTROL Co-op Device Graph] or third-party device graph options, you're working with an external device graph. See [Device Options](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

<br> 

**使用外部裝置圖表的常見使用案例[!UICONTROL Profile Merge Rule]為何？**

The main objective of using a device graph in a [!UICONTROL Profile Merge Rule] is to evaluate and qualify multiple devices belonging to a single person or household for a specific segment. 區段本身可能有多個用途，以DSP提供的潛在客源為目標對象，或透過臨場感個人化平台將客戶的現場體驗個人化。See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

<br> 

**Audience Manager是否提供外部裝置圖形的全域支援？**

不會。外部裝置圖形僅適用於美國和加拿大。

<br> 

**[!DNL Audience Manager]更新外部裝置圖表資料的頻率為何？**

每週一次。

<br> 

## Device Graphs and Profile Merge Rules {#device-graph-profile-merge-rules}

**[!DNL Audience Manager]如何使用裝置圖表？**

In [!DNL Audience Manager], device graphs appear as configuration options when you [create a Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md). Through your [!UICONTROL Profile Merge Rules], these device graphs help [!DNL Audience Manager]:

* 合併多個裝置設定檔。這會建立單一超規則集的特性。
* 評估針對區段資格設定的特徵(而非個別評估每個裝置設定檔)。
* 將合格的裝置新增至可用的區段。

<br> 

**我可以[!UICONTROL Profile Merge Rules]建立多少個？**

Currently, you can create a maximum of 3 [!UICONTROL Profile Merge Rules].

<br> 

**在使用裝置圖表時[!DNL Audience Manager]，有多少裝置設定檔會合併和讀取[!UICONTROL Profile Merge Rule]？**

When qualifying a device for a segment using a [!UICONTROL Profile Merge Rule], Audience Manager merges and reads the current device profile and a maximum of 3 additional device profiles linked by your selected device graph option.

<br> 

**使用裝置圖表時，哪些裝置符合區段的資格[!UICONTROL Profile Merge Rule]？**

The devices [!DNL Audience Manager] merges and reads are the same devices that are qualified for a segment.

>[!NOTE]
>
>For external device graphs, [!DNL Audience Manager] stores the mapping between devices at the platform level and selects 3 without evaluating their relationship to the devices seen in your instance of [!DNL Audience Manager].

<br> 

**哪些裝置&#x200B;**可以使用包含裝置圖表的區段[!UICONTROL Profile Merge Rule]符合區段資格？**

To qualify for a segment, devices must have been seen by Audience Manager on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created. 此外，Edge伺服器：

* 將描述檔資料儲存為最多14天。
* 如果裝置設定檔處於非活動狀態超過14天，則加以刪除。注意：此動作只會移除邊緣的資料。其他系統會保留記錄時間較長的時間間隔。See the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).
* Reset the 14-day interval if [!DNL Audience Manager] records any activity for that profile across the entire platform.

See also, [Data Collection Components](../reference/system-components/components-data-collection.md).

<br> 

**哪裡[!DNL Audience Manager]可以傳送使用裝置圖表的[!UICONTROL Profile Merge Rule]符合資格的區段？**

[!DNL Audience Manager] 可在批次檔案中或即時傳送區段至目的地。And, as noted in the FAQ entry above, To qualify for a segment, devices must have been seen by [!DNL Audience Manager] on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created.

<br> 

## Segments, Device Graphs, and Profile Merge Rules {#segments-device-graphs-rules}

**當裝置不再符合使用裝置圖表的區段時，該裝置的[!DNL Audience Manager][!UICONTROL Profile Merge Rule]解除區段方式如何？**

Audience Manager merges up to four devices when evaluating segments with a [!UICONTROL Profile Merge Rule] that uses a device graph. 如果未發出區段訊號，則會從目的地中移除即時檢視的目前裝置和另外三個裝置。例如，在六裝置叢集中，最多可合併、評估和符合區段的部裝置。同樣地，最多可合併、評估和未分段個裝置。

<br> 

**如果目的地可以解除區段裝置，會使用裝置圖表從[!UICONTROL Profile Merge Rules]區段移除裝置嗎？**

是。請參閱上述說明。

<br> 

**如果我建立使用[!UICONTROL Profile Merge Rule]裝置圖表且區段同時使用即時和已到職資料的區段，當已登錄的資料變更時，我的區段將會更新嗎？**

不會。Currently, [!DNL Audience Manager] evaluates segments with a [!UICONTROL Profile Merge Rule] that uses a device graph in real-time only. Updates made to on-boarded traits after the segment has been evaluated will be used to qualify the segment when the device is next seen by our [edge data servers](../reference/system-components/components-edge.md). 這假設裝置描述檔仍在邊緣伺服器中作用中，並已將已登錄的資料提供給這些系統。See also, the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**區段大小預估是否包含根據使用裝置圖表選項之連線所提供[!UICONTROL Profile Merge Rule]之連線的裝置？**

不會。See the definitions for the [!UICONTROL Estimated Real-Time Population] and [!UICONTROL Estimated Total Population] in [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

**[!UICONTROL Addressable Audiences]是否包含根據使用裝置圖表選項之連線所提供[!UICONTROL Profile Merge Rule]之連線的裝置？**

是。

<br> 

**如果區段使用[!UICONTROL Profile Merge Rule]了和[!UICONTROL No Authenticated Profile]符合區段裝置的特徵，則區段的裝置只會對已驗證的描述檔儲存，區段總人口是否為0？**

不會。今天，Audience Manager會將對應至已驗證的設定檔的裝置計算為符合區段資格的裝置。

<br> 

## Trait Frequency, Device Graphs, and Profile Merge Rules {#trait-freq-device-rules}

**[!DNL Audience Manager]如何使用裝置圖表[!UICONTROL Profile Merge Rule]計算特徵頻率？**

特徵頻率是由多個裝置上特定特徵的資格總和所定義。為協助您瞭解，請參閱下列使用案例。

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
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">裝置A和裝置B由裝置圖表連結。 </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">You have a <span class="wintitle"> Profile Merge Rule</span> that uses a device graph option. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">單一區段(區段1)由單一特徵(特徵1)組成，其中特徵的頻率為8。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>動作</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> 會讀取並合併裝置A和裝置B的裝置設定檔。在此，我們會看到下列內容： </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">裝置A的特徵為三次。對特徵的頻率為3。 </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">裝置B符合特徵次的資格。它的特徵為「特徵1」。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> 會計算特徵的頻率，並使用(3+5=8)來決定區段資格。裝置A和裝置B符合區段1，因為其頻率為8。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

## Reports, Device Graphs, and Profile Merge Rules {#reports-device-graphs-rules}

**我可以看到使用裝置圖表時，可[!UICONTROL Profile Merge Rule]觸及的裝置數嗎？**

是。Reports return data at the [!UICONTROL Profile Merge Rule] level. 報表資料每日更新。資料是以您帳戶中所看到的裝置為基礎，而非裝置圖表所連結的裝置。See [Report Metrics for Profile Merge Rules](../features/profile-merge-rules/profile-link-metrics.md).

<br> 

**我可以使用裝置圖表即時查看符合特定&#x200B;**區段的[!UICONTROL Profile Merge Rules]裝置數目嗎？**

是。即時人口度量會使用裝置圖表連結的所有裝置描述檔，擷取目前裝置(即時檢視裝置)的區段資格。

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
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">基於這些特性和資格邏輯的區段1：區段1=特徵A和特徵B和特徵C。 </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">裝置設定檔：裝置(目前裝置)、裝置(裝置圖形)、裝置(裝置圖形)。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>動作</b> </p> </td> 
   <td colname="col2"> <p>每個可用特徵都與裝置相關聯： </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">裝置1：Trait A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">裝置2：特徵B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">裝置3：特徵C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>在先前的元素中，區段的總人口數為1。 </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. 這表示裝置1、和版符合第1節的資格，但如上所述，在即時區段人口中僅包含Device1。這是因為： </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Device 1 is the current device interacting with the Audience Manager <span class="wintitle"> Data Collection Servers</span> (<span class="wintitle"> DCS</span>) in real-time. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">裝置和3會依裝置圖表與裝置相關聯，但並不與DCS同時與DCS互動。 </li> 
     </ul> </p> <p>因此，即時區段人口量度不包含裝置和3。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**可以看到使用裝置圖表的特定區段符合特定區段[!UICONTROL Profile Merge Rule]的裝置總數嗎？**

是。區段人口總計量度包括其他根據裝置圖表的連線而符合區段資格的裝置。

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
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">基於這些特性和資格邏輯的區段1：區段1=特徵A和特徵B和特徵C。 </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">裝置設定檔：裝置(目前裝置)、裝置(裝置圖形)、裝置(裝置圖形)。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associations</b> </p> </td> 
   <td colname="col2"> <p>每個可用特徵都與裝置相關聯： </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">裝置1：Trait A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">裝置2：特徵B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">裝置3：特徵C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>在先前的元素中，區段的總人口數為(3)。 </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. 這表示裝置1、和符合區段的資格，而且全部都包含在總人口中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**使用裝置圖表的裝置是否符合[!UICONTROL Profile Merge Rule][!UICONTROL Interactive]報表、[!UICONTROL Overlap]報告和[!UICONTROL Audience Optimization]報告中包含的裝置圖表？**

無

>[!MORE_贊_ this]
>
>* [個人資料連結](../features/profile-merge-rules/merge-rules-overview.md)

