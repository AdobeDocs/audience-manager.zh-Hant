---
description: 列出並說明可傳入「資料收集伺服器」(DCS)的語法和支援的屬性（或索引鍵值配對）。 此資訊可協助您格式化DCS要求，並瞭解此系統傳回的引數。
seo-description: Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the Data Collection Servers (DCS). This information can help you format your DCS requests and understand the parameters returned by this system.
seo-title: Supported Attributes for DCS API Calls
solution: Audience Manager
title: DCS API呼叫的支援屬性
keywords: d_caller， d_cb， d_cid， d_cid_ic， d_coppa， d_cts=1， d_cts=2， d_tdpid， d_dst=1， d_dst_filter， d_mid， d_ptfm， d_nsid， d_rs， d_rtbd=json， d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
exl-id: 1bdd7dcd-9411-4b0a-a236-059eb5faf00d
source-git-commit: e10211057a87622340fd2c61737c7c7a45c0e99c
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 2%

---

# [!DNL DCS] [!DNL API]呼叫的支援屬性 {#supported-attributes-for-dcs-api-calls}

列出並描述您可以傳遞至[!UICONTROL Data Collection Servers] ([!DNL DCS])的語法和支援的屬性（或機碼值組）。 此資訊可協助您格式化[!DNL DCS]要求，並瞭解此系統傳回的引數。

## 屬性首碼 {#attribute-prefixes}

[!DNL DCS]依賴新增到索引鍵值配對中的索引鍵的特定首碼，以分類您傳入的資料型別。

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 金鑰首碼 </th> 
   <th colname="col2" class="entry"> 保留給 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>客戶定義的屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span>屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>HTTP標頭資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>私人、客戶定義的屬性。 </p> <p> 當金鑰有<code> p_</code>首碼時，DCS會接受您自己的私人資料。 私人資料會用於特徵評估，但不會記錄或儲存在我們的系統中。 例如，假設您有一個定義為<code> customers = p_age&lt;25</code>的特徵，且您在事件呼叫中傳入<code> p_age=23</code>。 基於這些條件，符合年齡型資格條件的使用者符合特徵資格，但在<span class="keyword">Audience Manager</span>收到請求且未記錄後，機碼值組會被捨棄。 </p> </td>
  </tr> 
 </tbody> 
</table>

## [!DNL d_]屬性 {#d-attributes}

除非您想要來自[!DNL DCS]的回應，否則所有這些都是選擇性的。 若您希望[!DNL DCS]傳回回應，則需要`d_rtbd=json`。

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
   <td colname="col2"> <p>用於識別呼叫<span class="wintitle"> DCS</span> API的呼叫者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>指定要使用<span class="wintitle"> DCS</span>回應作為回呼函式的函式引數執行的JavaScript函式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>包含由<span class="keyword">Audience Manager</span>指派的一或多組資料提供者ID (<code> DPID</code>)和資料提供者ID (<code> DPUUID</code>)。 如果您使用多對<code> DPID</code>和<code> DPUUID</code>，請以非列印字元<code> %01</code>分隔每對。 例如： <code><i>DPID</i>%01<i>DPUUUID</i></code>。 </p> <p><code> d_cid</code> 取代<code> d_dpid</code>和<code> d_dpuuid</code>，這兩個專案已棄用，但仍受支援。 請參閱<a href="../../../reference/cid.md"> CID取代DPID與DPUUID</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>在單一索引鍵值配對中包含整合代碼和關聯的唯一使用者ID。 </p> <p><code> d_cid_ic</code> 取代<code> d_dpid</code>和<code> d_dpuuid</code>，這兩個專案已棄用，但仍受支援。 請參閱<a href="../../../reference/cid.md"> CID取代DPID與DPUUID</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>停用第三方Cookie的使用以遵守兒童保護法規。 此引數由AdobeAdobe Experience Platform Identity Service動態設定，且取決於<code> idSyncDisable3rdPartySyncing</code>設定。 請參閱Adobe Experience Platform Identity服務</a>中的<a href="https://experienceleague.adobe.com/docs/id-service/using/reference/coppa.html?lang=zh-Hant" format="https" scope="external"> COPPA支援。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>可選。已根據客戶要求啟用。 請聯絡您的Adobe Audience Manager顧問或客戶服務。 </p> <p>指出應在<code> JSON</code>回應中傳回特徵和區段。 </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> 傳回區段的<a href="../../../reference/ids-in-aam.md">舊式區段ID</a>。 </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> 傳回區段的區段ID。 </p> </li>
     </ul> </p> <p>範例回應可能如下所示： </p> <p>
     <code class="syntax javascript">
      &lbrace;
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      &nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      &rbrace;
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpid</code> </p> </td> 
   <td colname="col2"> <p>不再提倡。請參閱<code> d_cid</code>和<code> d_cid_ic</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>不再提倡。請參閱<code> d_cid</code>和<code> d_cid_ic</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>在<code> JSON</code>回應中傳回URL目的地資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> 是保留的屬性，用於Adobe Analytics與Audience Manager之間的整合。 </p> <p>我們建議不要建立使用保留屬性的特徵。 Adobe可隨時變更保留屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>表示要在回應中使用的<code> JSON</code>版本。 通常您應該將此專案設定為<code> d_jsonv=1</code>。 設定<code> d_jsonv=0</code>會停用ID同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>指定<span class="keyword">Experience Cloud</span> ID服務所設定及使用的Experience CloudID。 如需有關ECID的詳細資訊，請參閱<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=zh-Hant" format="https" scope="external"> Cookie與Experience Cloud識別服務</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>名稱空間ID。 指出使用的JavaScript容器。 由<span class="wintitle">DIL</span>使用以進行ID同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>允許Audience Manager將行動請求與案頭請求區分開來。 支援的值包括: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>不再提倡。<code> d_rs</code>是保留的屬性，用於<span class="keyword"> Adobe Analytics</span>與<span class="keyword">Audience Manager</span>之間的舊版整合。 </p> <p>我們建議不要建立使用保留屬性的特徵。 Adobe可隨時變更保留屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>如果您想要來自<span class="wintitle"> DCS</span>的<code> JSON</code>回應，則此為必要專案。 </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">如果省略這個專案，<span class="wintitle"> DCS</span>會在標頭中傳回畫素。 </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">如果您包含此專案，<span class="wintitle"> DCS</span>會在回應內文中傳回<code> JSON</code>物件。 請參閱下列範例。 您的回應可能比較複雜。 </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      &lbrace;
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      &rbrace;
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> 代表<span class="term">分數識別碼</span>。 這是特徵或區段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>傳遞資料來源以進行特徵評估。 只會評估來自此資料來源的特徵。 </p> <p>例如，假設您有： </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>特徵T1</b>包含： </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">特徵規則： "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">資料Source (<a href="../../../reference/ids-in-aam.md"> DPID</a>)： 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID整合代碼：ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>特徵T2</b>包含： </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">特徵規則： "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">資料Source (DPID)：2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID整合代碼：ic2 </li> 
     </ul> </p> <p>在範例呼叫<code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>中，只傳回特徵T1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>用途與上述<code> d_tdpid</code>引數相同。 不過，在此情況下，資料來源會使用整合程式碼傳遞。 </p> <p>若要保留上述特徵，請考量範例呼叫： </p> <p>針對<code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>，僅傳回特徵T2。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>不重複使用者識別碼。 無法從Cookie取得此值時識別訪客。 </p> </td> 
  </tr>
 </tbody>
</table>

## h_屬性

這些標頭包含HTTP呼叫中資料請求和回應之類的資訊。

| 屬性 | 說明 |
| --- | --- | 
| `h_host` | 這會設定為使用者端的特定資料收集主機名稱。 它顯示為`host name .demdex.net`。 請參閱[瞭解向 Demdex 網域進行的呼叫](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=zh-Hant)。 |
| `h_user-agent` | 設定為`User-Agent`標頭值。 |
| `h_accept-language` | 設定為`Accept-Language`標頭值。 |
| `h_referer` | 設定為`Referer`標頭值。 |
| `h_referrer` | 設定為`Referrer`標頭值。 |
| `h_date` | 設定為`Date`標頭值。 |