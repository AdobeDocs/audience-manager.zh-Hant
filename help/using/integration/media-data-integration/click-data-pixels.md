---
description: 點擊跟蹤功能可以衡量整個活動中的訪問者參與程度，因為它記錄了第三方創意的點擊式活動。
seo-description: Click tracking enables measurement of visitor engagement throughout your campaign, as it records click-based activity for third-party creatives.
seo-title: Capturing Campaign Click Data via Pixel Calls
solution: Audience Manager
title: 透過像素呼叫擷取行銷活動的點按資料
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Adobe Campaign Integration
exl-id: 41b169bf-3727-4ed7-b74f-fea75244d2cb
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 9%

---

# 透過像素呼叫擷取行銷活動的點按資料 {#capturing-campaign-click-data-via-pixel-calls}

點擊跟蹤功能可以衡量整個活動中的訪問者參與程度，因為它記錄了第三方創意的點擊式活動。 類似於 [印刷品](/help/using/integration/media-data-integration/impression-data-pixels.md)，將事件呼叫發送到 [!DNL Audience Manager] 資料收集伺服器([!DNL DCS])進行處理。 然後將訪問者重定向到預期的網址。

>[!NOTE]
>
>請聯繫您 [!DNL Audience Manager] 咨詢或客戶線索 [!DNL URL] 特定於客戶端域。

## 要求

按一下跟蹤調用需要以下參數：

* `d_event=click`:將事件調用標識為按一下事件的鍵值對。
* `d_rd=redirect URL`:包含雙編碼重定向的鍵值對 [!DNL URL]。 如果使用聯機編碼工具，請通過編碼器運行字串，然後重新編碼結果，以便重定向工作。

此外，該調用可包含鍵值對，這些鍵值對可用於特徵鑑定或為其他報告提供資料和元資料。

## 請求示例

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## 回應

響應將瀏覽器重定向到 [!DNL URL] 在 `d_rd` 的下界。 響應字串可以包括由下面列出的任何受支援的宏生成的值。

根據上例，瀏覽器將重定向到以下 [!DNL URL]:

`https://adobe.com/callback?creative=123`

## 支援的宏

按一下事件支援下表中列出的宏。 宏是自包含代碼的小單元，當廣告標籤載入用於市場活動和用戶跟蹤時激活。 宏將與目標一起傳遞 [!DNL URL]，只要它們標籤為以下格式： `%macro%`。 某些鍵沒有宏，而接受硬編碼ID值。 如果要分析中的資料，則需要接受硬編碼值的鍵 [Audience Optimization報告](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。

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
   <td colname="col2"> <p>廣告伺服器中的數字廣告組ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>沒有宏。 </p> <p>接受硬編碼ID值。 </p> </td> 
   <td colname="col2"> <p>廣告主 ID.</p> <p>廣告商資料源的整合代碼。 請注意，這與Audience Manager資料源無關。</p> <p> 需要 <span class="wintitle"> Audience Optimization</span> 報告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>業務單位的數字ID。 </p> <p> 需要 <span class="wintitle"> Audience Optimization</span> 報告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>廣告伺服器中的數字市場活動ID。 </p> <p> 需要 <span class="wintitle"> Audience Optimization</span> 報告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>廣告伺服器中的數字創作ID。 </p> <p>必填. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>資料提供程式ID。 </p> <p>常用於 <code> d_dpuuid</code> 將資料提供程式ID連結到用戶ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>資料提供程式提供的唯一用戶ID。 </p> <p>常用於 <code> d_dpid</code> 將用戶ID連結到資料提供程式ID。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"></span> Experience Cloud ID (ECID). 有關ECID的詳細資訊，請參見 <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Experience CloudID</a>。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>廣告伺服器的數字放置ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>為請求提供服務的DCS群集的數字區域ID。 有關DCS的詳細資訊，請參見 <a href="../../reference/system-components/components-data-collection.md"> 資料收集元件</a>。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>用於快取突破的隨機數。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>廣告伺服器中的數字站點ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>源的DPID,Audience Manager從中提取元資料。 </p> <p>必填. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>直接在URL中指定訪問者的ID，而不是依賴Demdex cookie。 </p> <p>選填。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a> </p><p><code>gdpr</code> 可以是0（GDPR不適用）或1（GDPR適用）。</p> <p>預設值為 0。</p><p>選填。</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a></p><p> 如果 <code>gdpr=1</code>，則 <code>${gdpr_consent_XXXX}</code> 替換為 <code>gdpr_consent</code> 字串和供應商ID(請參見 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB規範</a>)。</p> <p>預設值為 0。</p><p>選填。</p></td> 
  </tr> 
 </tbody> 
</table>

## 宏示例

此示例演示傳遞創意宏、adgroup宏和放置宏。 它假定在點擊跟蹤呼叫的非重定向部分傳遞每個參數的值。

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

根據上例，瀏覽器將重定向到以下 [!DNL URL]:

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## 其他功能 —  [!UICONTROL Audience Optimization Reports]

可以使用像素調用為 [Audience Optimization報告](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)。 請參閱 [元資料檔案的概述和映射](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 如果希望使用像素為報表供電。


>[!MORELIKETHIS]
>
>* [用於Audience Optimization報告的資料和元資料檔案](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

