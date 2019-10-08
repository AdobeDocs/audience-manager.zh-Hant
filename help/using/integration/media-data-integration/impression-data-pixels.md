---
description: 一種傳送媒體資料至Audience manager的方法，是使用廣告伺服器巨集將促銷活動屬性傳送至Audience Manager。
seo-description: 一種傳送媒體資料至Audience manager的方法，是使用廣告伺服器巨集將促銷活動屬性傳送至Audience Manager。
seo-title: 透過像素呼叫擷取促銷活動的曝光資料
solution: Audience Manager
title: 透過像素呼叫擷取促銷活動的曝光資料
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
translation-type: tm+mt
source-git-commit: f072c5328ac75bf3376f80e86418d25d4f10df23

---


# 透過像素呼叫擷取促銷活動的曝光資料{#capturing-campaign-impression-data-via-pixel-calls}

一種傳送媒體資料至Audience manager的方法，是使用廣告伺服器巨集將促銷活動屬性傳送至Audience Manager。

這種方法通常稱為「對創意素材進行像素化」。 這些資料點會由協力廠商廣告伺服器巨集動態插入像素程式碼中，這些巨集用於根據促銷活動的主要報告屬性來對應和報告所有印象和點按。 [!DNL Audience Manager] 匯整的資料可提供促銷活動績效的統一檢視，有助於識別自訂的轉換路徑，並協助客戶改善導致轉換的廣告伺服器事件順序。

## 事件呼叫語法

>[!NOTE]
>
>文字樣式 (`monospaced text`、*斜體*、括號 `[ ]` `( )` 等)表示程式碼元素和選項。如需詳細資訊，請參閱[程式碼與文字元素的樣式慣例](../../reference/code-style-elements.md)。

事件呼叫會收集曝光次數和轉換資料，並傳送給 [!DNL Audience Manager][資料收集伺服器](/help/using/reference/system-components/components-data-collection.md) ([!UICONTROL DCS])。此程序需仰賴協力廠商廣告伺服器，將呼叫放置在創意素材中，以控制插入程式碼中的內容。協力廠商廣告伺服器 (例如 [!DNL DFA]) 可在廣告每次曝光中置入此程式碼。此外，廣告呼叫不會使用 [!DNL JavaScript] 或採用 frame-busting 技術存取廣告標記以外的發佈者資料。

事件呼叫由使用下列語法的鍵值配對組成：

```
http://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

在索引鍵值對中，值變數是廣告伺服器所插入的ID或巨集。 當廣告標籤載入時，會 `%macro%` 以必要的對應值來取代。 此呼叫不會傳回回應。

## 支援的索引鍵值配對 {#supported-key-value-pairs}

曝光事件呼叫接受形成鍵值對的資料。 下表列出並說明用來存放這些變數的鍵。 若您想要擷取並分析「對象最佳化報表」中的資料，則需要其中 [許多項](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。

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
   <td colname="col2"> <p>來自廣告伺服器的數值廣告群組ID。 </p> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>您廣告商的資料來源ID或整合代碼。 </p> <p>「對象最佳 <span class="wintitle"> 化」報表 </span> 必要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>您業務單位的資料來源ID或整合代碼。 </p> <p>「對象最佳 <span class="wintitle"> 化」報表 </span> 必要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>快取破壞值。 <span class="keyword"> Audience manager會 </span> 自動傳送大部分瀏覽器和Proxy都採用的快取控制標題。 如果您想要執行其他快取破壞，請將此參數加入事件呼叫中，然後加入隨機字串。 </p> <p> 選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值促銷活動ID。 </p> <p>「對象最佳 <span class="wintitle"> 化」報表 </span> 必要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>在此內容中， <code> d_cid </code> 會執行個體化金鑰值對，讓您將行動裝置類型與唯一使用者ID(DPUUID)產生關聯。 固定ID會決定行動裝置類型。 值（即用戶ID）可能有所不同。 將鍵值對與 <code> %01分 </code>隔，這是非列印控制字元。 此參數接受下列鍵： </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">二零九一四年：識別Android(GAID)裝置。 例如， <code> d_cid = 20914 %01 1234 </code> 表示使用者1234與Android裝置相關聯。 </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915年：識別iOS(IDFA)裝置。 例如， <code> d_cid = 20915 %01 5678 </code> 表示使用者5678與iOS裝置相關聯。 </li> 
    </ul> <p>選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值創意ID。 </p> <p>「對象最佳 <span class="wintitle"> 化」報表 </span> 必要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>將事件呼叫識別為印象事件。 </p> <p>必填. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值位置ID。 </p> <p> 選填。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>來自廣告伺服器的數值網站ID。 </p> <p>「對象最佳 <span class="wintitle"> 化」報表 </span> 必要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>提供中繼資料之平台的資料來源ID或整合程式碼（例如DFA、Atlas、GBM、Media Math等）。 </p> <p>「對象最佳 <span class="wintitle"> 化」報表 </span> 必要。 </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code><i>gdpr</i></code>  </td> 
   <td colname="col2"> <p><a href="../../overview/aam-gdpr/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a></p> <p><code>gdpr可以是</code> 0（GDPR不適用）或1（GDPR適用）。</p> <p>預設值為 0。</p><p>選填。</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_counnence</code> </td> 
   <td colname="col2"> <p><a href="../../overview/aam-gdpr/aam-iab-plugin.md">與適用 IAB TCF 的 Audience Manager 增效模組相關。</a></p><p> 「若 <code>gdpr=1</code>，則 <code>%gdpr_consent%</code>」取代為「<code>gdpr_consent</code>」字串 (請參閱 <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB 規格</a>)。</p> <p>預設值為 0。</p><p>選填。</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>請連絡您的Adobe Audience manager諮詢或客戶主管，以取得用戶端網域的確切URL。

>[!MORE_LIKE_THIS]
>
>* [受眾最佳化報告的資料和中繼資料檔案](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

