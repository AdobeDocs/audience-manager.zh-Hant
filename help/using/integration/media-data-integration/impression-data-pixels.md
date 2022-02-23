---
description: 一種向Audience Manager發送媒體資料的方法使用廣告伺服器宏向Audience Manager發送活動屬性。
seo-description: One approach for sending media data to Audience Manager uses ad server macros to send campaign attributes to Audience Manager.
seo-title: Capturing Campaign Impression Data via Pixel Calls
solution: Audience Manager
title: 透過像素呼叫擷取行銷活動的曝光資料
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Adobe Campaign Integration
exl-id: 04e6f1e5-5075-4221-a310-deb3717458ad
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 20%

---

# 透過像素呼叫擷取行銷活動的曝光資料{#capturing-campaign-impression-data-via-pixel-calls}

一種向Audience Manager發送媒體資料的方法使用廣告伺服器宏向Audience Manager發送活動屬性。

這種方法通常被稱為「對創意進行像素化」。 這些資料點將動態插入 [!DNL Audience Manager] 第三方和伺服器宏的像素代碼，用於根據市場活動的關鍵報告屬性映射和報告所有印象和點擊。 聚合資料提供了市場活動績效的統一視圖，有助於確定自定義轉換路徑，並幫助客戶改進導致轉換的廣告伺服器事件的順序。

## 事件調用語法

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)表示程式碼元素和選項。如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../reference/code-style-elements.md)。

事件呼叫會收集曝光次數和轉換資料，並傳送給 [!DNL Audience Manager][資料收集伺服器](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS])。此程序需仰賴協力廠商廣告伺服器，將呼叫放置在創意素材中，以控制插入程式碼中的內容。協力廠商廣告伺服器 (例如 [!DNL DFA]) 可在廣告每次曝光中置入此程式碼。此外，廣告呼叫不會使用 [!DNL JavaScript] 或採用 frame-busting 技術存取廣告標記以外的發佈者資料。

事件調用由使用以下語法的鍵值對組成：

```
https://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

在key-value對中，value變數是廣告伺服器插入的ID或宏。 當廣告標籤載入時， `%macro%` 替換為所需的相應值。 此呼叫不返迴響應。

## 支援的鍵值對 {#supported-key-value-pairs}

印象事件調用接受形成鍵值對的資料。 下表列出並說明了用於保存這些變數的鍵。 如果要捕獲和分析中的資料，則需要執行其中許多操作 [Audience Optimization報告](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 金鑰 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>廣告伺服器中的數字廣告組ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>您的廣告商的資料源ID或整合代碼。 </p> <p>需要 <span class="wintitle"> Audience Optimization </span> 報告。 </p> <p>選填。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>業務部門的資料源ID或整合代碼。 </p> <p>需要 <span class="wintitle"> Audience Optimization </span> 報告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>快取突破值。 <span class="keyword"> Audience Manager </span> 自動發送大多數瀏覽器和代理都遵守的快取控制標頭。 如果要執行其他快取突破，請在事件調用中包括此參數，然後是隨機字串。 </p> <p> 選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>廣告伺服器中的數字市場活動ID。 </p> <p>需要 <span class="wintitle"> Audience Optimization </span> 報告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>在這種背景下， <code> d_cid </code> 實例化鍵值對，該對允許您將移動設備類型與唯一用戶ID(DPUUID)關聯。 固定ID確定移動設備類型。 值（即用戶ID）可能有所不同。 將鍵值對與 <code> %01 </code>，是非打印控制字元。 此參數接受以下鍵： </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914:標識Android(GAID)設備。 比如說， <code> d_cid = 20914 %01 1234 </code> 用戶1234與Android設備關聯。 </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915:標識iOS(IDFA)設備。 比如說， <code> d_cid = 20915 %01 5678 </code> 用戶5678與iOS設備關聯。 </li> 
    </ul> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>廣告伺服器中的數字創作ID。 </p> <p>需要 <span class="wintitle"> Audience Optimization </span> 報告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>將事件調用標識為印象事件。 </p> <p>必填. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>廣告伺服器的數字放置ID。 </p> <p> 選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>廣告伺服器中的數字站點ID。 </p> <p>需要 <span class="wintitle"> Audience Optimization </span> 報告。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>提供元資料的平台的資料源ID或整合代碼（例如DFA、Atlas、GBM、媒體數學等）。 </p> <p>需要 <span class="wintitle"> Audience Optimization </span> 報告。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a></p> <p><code>gdpr</code> 可以是0（GDPR不適用）或1（GDPR適用）。</p> <p>預設值為 0。</p><p>選填。</p><p>如果 <code>gdpr=1</code>，則 <code>gdpr_consent</code> 參數應包含IAB TC同意參數以成功處理資料。 否則，所有資料都將被刪除。</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p><a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a></p><p> 如果 <code>gdpr=1</code>，則 <code>${gdpr_consent_XXXX}</code> 替換為 <code>gdpr_consent</code> 字串和供應商ID(請參見 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB規範</a>)。</p> <p>預設值為 0。</p><p>選填。</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>請聯繫您的Adobe Audience Manager咨詢或客戶主管，瞭解特定於客戶端域的確切URL。

## 其他功能 —  [!DNL Audience Optimization Reports] {#additional-functionality-aor}

可以使用像素調用為 [Audience Optimization報告](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md)。 請參閱 [元資料檔案的概述和映射](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 如果希望使用像素為報表供電。

>[!MORELIKETHIS]
>
>* [用於Audience Optimization報告的資料和元資料檔案](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

