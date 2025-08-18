---
description: 點按追蹤可記錄協力廠商創意內容的點按型活動，因此可測量整個行銷活動的訪客參與度。
seo-description: Click tracking enables measurement of visitor engagement throughout your campaign, as it records click-based activity for third-party creatives.
seo-title: Capturing Campaign Click Data via Pixel Calls
solution: Audience Manager
title: 透過畫素呼叫擷取行銷活動的點按資料
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Adobe Campaign Integration
exl-id: 41b169bf-3727-4ed7-b74f-fea75244d2cb
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 6%

---

# 透過畫素呼叫擷取行銷活動的點按資料 {#capturing-campaign-click-data-via-pixel-calls}

點按追蹤可記錄協力廠商創意內容的點按型活動，因此可測量整個行銷活動的訪客參與度。 類似於[曝光數集合](/help/using/integration/media-data-integration/impression-data-pixels.md)，事件呼叫已傳送至[!DNL Audience Manager]資料集合伺服器([!DNL DCS])進行處理。 接著，系統會將訪客重新導向至預定網址。

>[!NOTE]
>
>請連絡您的[!DNL Audience Manager]諮詢或帳戶負責人，以取得使用者端網域專屬的確切[!DNL URL]。

## 要求

點選追蹤呼叫需要下列引數：

* `d_event=click`：將事件呼叫識別為點選事件的機碼值組。
* `d_rd=redirect URL`：包含雙重編碼重新導向[!DNL URL]的機碼值組。 如果您使用線上編碼工具，請透過編碼器執行字串，然後再次對結果進行編碼，以便重新導向能夠運作。

此外，呼叫可包含機碼值組，這些機碼值組可用於特徵資格或提供其他報表的資料和中繼資料。

## 要求範例

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 回應

回應會將瀏覽器重新導向至[!DNL URL]引數中指定的`d_rd`。 回應字串可包含下列任何支援巨集所產生的值。

根據上述範例，瀏覽器會重新導向至下列[!DNL URL]：

`https://adobe.com/callback?creative=123`

## 支援的巨集

按一下「事件」可支援下表列出的巨集。 巨集是自我包含程式碼的一個小單位，當廣告標籤載入行銷活動和使用者追蹤時會啟用。 只要這些巨集標示為下列格式，就會隨目的地[!DNL URL]一併傳送： `%macro%`。 有些金鑰沒有巨集，而是接受硬式編碼的ID值。 如果您想要分析[Audience Optimization報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)中的資料，則需要接受硬式編碼值的金鑰。

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 索引鍵 </th> 
   <th colname="col02" class="entry"> 巨集 </th> 
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
   <td colname="col02"> <p>沒有巨集。 </p> <p>接受硬式編碼ID值。 </p> </td> 
   <td colname="col2"> <p>廣告商ID。</p> <p>廣告商資料來源的整合程式碼。 請注意，這與Audience Manager資料來源無關。</p> <p> <span class="wintitle">個Audience Optimization</span>報表的必要專案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>業務單位的數值ID。 </p> <p> <span class="wintitle">個Audience Optimization</span>報表的必要專案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值促銷活動ID。 </p> <p> <span class="wintitle">個Audience Optimization</span>報表的必要專案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值創意ID。 </p> <p>必填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。 </p> <p>通常與<code> d_dpuuid</code>搭配使用，將資料提供者ID連結至使用者ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>資料提供者提供的唯一使用者ID。 </p> <p>通常與<code> d_dpid</code>搭配使用，將使用者ID連結至資料提供者ID。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud</span> ID (ECID)。 如需有關ECID的詳細資訊，請參閱<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie與Experience Cloud ID</a>。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值位置ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>為請求提供服務的DCS叢集的數值區域ID。 如需DCS的詳細資訊，請參閱<a href="../../reference/system-components/components-data-collection.md">資料收集元件</a>。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>用於快取失敗的隨機數。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值網站ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>Audience Manager提取中繼資料之來源的DPID。 </p> <p>必填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>直接在URL中指定訪客的ID，而非依賴Demdex Cookie。 </p> <p>選填。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a> </p><p><code>gdpr</code> 可為0 （GDPR不適用）或1 （GDPR適用）。</p> <p>預設值為 0。</p><p>選填。</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a></p><p> 若<code>gdpr=1</code>，則<code>${gdpr_consent_XXXX}</code>會由<code>gdpr_consent</code>字串和廠商ID取代（請參閱<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB規格</a>）。</p> <p>預設值為 0。</p><p>選填。</p></td> 
  </tr> 
 </tbody> 
</table>

## 巨集範例

此範例示範如何傳遞創意、廣告群組和放置巨集。 假設每個引數的值都會傳入點選追蹤呼叫的非重新導向部分。

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

根據上述範例，瀏覽器會重新導向至下列[!DNL URL]：

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## 其他功能 — [!UICONTROL Audience Optimization Reports]

您可以使用畫素呼叫來支援[Audience Optimization報表](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)。 如果您想要使用畫素來支援報表，請參閱[中繼資料檔案的概述與對應](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)。


>[!MORELIKETHIS]
>
>* [Audience Optimization報表的資料和中繼資料檔案](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)
