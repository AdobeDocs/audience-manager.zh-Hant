---
description: 列出並說明您可傳入資料收集伺服器(DCS)的語法和支援的屬性（或金鑰值配對）。 此資訊可協助您格式化DCS要求，並瞭解此系統傳回的參數。
seo-description: 列出並說明您可傳入資料收集伺服器(DCS)的語法和支援的屬性（或金鑰值配對）。 此資訊可協助您格式化DCS要求，並瞭解此系統傳回的參數。
seo-title: DCS API 呼叫的支援屬性。
solution: Audience Manager
title: DCS API 呼叫的支援屬性。
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 5%

---


# 呼叫的支援屬 [!DNL DCS][!DNL API] 性 {#supported-attributes-for-dcs-api-calls}

列出並說明您可傳入()的語法和支援的屬性(或金鑰值 [!UICONTROL Data Collection Servers] 配對[!DNL DCS])。 這些資訊可協助您設定請求 [!DNL DCS] 的格式，並瞭解此系統傳回的參數。

## 屬性前置詞 {#attribute-prefixes}

依 [!DNL DCS] 賴於鍵值對中新增至鍵的特定字首，以分類您傳入的資料類型。

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 密鑰前置詞 </th> 
   <th colname="col2" class="entry"> 保留對象 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>客戶定義的屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager屬性</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>HTTP標題資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>私人、客戶定義的屬性。 </p> <p> 當金鑰有首碼時，DCS會接受您自己的私人 <code> p_</code> 資料。 私人資料用於特徵評估，但不會記錄或儲存在我們的系統中。 例如，假設您有個特徵定義為， <code> customers = p_age&lt;25</code> 而且您在事件呼 <code> p_age=23</code> 叫中傳入。 基於這些條件，符合年齡資格條件的使用者符合特徵的資格，但是Audience Manager <span class="keyword"></span> 收到請求後，索引鍵值配對會被捨棄，而且不會記錄。 </p> </td>
  </tr> 
 </tbody> 
</table>

## [!DNL d_] 屬性 {#d-attributes}

所有這些都是選用的，除非您想要回應 [!DNL DCS]。 如果您想要傳 [!DNL DCS] 回回應，則為必 `d_rtbd=json` 要項目。

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
   <td colname="col2"> <p>用於識別對 <span class="wintitle"> DCS</span> API進行呼叫的呼叫者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>指定您要使用 <span class="wintitle"> DCS回應來執行的JavaScript函式</span> ，作為回呼函式的函式參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>包含一對或多對資料提供者ID(<code> DPID</code>)和Audience Manager指派的資料提供者<code> DPUUID</code>使用者ID( <span class="keyword"> )</span>。 如果您使用多對 <code> DPID</code>s和 <code> DPUUID</code>s，請將每對分隔為非列印字元 <code> %01</code>。 例如: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> 取代 <code> d_dpid</code> 和 <code> d_dpuuid</code>，這些已過時但仍受支援。 請參閱 <a href="../../../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>在單一金鑰值配對中包含整合程式碼和相關聯的唯一使用者ID。 </p> <p><code> d_cid_ic</code> 取代 <code> d_dpid</code> 和 <code> d_dpuuid</code>，這些已過時但仍受支援。 請參閱 <a href="../../../reference/cid.md">CID 取代 DPID 及 DPUUID</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>停用第三方Cookie的使用，以符合兒童保護法規。 此參數由Adobe Experience Platform Identity Service動態設定，並視設定而 <code> idSyncDisable3rdPartySyncing</code> 定。 請參 <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/coppa.html" format="https" scope="external"> 閱Adobe Experience Platform Identity Service中的COPPA支援</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>選填。在客戶要求時啟用。 請連絡您的Adobe Audience Manager顧問或客戶服務。 </p> <p>指出應在回應內傳回特徵和區 <code> JSON</code> 段。 </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> 傳回 <a href="../../../reference/ids-in-aam.md"> 區段的舊有</a> ID。 </p> </li>
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
   <td colname="col2"> <p>不再提倡。請參閱 <code> d_cid</code> 和 <code> d_cid_ic</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>不再提倡。請參閱 <code> d_cid</code> 和 <code> d_cid_ic</code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>在回應中傳回URL目標 <code> JSON</code> 資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> 是保留屬性，用於Adobe Analytics與Audience Manager的整合。 </p> <p>我們建議不要建立使用保留屬性的特徵。 Adobe得隨時變更保留屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>指出要 <code> JSON</code> 在回應中使用的版本。 通常，您應將此設定為 <code> d_jsonv=1</code>。 設定 <code> d_jsonv=0</code> 會停用ID同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>指定Experience Cloud ID服務所設定及使 <span class="keyword"> 用的Experience Cloud</span> ID。 如需ECID的詳細資訊，請參 <a href="https://docs.adobe.com/content/help/zh-Hant/id-service/using/intro/cookies.html" format="https" scope="external"> 閱Cookie和Experience Cloud Identity Service</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>命名空間ID。 指出使用的JavaScript容器。 DIL用 <span class="wintitle"> 於</span> ID同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>可讓Audience Manager將行動裝置要求與案頭要求區分開來。 支援的值包括: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>不再提倡。<code> d_rs</code> 是保留屬性，用於 <span class="keyword"> Adobe Analytics和</span> Audience Manager之間的舊版整合 <span class="keyword"></span>。 </p> <p>我們建議不要建立使用保留屬性的特徵。 Adobe得隨時變更保留屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>如果您想要DCS的 <code> JSON</code> 回應，則 <span class="wintitle"> 為必要</span>。 </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">如果省略此項， <span class="wintitle"> DCS</span> 會傳回標題中的像素。 </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">如果包含此項， <span class="wintitle"> DCS</span> 會傳 <code> JSON</code> 回回應內文中的物件。 請參閱以下範例。 您的回應可能會更複雜。 </li> 
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
   <td colname="col2"> <p><code> SID</code> 代表分 <span class="term"> 數ID</span>。 這是特徵或區段的唯一ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>傳遞特徵評估的資料來源。 僅評估此資料來源的特徵。 </p> <p>例如，假設您有： </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>特徵T1</b> : </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">特徵規則： "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">資料來源(<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID整合程式碼： ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>特徵T2</b> ，包含： </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">特徵規則： "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">資料來源(DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID整合程式碼： ic2 </li> 
     </ul> </p> <p>在範例呼叫中， <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>只會傳回特徵T1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>其用途與上述參 <code> d_tdpid</code> 數相同。 不過，在此情況下，會使用整合程式碼來傳遞資料來源。 </p> <p>保留上述特徵，請考慮範例呼叫： </p> <p>對 <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>於，僅傳回特徵T2。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>唯一使用者ID。 識別無法從Cookie使用此值的訪客。 </p> </td> 
  </tr>
 </tbody>
</table>