---
description: 設定檔合併規則與裝置圖表的常見問題解答。
keywords: Organization ID
seo-description: 設定檔合併規則與裝置圖表的常見問題解答。
seo-title: 設定檔合併規則與裝置圖表常見問題集
solution: Audience Manager
title: 設定檔合併規則與裝置圖表常見問題集
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 86%

---


# 設定檔合併規則與裝置圖表常見問題集{#profile-merge-rules-and-device-graph-faq}

設定檔合併規則與裝置圖表的常見問題解答。

<!-- profile-merge-faq.xml -->

## 裝置圖表基本須知 {#device-graph-basics}

**什麼是裝置圖表？**

裝置圖表是一組 ID 對應，用於定義匿名裝置群組。它會根據從每部裝置收集到的訊號中之共同元素，將這些裝置與個人或家庭建立關聯。這些訊號有助於識別個人或家庭層級的裝置。

 

**什麼是外部裝置圖表？**

外部裝置圖表是指 [!DNL Audience Manager] 中並非專門從您自己的跨裝置資料來源建立的任何裝置圖表。例如，當您建立[設定檔合併規則](../features/profile-merge-rules/merge-rules-start.md)，並選擇 [!UICONTROL Co-op Device Graph] 或第三方裝置圖表選項時，就是使用外部裝置圖表。請參閱[裝置選項](../features/profile-merge-rules/merge-rule-definitions.md#device-options)。

 

**在[!UICONTROL Profile Merge Rule]中使用外部裝置圖表有哪些常見的使用案例？**

在 [!UICONTROL Profile Merge Rule] 中使用裝置圖表的主要目的，是針對特定區段評估，以及為屬於單一個人或家庭的多部裝置授與資格。例如，區段本身可能有多種用途，例如以 DSP 所提供的廣告對潛在客戶進行目標定位，或透過站上個人化平台將客戶的站上體驗個人化。請參閱[外部裝置圖表使用案例](../features/profile-merge-rules/external-graph-use-cases.md)

 

**Audience Manager 是否對外部裝置圖表提供全球支援？**

否。外部裝置圖表僅開放美國和加拿大使用。

 

**[!DNL Audience Manager]多久更新一次外部裝置圖表資料？**

每週一次。

 

## 裝置圖表和設定檔合併規則 {#device-graph-profile-merge-rules}

**[!DNL Audience Manager]如何使用裝置圖表？**

在 [!DNL Audience Manager] 中[建立設定檔合併規則](../features/profile-merge-rules/merge-rules-start.md)時，裝置圖表會顯示為設定選項。透過您的 [!UICONTROL Profile Merge Rules]，這些裝置圖表可協助 [!DNL Audience Manager]：

* 將多個裝置設定檔合併在一起。這會建立一個特徵超集。
* 評估區段資格的特徵超集 (而不是分別評估各個裝置設定檔)。
* 將符合資格的裝置新增至可用區段。

 

**我可以建立多少[!UICONTROL Profile Merge Rules]？**

目前最多可以建立 4 個 [!UICONTROL Profile Merge Rules]。第四個設定檔合併規則 ([!UICONTROL All Cross-Device Profiles]) 僅適用於購買 [!UICONTROL People-Based Destinations] 附加元件的客戶。

 

**在[!UICONTROL Profile Merge Rule]中使用裝置圖表時，[!DNL Audience Manager]會合併和讀取幾個裝置設定檔？**

使用 [!UICONTROL Profile Merge Rule] 為裝置授與區段的資格時，Audience Manager 會合併並讀取目前的裝置設定檔，以及最多 99 個由您所選的裝置圖表選項連結的其他裝置設定檔。

 

**在[!UICONTROL Profile Merge Rule]中使用裝置圖表時，哪些裝置符合區段的資格？**

[!DNL Audience Manager] 合併和讀取的裝置，與符合區段資格的裝置相同。

 

**[!DNL Audience Manager]可在哪裡傳送使用裝置圖表的[!UICONTROL Profile Merge Rule]已授與資格的區段？**

[!DNL Audience Manager] 能以批次檔案或即時方式將區段傳送至目的地。

 

## 區段、裝置圖表和設定檔合併規則 {#segments-device-graphs-rules}

**透過使用裝置圖表的[!UICONTROL Profile Merge Rule]，若判斷裝置不再符合區段的資格，[!DNL Audience Manager]會如何取消裝置的區段？**

透過使用裝置圖表的 [!UICONTROL Profile Merge Rule] 評估區段時，Audience Manager 可合併最多 100 部裝置。如果系統發出取消細分訊號，那麼目前的裝置和最多 99 部其他裝置將會從目的地的區段中移除。如需取消細分的詳細資訊，請參閱[設定檔合併規則和裝置取消細分程序](../features/profile-merge-rules/merge-rule-unsegment.md)。

 

**如果目的地可以取消裝置的區段，使用裝置圖表的[!UICONTROL Profile Merge Rules]是否會將裝置從區段中移除？**

是。請參閱上述說明。

 

**如果透過使用裝置圖表的[!UICONTROL Profile Merge Rule]建立區段，且區段同時使用即時和已上線的資料，我的區段是否會隨著已上線的資料變更而更新？**

是。

 

**區段大小估計是否包含根據使用裝置圖表選項的[!UICONTROL Profile Merge Rule]提供的連線符合區段資格的裝置？**

不會。請參閱[區段產生器中的特徵和區段母體資料](https://docs.adobe.com/content/help/zh-Hant/audience-manager/user-guide/features/segments/segment-builder-data.translate.html)中的 [!UICONTROL Estimated Real-Time Population] 和 [!UICONTROL Estimated Total Population] 定義。

 

**[!UICONTROL Addressable Audiences]是否包含根據使用裝置圖表選項的[!UICONTROL Profile Merge Rule]提供的連線符合區段資格的裝置？**

是。

 

**如果區段搭配[!UICONTROL No Cross-Device Profile]使用[!UICONTROL Profile Merge Rule]，且讓裝置符合區段資格的特徵只儲存在跨裝置設定檔中，那麼區段的總母體會是 0 嗎？**

是。當設定檔合併規則設為 [!UICONTROL No Cross-Device Profile]，Audience Manager 就不會在進行區段評估時計算跨裝置設定檔中儲存的特徵數。

 

## 特徵頻率、裝置圖表和設定檔合併規則 {#trait-freq-device-rules}

**[!DNL Audience Manager]如何透過使用裝置圖表的[!UICONTROL Profile Merge Rule]來計算特徵頻率？**

特徵頻率取決於跨多部裝置的特定特徵資格數總和。為協助您瞭解，請參閱下列使用案例。

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
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">裝置 A 和裝置 B 由裝置圖表連結。 </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">您有一個使用裝置圖表選項的<span class="wintitle">設定檔合併規則</span>。 </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">一個區段 (區段 1) 包含一個特徵 (特徵 1)，其中特徵 1 的頻率為 8。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>動作</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> 讀取並合併裝置 A 和裝置 B 的裝置設定檔。從這裡可以看出以下幾點： </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">裝置 A 已符合特徵 1 資格三次。特徵 1 的頻率為 3。 </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">裝置 B 已符合特徵 1 資格五次。特徵 1 的頻率為 5。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> 會加總特徵 1 的頻率，並使用 8 (3 + 5 = 8) 來決定區段資格。裝置 A 和裝置 B 符合區段 1 的資格，因為其頻率為 8。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## 報表、裝置圖表和設定檔合併規則 {#reports-device-graphs-rules}

**我是否能透過使用裝置圖表的[!UICONTROL Profile Merge Rule]看到可觸及的裝置數？**

是。報表會傳回 [!UICONTROL Profile Merge Rule] 層級的資料。報表資料會每天更新。資料是根據在您帳戶中看到的裝置，而非裝置圖表所連結的裝置。請參閱[設定檔合併規則的報表量度](../features/profile-merge-rules/profile-link-metrics.md)。

 

**我是否能透過使用裝置圖表的[!UICONTROL Profile Merge Rules]*即時*看到符合特定區段資格的裝置數？**

是。即時母體量度會使用裝置圖表連結的所有裝置之設定檔，擷取目前裝置 (即時發現的裝置) 的區段資格。

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
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">區段 1 (以這些特徵與資格邏輯建置)：區段 1 = 特徵 A、特徵 B 和特徵 C。 </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 個裝置設定檔：裝置 1 (目前裝置)、裝置 2 (裝置圖表)、裝置 3 (裝置圖表)。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>動作</b> </p> </td> 
   <td colname="col2"> <p>每個可用特徵都與一部裝置相關聯： </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">裝置 1：特徵 A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">裝置 2：特徵 B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">裝置 3：特徵 C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>根據先前的元素，區段 1 的總母體為 1。 </p> <p>在此情況下，<span class="wintitle">設定檔合併規則</span>會使用所有裝置及其特徵來決定區段資格。這表示裝置 1、2 和 3 符合區段 1 的資格，但如上所述，即時區段母體中只會包含裝置 1。原因如下： </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">裝置 1 是目前與 Audience Manager <span class="wintitle">資料收集伺服器</span> (<span class="wintitle"> DCS</span>) 即時互動的裝置。 </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">裝置 2 和 3 透過裝置圖表與裝置 1 建立關聯，但它們與 DCS 互動的時間和裝置 1 不同。 </li> 
     </ul> </p> <p>因此，裝置 2 和 3 不會納入即時區段母體量度中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**我是否能透過使用裝置圖表的[!UICONTROL Profile Merge Rule]看到符合特定區段資格的總裝置數？**

是。總區段母體量度包括已根據裝置圖表的連線符合區段資格的其他裝置。

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
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">區段 1 (以這些特徵與資格邏輯建置)：區段 1 = 特徵 A、特徵 B 和特徵 C。 </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 個裝置設定檔：裝置 1 (目前裝置)、裝置 2 (裝置圖表)、裝置 3 (裝置圖表)。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>關聯</b> </p> </td> 
   <td colname="col2"> <p>每個可用特徵都與一部裝置相關聯： </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">裝置 1：特徵 A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">裝置 2：特徵 B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">裝置 3：特徵 C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>根據先前的元素，區段 1 的總母體為三 (3)。 </p> <p>在此情況下，<span class="wintitle">設定檔合併規則</span>會使用所有裝置及其特徵來決定區段資格。這表示裝置 1、2 和 3 符合區段 1 的資格，而且這三者皆納入總母體中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**[!UICONTROL Interactive]報表、[!UICONTROL Overlap]報表和[!UICONTROL Audience Optimization]報表中，是否包含透過使用裝置圖表的[!UICONTROL Profile Merge Rule]符合區段資格的裝置？**

否。

**為何2020年3月16日之後，區段匯出至Adobe Campaign的區段人口為零？**

在2019年底，我們推出了一系列的描述檔合併規則增強功能，以改善使用跨裝置ID產生的批次檔案的精確度。 從2020年3月16日星期一開始，您的Audience Manager例項將嚴格執行這些增強功能。 因此，使用跨裝置ID映射至目的地的區段，會停止在某些「描述檔合併規則」設定中產生匯出。

若要使用跨裝置ID（例如Adobe Campaign）確保Audience Manager實例與目標之間的正確整合，請確定您符合下列需求：

1. 檢閱對應至Adobe Campaign Declared ID目的地的區段所使用的描述檔合併規則。 「描述檔合併規則」必須使 [!UICONTROL Last Authenticated Profile] 用選項，因此所有已驗證的描述檔都可以包含在匯出中。 如果您的描述檔合併規則使用不同的選項，請將其切換為 [!UICONTROL Last Authenticated Profile]。
2. 在「描述檔合併規則」設定中，選取「Adobe Campaign Declared ID」資料來源。

>[!NOTE]
>
> 我們已針對面臨此情況的客戶，將「描述檔合併規則」限制提高1，以便您可以為對應至Adobe Campaign Declared ID目的地的區段建立專用的「描述檔合併規則」，而不會變更其他使用案例的「描述檔合併規則」。

>[!MORELIKETHIS]
>
>* [設定檔連結](../features/profile-merge-rules/profile-link-use-case.md)

