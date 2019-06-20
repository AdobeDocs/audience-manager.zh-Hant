---
description: 將媒體資料傳送至Audience Manager的一種方法是使用廣告伺服器巨集，將促銷活動屬性傳送至Audience Manager。
seo-description: 將媒體資料傳送至Audience Manager的一種方法是使用廣告伺服器巨集，將促銷活動屬性傳送至Audience Manager。
seo-title: 透過像素呼叫擷取促銷活動的曝光資料
solution: Audience Manager
title: 透過像素呼叫擷取促銷活動的曝光資料
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c
translation-type: tm+mt
source-git-commit: c79c2311c3ea76ce2450dc1b84a7a22b60a6edb7

---


# 透過像素呼叫擷取促銷活動的曝光資料{#capturing-campaign-impression-data-via-pixel-calls}

將媒體資料傳送至Audience Manager的一種方法是使用廣告伺服器巨集，將促銷活動屬性傳送至Audience Manager。

此方法通常稱為「pixiles the creative」。Those data points are dynamically inserted into the [!DNL Audience Manager] pixel code by the third-party ad server macros, which are used to map and report all impressions and clicks based on the key reporting attributes of the campaign. 匯總資料可提供宣傳績效的統一檢視、有助於識別自訂轉換路徑，並協助客戶改善導致轉換的廣告伺服器事件序列。

## 事件呼叫語法

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)表示程式碼元素和選項。如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../reference/code-style-elements.md)。

事件呼叫會收集曝光次數和轉換資料，並傳送給 [!DNL Audience Manager][資料收集伺服器](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS])。此程序需仰賴協力廠商廣告伺服器，將呼叫放置在創意素材中，以控制插入程式碼中的內容。協力廠商廣告伺服器 (例如 [!DNL DFA]) 可在廣告每次曝光中置入此程式碼。此外，廣告呼叫不會使用 [!DNL JavaScript] 或採用 frame-busting 技術存取廣告標記以外的發佈者資料。

事件呼叫包含使用下列語法的索引鍵值配對：

<pre>
http://clientname.demdex.net/event?d_event=imp&amp;d_src=datasource_id&amp;d_site=siteID&amp;
d_creative=<i>creative_id</i>&amp;d_adgroup=<i>adgroup_id</i>&amp;d_placement=<i>placement_id</i>
&amp;d_campaign=<i>campaign_id</i>[&amp;d_cid=(GAID|IDFA)%01 DPUUID]&amp;d_bust=cache buster value
</pre>

在索引鍵值配對中，值變數是廣告伺服器插入的ID或巨集。When the ad tag loads, that `%macro%` gets replaced with the required, corresponding values. 此呼叫不會傳回回應。

## Supported Key-Value Pairs {#supported-key-value-pairs}

曝光事件呼叫可接受形成為索引鍵值配對的資料。下表列出並說明用來放置這些變數的索引鍵。Many of these are required if you want to capture and analyze data in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 金鑰 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_ adgroup </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值廣告群組ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ adsc </code> </td> 
   <td colname="col2"> <p>廣告商的資料來源ID或整合代碼。 </p> <p><span class="wintitle"> 「對象最佳化 </span> 」報表所需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ bu </code> </td> 
   <td colname="col2"> <p>您的業務單位的資料來源ID或整合代碼。 </p> <p><span class="wintitle"> 「對象最佳化 </span> 」報表所需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bust </code> </p> </td> 
   <td colname="col2"> <p>快取緩衝值。<span class="keyword"> Audience Manager </span> 會自動傳送由大部分瀏覽器和proxy接受的快取控制標題。如果您想要執行額外的快取，請在事件呼叫中加入此參數，然後在隨機字串中加入此參數。 </p> <p> 選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ campaign </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值促銷活動ID。 </p> <p><span class="wintitle"> 「對象最佳化 </span> 」報表所需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In this context, <code> d_cid </code> instantiates a key-value pair that lets you associate a mobile device type to a unique user ID (DPUUID). 固定ID會決定行動裝置類型。值(即使用者ID)會有所不同。Separate the key-value pair with <code> %01 </code>, which is a non-printing control character. 此參數接受下列按鍵： </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914：識別Android(GAID)裝置。For example, <code> d_cid = 20914 %01 1234 </code> says that user 1234 is associated with an Android device. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915：識別iOS(IDFA)裝置。For example, <code> d_cid = 20915 %01 5678 </code> says that user 5678 is associated with an iOS device. </li> 
    </ul> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ creative </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值創意ID。 </p> <p><span class="wintitle"> 「對象最佳化 </span> 」報表所需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ event= imp </code> </td> 
   <td colname="col2"> <p>將事件呼叫識別為曝光事件。 </p> <p>必填. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ place </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值位置ID。 </p> <p> 選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ site </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值網站ID。 </p> <p><span class="wintitle"> 「對象最佳化 </span> 」報表所需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_ src </code> </td> 
   <td colname="col2"> <p>提供中繼資料之平台的資料來源ID或整合程式碼(例如DFA、Atlas、GBM、Media Math等)。 </p> <p><span class="wintitle"> 「對象最佳化 </span> 」報表所需。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code><i>gdpr</i></code>  </td> 
   <td colname="col2"> <p><a href="../../overview/aam-gdpr/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a></p> <p><code>gdpr</code> 可能為(GDPR不適用)或1(GDPR適用)。</p> <p>預設值為 0。</p><p>選填。</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_ contract</code> </td> 
   <td colname="col2"> <p><a href="../../overview/aam-gdpr/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a></p><p> 「若 <code>gdpr=1</code>，則 <code>%gdpr_consent%</code>」取代為「<code>gdpr_consent</code>」字串 (請參閱 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB 規格</a>)。</p> <p>預設值為 0。</p><p>選填。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>請連絡您的Adobe Audience Manager諮詢或帳戶，以取得客戶網域專屬的確切URL。

>[!MORE_贊_ this]
>
>* [觀眾最佳化報表的資料和中繼資料檔案](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

