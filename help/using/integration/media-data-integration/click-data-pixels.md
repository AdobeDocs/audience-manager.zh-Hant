---
description: 'null'
seo-description: 'null'
seo-title: 透過像素呼叫擷取促銷活動點按資料
solution: Audience Manager
title: 透過像素呼叫擷取促銷活動點按資料
uuid: 7c3797f7-9674-493d-972b-38be0584fede
translation-type: tm+mt
source-git-commit: b1e438a77a472c192117a2c1ddcf63f4eb25d07d

---


# Capturing Campaign Click Data via Pixel Calls {#capturing-campaign-click-data-via-pixel-calls}

點按追蹤可讓您測量整個促銷活動中的訪客參與度，因為它會記錄第三方創意人員的點按式活動。 與印象收集類似，事件呼叫會傳送至Audience manager資料收集伺服器([!UICONTROL DCS])以進行處理。 接著，訪客會重新導向至預期的網址。

## 要求

點按追蹤呼叫需要下列參數：

* `d_event=click`:將事件呼叫識別為點按事件的金鑰值配對。
* `d_rd=redirect URL`:包含編碼重新導向的金鑰值對 [!DNL URL]。

此外，呼叫可包含可用於特徵限定或為其他報表提供資料和中繼資料的鍵值配對。

## 請求範例

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 回應

回應會將瀏覽器重新導向 [!DNL URL] 至參數中指定的 `d_rd` 位置。 回應字串可包含下列任何支援的巨集所產生的值。

根據上述範例，瀏覽器會重新導向至下列範例 [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=123`]

## 支援的巨集

按一下事件支援下表中列出的宏。 巨集是自含代碼的一小部分，當廣告標籤載入促銷活動和使用者追蹤時會啟動。 宏將隨目標一起傳遞，只 [!DNL URL]要它們標有以下格式： `%macro%`。 某些鍵沒有宏，而接受硬編碼ID值。 如果您要分析「對象最佳化報表」中的資料，則需要接受硬式編碼值 [的金鑰](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 金鑰 </th> 
   <th colname="col02" class="entry"> 宏 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_adgroup%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值廣告群組ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>無宏。 </p> <p>接受硬式編碼ID值。 </p> </td> 
   <td colname="col2"> <p>廣告主 ID.</p> <p>廣告商資料來源的整合代碼。 請注意，這與Audience manager資料來源無關。</p> <p> 「對象最佳 <span class="wintitle"> 化」報表</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>業務單位的數值ID。 </p> <p> 「對象最佳 <span class="wintitle"> 化」報表</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值促銷活動ID。 </p> <p> 「對象最佳 <span class="wintitle"> 化」報表</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值創意ID。 </p> <p>必填. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。 </p> <p>通常用於 <code> d_dpuuid</code> 將資料提供者ID連結至使用者ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>資料提供者提供的唯一使用者ID。 </p> <p>通常用於 <code> d_dpid</code> 將使用者ID連結至資料提供者ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud ID (ECID). </span>For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值位置ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>為請求提供服務的DCS叢集的數值區域ID。 如需DCS的詳細資訊，請參閱資 <a href="../../reference/system-components/components-data-collection.md"> 料收集元件</a>。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>用於快取破壞的隨機數。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值網站ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>Audience manager提取中繼資料的來源DPID。 </p> <p>必填. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>直接在URL中指定訪客的ID，而非依賴Demdex Cookie。 </p> <p>選填。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_applies%</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a> </p><p><code>gdpr</code> 可以是0（GDPR不適用）或1（GDPR適用）。</p> <p>預設值為 0。</p><p>選填。</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>%gdpr_consent%</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a></p><p> 「若 <code>gdpr=1</code>，則 <code>%gdpr_consent%</code>」取代為「<code>gdpr_consent</code>」字串 (請參閱 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">IAB 規格</a>)。</p> <p>預設值為 0。</p><p>選填。</p></td> 
  </tr> 
 </tbody> 
</table>

## 宏示例

此範例示範如何傳遞創意、adgroup和位置巨集。 它會假設每個參數的值會傳遞至點按追蹤呼叫的非重新導向部分。

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placement=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## 請求

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25%26campaign%3D%25d_campaign%25%26adgroup%3D%25
d_adgroup%25%26d_placement%3D%25placement%25%26src%3D%25d_src%25
```

## 回應

根據上述範例，瀏覽器會重新導向至下列範例 [!DNL URL]:

[!DNL `https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`]

>[!MORELIKETHIS]
>
>* [受眾最佳化報告的資料和中繼資料檔案](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

