---
description: 'null'
seo-description: 'null'
seo-title: 透過像素呼叫擷取促銷活動點擊資料
solution: Audience Manager
title: 透過像素呼叫擷取促銷活動點擊資料
uuid: 7c3797f7-9674-493d-972b-38be0584feed
translation-type: tm+mt
source-git-commit: c79c2311c3ea76ce2450dc1b84a7a22b60a6edb7

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

點擊追蹤可讓您測量促銷活動中的訪客參與，因為它記錄第三方創意人士的點按活動。Similar to impressions collection, an event call is sent to the Audience Manager data collection servers ([!UICONTROL DCS]) for processing. 然後將訪客重新導向至預定的網頁位址。

## 要求

按一下追蹤呼叫需要下列參數：

* `d_event=click`：識別事件呼叫作為點按事件的索引鍵值配對。
* `d_rd=redirect URL`：包含編碼重新導向 [!DNL URL]的索引鍵值配對。

此外，呼叫可以包含可用於特徵資格的索引鍵值配對，也可以提供其他報表的資料和中繼資料。

## 請求範例

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 回應

The response redirects the browser to the [!DNL URL] specified in the `d_rd` parameter. 回應字串可包含下列任何受支援巨集所產生的值。

Based on the above example, the browser is redirected to the following [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=123`]

## 支援的Macros

按一下事件可支援下表所列的巨集。巨集是一個小型的自助代碼，可在廣告標記載入為促銷活動和使用者追蹤時啓動。The macros will be passed along with the destination [!DNL URL], as long as they are marked with the following format: `%macro%`. 有些按鍵沒有巨集，而是接受硬式編碼ID值。Keys that accept hard coded values are required if you want to analyze data in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 金鑰 </th> 
   <th colname="col02" class="entry"> 巨集 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ adgroup%d</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值廣告群組ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsc</code> </p> </td> 
   <td colname="col02"> <p>無巨集。 </p> <p>接受硬式編碼ID值。 </p> </td> 
   <td colname="col2"> <p> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 廣告商的資料來源</a> ID或整合代碼。 </p> <p> <span class="wintitle"> 「對象最佳化</span> 」報表所需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ bu%</code> </p> </td> 
   <td colname="col2"> <p>業務單位的數值ID。 </p> <p> <span class="wintitle"> 「對象最佳化</span> 」報表所需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ campaign%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值促銷活動ID。 </p> <p> <span class="wintitle"> 「對象最佳化</span> 」報表所需。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ creative%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值創意ID。 </p> <p>必填. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ id%</code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。 </p> <p>Often used with <code> d_dpuuid</code> to link a data provider ID to a user ID. </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ dpuuid%d</code> </p> </td> 
   <td colname="col2"> <p>資料提供者提供的唯一使用者ID。 </p> <p>Often used with <code> d_dpid</code> to link a user ID to a data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID (ECID). </span>For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ place</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ placement%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值位置ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_地區%d</code> </p> </td> 
   <td colname="col2"> <p>服務之DCS叢集的數值區域ID。For more information about the DCS, see <a href="../../reference/system-components/components-data-collection.md"> Data Collection Components</a>. </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_ rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_ rand%</code> </p> </td> 
   <td colname="col2"> <p>用於快取的隨機數字。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ site%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值網站ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ src%</code> </p> </td> 
   <td colname="col2"> <p>Audience Manager提取中繼資料的來源DPID。 </p> <p>必填. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_ uuid%d</code> </p> </td> 
   <td colname="col2"> <p>直接在URL中指定訪客的ID，而不是依賴Demdex Cookie。 </p> <p>選填。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_ apply%</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/aam-gdpr/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a> </p><p><code>gdpr</code> 可能為(GDPR不適用)或1(GDPR適用)。</p> <p>預設值為 0。</p><p>選填。</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_ contract</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_ conseption%</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/aam-gdpr/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a></p><p> 「若 <code>gdpr=1</code>，則 <code>%gdpr_consent%</code>」取代為「<code>gdpr_consent</code>」字串 (請參閱 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB 規格</a>)。</p> <p>預設值為 0。</p><p>選填。</p></td> 
  </tr> 
 </tbody> 
</table>

## Macros範例

此範例示範傳遞創意、群組和位置巨集。假設每個參數的值會傳入點擊追蹤呼叫的非重導部分。

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> 位置=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## 請求

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25%26campaign%3D%25d_campaign%25%26adgroup%3D%25
d_adgroup%25%26d_placement%3D%25placement%25%26src%3D%25d_src%25
```

## 回應

Based on the above example, the browser is redirected to the following [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORE_贊_ this]
>
>* [觀眾最佳化報表的資料和中繼資料檔案](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

