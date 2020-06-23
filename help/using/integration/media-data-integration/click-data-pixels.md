---
description: 'null'
seo-description: 'null'
seo-title: 透過像素呼叫擷取行銷活動的點按資料
solution: Audience Manager
title: 透過像素呼叫擷取行銷活動的點按資料
uuid: 7c3797f7-9674-493d-972b-38be0584fede
translation-type: tm+mt
source-git-commit: 620730ab1596d4777a768de4453b73538671279d
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 12%

---


# 透過像素呼叫擷取行銷活動的點按資料 {#capturing-campaign-click-data-via-pixel-calls}

點按追蹤可讓您測量整個促銷活動中的訪客參與度，因為它會記錄第三方創意人員的點按式活動。 與印象 [收集類似](/help/using/integration/media-data-integration/impression-data-pixels.md)，事件呼叫會傳送至資料 [!DNL Audience Manager] 收集伺服器([!DNL DCS])以進行處理。 接著，訪客會重新導向至預期的網址。

>[!NOTE]
>
>請連絡您 [!DNL Audience Manager] 的諮詢或客戶主管，以取得 [!DNL URL] 客戶網域的確切資訊。

## 要求

點按追蹤呼叫需要下列參數：

* `d_event=click`: 將事件呼叫識別為點按事件的金鑰值配對。
* `d_rd=redirect URL`: 包含雙重編碼重新導向的索引鍵值對 [!DNL URL]。 如果您使用線上編碼工具，請在編碼器中執行字串，然後重新編碼結果，以便重新導向正常運作。

此外，呼叫可包含可用於特徵限定或為其他報表提供資料和中繼資料的鍵值配對。

## 請求範例

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 回應

回應會將瀏覽器重新導向 [!DNL URL] 至參數中指定的 `d_rd` 位置。 回應字串可包含下列任何支援的巨集所產生的值。

根據上述範例，瀏覽器會重新導向至下列範例 [!DNL URL]:

`https://adobe.com/callback?creative=123`

## 支援的巨集

按一下事件支援下表中列出的宏。 巨集是自含代碼的一小部分，當廣告標籤載入促銷活動和使用者追蹤時會啟動。 宏將隨目標一起傳遞，只 [!DNL URL]要它們標有以下格式： `%macro%`. 某些鍵沒有宏，而接受硬編碼ID值。 如果您要分析「對象最佳化報表」中的資料，則需要接受硬式編碼值 [的金鑰](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。

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
   <td colname="col2"> <p>廣告主 ID.</p> <p>廣告商資料來源的整合代碼。 請注意，這與Audience Manager資料來源無關。</p> <p> 「對象最佳 <span class="wintitle"> 化」報表</span> 。 </p> </td> 
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
   <td colname="col2"> <p> <span class="keyword"></span> Experience Cloud ID (ECID). For more information about the ECID, see <a href="https://docs.adobe.com/content/help/zh-Hant/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> <p>選填。 </p> </td> 
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
   <td colname="col2"> <p>Audience Manager提取中繼資料的來源DPID。 </p> <p>必填. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>直接在URL中指定訪客的ID，而非依賴Demdex Cookie。 </p> <p>選填。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a> </p><p><code>gdpr</code> 可以是0（GDPR不適用）或1（GDPR適用）。</p> <p>預設值為 0。</p><p>選填。</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a></p><p> 如 <code>gdpr=1</code>果，則 <code>${gdpr_consent_XXXX}</code> 由字串和廠商ID <code>gdpr_consent</code> 取代(請參閱 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB規格</a>)。</p> <p>預設值為 0。</p><p>選填。</p></td> 
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
d_rd%3Dhttp%253A%252F%252Fadobe.com%252Fcallback%253Fcreative%253D%2525d_creative%2525%2526campaign%253D%2525d_campaign%2525%2526adgroup%253D%2525%0Ad_adgroup%2525%2526d_placement%253D%2525placement%2525%2526src%253D%2525d_src%2525
```

## 回應

根據上述範例，瀏覽器會重新導向至下列範例 [!DNL URL]:

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## 其他功能- [!UICONTROL Audience Optimization Reports]

您可以使用像素呼叫來強化「對象最 [佳化報表」](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)。 如果 [您想使用像素來為報表加電](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) ，請參閱中繼資料檔案的概述和對應。


>[!MORELIKETHIS]
>
>* [受眾最佳化報告的資料和中繼資料檔案](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

