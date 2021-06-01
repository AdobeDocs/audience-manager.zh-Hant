---
description: 點擊追蹤可讓您測量整個促銷活動中的訪客參與度，因為它會記錄第三方創意素材的點擊式活動。
seo-description: 點擊追蹤可讓您測量整個促銷活動中的訪客參與度，因為它會記錄第三方創意素材的點擊式活動。
seo-title: 透過像素呼叫擷取行銷活動的點按資料
solution: Audience Manager
title: 透過像素呼叫擷取行銷活動的點按資料
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Adobe Campaign整合
exl-id: 41b169bf-3727-4ed7-b74f-fea75244d2cb
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 11%

---

# 透過像素呼叫擷取行銷活動的點按資料 {#capturing-campaign-click-data-via-pixel-calls}

點擊追蹤可讓您測量整個促銷活動中的訪客參與度，因為它會記錄第三方創意素材的點擊式活動。 與[曝光數收集](/help/using/integration/media-data-integration/impression-data-pixels.md)類似，事件呼叫會傳送至[!DNL Audience Manager]資料收集伺服器([!DNL DCS])以進行處理。 接著，系統會將訪客重新導向至預期的網址。

>[!NOTE]
>
>請連絡您的[!DNL Audience Manager]諮詢或客戶主管，以取得用戶端網域特有的確切[!DNL URL]。

## 要求

點擊追蹤呼叫需要下列參數：

* `d_event=click`:索引鍵值組，可將事件呼叫識別為點按事件。
* `d_rd=redirect URL`:包含雙重編碼重新導向的機碼值組 [!DNL URL]。如果您使用線上編碼工具，請透過編碼器執行字串，然後重新編碼結果，以便重新導向運作。

此外，呼叫可包含索引鍵值配對，可用於特徵資格或提供其他報表的資料和中繼資料。

## 請求範例

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 回應

回應會將瀏覽器重新導向至`d_rd`參數中指定的[!DNL URL]。 回應字串可包含下列任何支援的巨集所產生的值。

根據上述範例，瀏覽器會重新導向至下列[!DNL URL]:

`https://adobe.com/callback?creative=123`

## 支援的巨集

按一下事件支援下表中列出的宏。 巨集是自我包含的小單位，當廣告標籤載入以進行促銷活動和使用者追蹤時，就會啟用。 只要宏標籤為以下格式，則宏將與目標[!DNL URL]一起傳遞：`%macro%`。 有些索引鍵沒有巨集，而是接受硬式編碼ID值。 如果要分析[Audience Optimization報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)中的資料，則需要接受硬式編碼值的索引鍵。

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
   <td colname="col1"> <p> <code> d_adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_adgroup%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值廣告群組ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>沒有宏。 </p> <p>接受硬式編碼ID值。 </p> </td> 
   <td colname="col2"> <p>廣告主 ID.</p> <p>廣告商資料來源的整合代碼。 請注意，這與Audience Manager資料來源無關。</p> <p> <span class="wintitle">Audience Optimization</span>報表必要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>業務單位的數值ID。 </p> <p> <span class="wintitle">Audience Optimization</span>報表必要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值促銷活動ID。 </p> <p> <span class="wintitle">Audience Optimization</span>報表必要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值創作ID。 </p> <p>必填. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>資料提供者ID。 </p> <p>通常與<code> d_dpuuid</code>搭配使用，將資料提供者ID連結至使用者ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>資料提供者提供的不重複使用者ID。 </p> <p>通常與<code> d_dpid</code>搭配使用，將使用者ID連結至資料提供者ID。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"></span> Experience Cloud ID (ECID). 如需ECID的詳細資訊，請參閱<a href="https://docs.adobe.com/content/help/zh-Hant/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Experience CloudID</a>。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值位置ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>為請求提供服務之DCS叢集的數值區域ID。 如需DCS的詳細資訊，請參閱<a href="../../reference/system-components/components-data-collection.md">資料收集元件</a>。 </p> <p>選填。 </p> </td> 
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
   <td colname="col2"> <p>來源的DPID,Audience Manager從中提取中繼資料。 </p> <p>必填. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>直接在URL中指定訪客的ID，而非依賴Demdex Cookie。 </p> <p>選填。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a> </p><p><code>gdpr</code> 可為0（GDPR不適用）或1（GDPR適用）。</p> <p>預設值為 0。</p><p>選填。</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a></p><p> 如果<code>gdpr=1</code>，則<code>${gdpr_consent_XXXX}</code>被<code>gdpr_consent</code>字串和供應商ID取代（請參閱<a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB規範</a>）。</p> <p>預設值為 0。</p><p>選填。</p></td> 
  </tr> 
 </tbody> 
</table>

## 巨集範例

此範例示範如何傳遞創作、廣告群組和版位巨集。 這會假設每個參數的值會傳入點擊追蹤呼叫的非重新導向部分。

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

根據上述範例，瀏覽器會重新導向至下列[!DNL URL]:

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## 其他功能 — [!UICONTROL Audience Optimization Reports]

您可以使用像素呼叫來為[Audience Optimization報表](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)加電。 如果您想要使用像素來為報表提供動力，請參閱[中繼資料檔案的概述和對應](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 。


>[!MORELIKETHIS]
>
>* [Audience Optimization報表的資料和中繼資料檔案](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

