---
description: 列出並說明您可傳遞至資料收集伺服器(DCS)的語法和支援的屬性（或機碼值組）。 此資訊可協助您設定DCS請求的格式，並了解此系統傳回的參數。
seo-description: Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the Data Collection Servers (DCS). This information can help you format your DCS requests and understand the parameters returned by this system.
seo-title: Supported Attributes for DCS API Calls
solution: Audience Manager
title: DCS API 呼叫的支援屬性。
keywords: d呼叫者， d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
exl-id: 1bdd7dcd-9411-4b0a-a236-059eb5faf00d
source-git-commit: e10211057a87622340fd2c61737c7c7a45c0e99c
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 4%

---

# 支援的屬性 [!DNL DCS] [!DNL API] 呼叫 {#supported-attributes-for-dcs-api-calls}

列出並說明您可傳遞至的語法和支援的屬性（或機碼值組） [!UICONTROL Data Collection Servers] ([!DNL DCS])。 此資訊可協助您將 [!DNL DCS] 請求並了解此系統傳回的參數。

## 屬性前置詞 {#attribute-prefixes}

此 [!DNL DCS] 需仰賴索引鍵值配對中新增至索引鍵的特定前置詞，才能分類您要傳入的資料類型。

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 密鑰前置詞 </th> 
   <th colname="col2" class="entry"> 保留 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>客戶定義的屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>HTTP標題資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>私人、客戶定義的屬性。 </p> <p> 當金鑰具有 <code> p_</code> 前置詞。 私人資料用於特徵評估，但不會將其記錄或儲存在我們的系統中。 例如，假設您有一個特徵定義為 <code> customers = p_age&lt;25</code> 你傳入 <code> p_age=23</code> 在事件呼叫中。 基於這些條件，符合年齡型資格條件的使用者符合特徵資格，但機碼 — 值組會在 <span class="keyword"> Audience Manager</span> 接收要求且未記錄。 </p> </td>
  </tr> 
 </tbody> 
</table>

## [!DNL d_] 屬性 {#d-attributes}

除非您想要 [!DNL DCS]. 如果您想要 [!DNL DCS] 傳回回應，然後 `d_rtbd=json` 為必要項目。

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 屬性 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_caller</code> </p> </td> 
   <td colname="col2"> <p>用於識別呼叫者 <span class="wintitle"> DCS</span> API。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>指定您要使用 <span class="wintitle"> DCS</span> 回應作為回呼函式的函式參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>包含一或多組資料提供者ID(<code> DPID</code>)和資料提供者使用者ID(<code> DPUUID</code>)指派給 <span class="keyword"> Audience Manager</span>. 如果您使用 <code> DPID</code>s和 <code> DPUUID</code>s，用非打印字元分隔每對 <code> %01</code>. 例如: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> 取代 <code> d_dpid</code> 和 <code> d_dpuuid</code>，已過時但仍支援。 請參閱 <a href="../../../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>在單一機碼值組中包含整合程式碼和相關聯的唯一使用者ID。 </p> <p><code> d_cid_ic</code> 取代 <code> d_dpid</code> 和 <code> d_dpuuid</code>，已過時但仍支援。 請參閱 <a href="../../../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>為遵守兒童保護法規，停用第三方Cookie的使用。 此參數由AdobeAdobe Experience Platform Identity Service動態設定，且取決於 <code> idSyncDisable3rdPartySyncing</code> 設定。 請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/coppa.html" format="https" scope="external"> Adobe Experience Platform Identity服務的COPPA支援</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>選填。在客戶要求時啟用。 請聯絡您的Adobe Audience Manager顧問或客戶服務。 </p> <p>指出特徵和區段應在 <code> JSON</code> 回應。 </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> 傳回 <a href="../../../reference/ids-in-aam.md"> 舊式區段ID</a> ，以取得Advertising Cloud的說明。 </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> 傳回區段的區段ID。 </p> </li>
     </ul> </p> <p>範例回應可能如下所示： </p> <p>
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      &nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpid</code> </p> </td> 
   <td colname="col2"> <p>不再提倡。請參閱 <code> d_cid</code> 和 <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>不再提倡。請參閱 <code> d_cid</code> 和 <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>在 <code> JSON</code> 回應。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> 是保留屬性，用於Adobe Analytics與Audience Manager之間的整合。 </p> <p>我們建議不要建立使用保留屬性的特徵。 Adobe可隨時更改保留屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>指出 <code> JSON</code> 版本以用於回應。 通常，您應將此設定為 <code> d_jsonv=1</code>. 設定 <code> d_jsonv=0</code> 停用ID同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>指定Experience CloudID集，並由 <span class="keyword"> Experience Cloud</span> ID服務。 如需ECID的詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie與Experience CloudIdentity Service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>名稱空間ID。 指出使用的JavaScript容器。 使用者 <span class="wintitle"> DIL</span> 為進行id同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>允許Audience Manager區分行動請求與案頭請求。 支援的值包括: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>不再提倡。<code> d_rs</code> 是保留屬性，用於 <span class="keyword"> Adobe Analytics</span> 和 <span class="keyword"> Audience Manager</span>. </p> <p>我們建議不要建立使用保留屬性的特徵。 Adobe可隨時更改保留屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>如果您想要 <code> JSON</code> 來自 <span class="wintitle"> DCS</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">如果您忽略此項目， <span class="wintitle"> DCS</span> 傳回標題中的像素。 </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">若包含此項目， <span class="wintitle"> DCS</span> 傳回a <code> JSON</code> 回應內文中的物件。 請參閱下列範例。 您的回應可能會更複雜。 </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> 代表 <span class="term"> 分數ID</span>. 這是特徵或區段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>傳遞特徵評估的資料來源。 系統只會評估此資料來源的特徵。 </p> <p>例如，假設您有： </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>特徵T1</b> 包含： </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">特徵規則："<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">資料來源(<a href="../../../reference/ids-in-aam.md"> DPID</a>):1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID整合程式碼：ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>特徵T2</b> 包含： </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">特徵規則："<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">資料來源(DPID):2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID整合程式碼：ic2 </li> 
     </ul> </p> <p>在範例呼叫中， <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>，只會傳回特徵T1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>目的與 <code> d_tdpid</code> 參數。 但在此情況下，會使用整合程式碼來傳遞資料來源。 </p> <p>保留上述特徵，請考量範例呼叫： </p> <p>針對 <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>，只會傳回特徵T2。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>不重複使用者ID。 無法從Cookie取得此值時，可識別訪客。 </p> </td> 
  </tr>
 </tbody>
</table>

## h_屬性

這些標題包含HTTP呼叫中資料和回應的要求等資訊。

| 屬性 | 說明 |
| --- | --- | 
| `h_host` | 這會設為用戶端的特定資料收集主機名稱。 其顯示為 `host name .demdex.net`. 請參閱[瞭解向 Demdex 網域進行的呼叫](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=en)。 |
| `h_user-agent` | 設為 `User-Agent` 標題值。 |
| `h_accept-language` | 設為  `Accept-Language`  標題值。 |
| `h_referer` | 設為 `Referer` 標題值。 |
| `h_referrer` | 設為 `Referrer` 標題值。 |
| `h_date` | 設為 `Date` 標題值。 |