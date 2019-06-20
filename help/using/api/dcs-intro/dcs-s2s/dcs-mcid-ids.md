---
description: ID服務客戶應參閱本節，以瞭解如何讀取訪客Cookie以進行DCS API呼叫所需的訪客Cookie。
seo-description: ID服務客戶應參閱本節，以瞭解如何讀取訪客Cookie以進行DCS API呼叫所需的訪客Cookie。
seo-title: 透過Experience Cloud ID服務取得使用者ID和地區
solution: Audience Manager
title: 透過Experience Cloud ID服務取得使用者ID和地區
uuid: 80de6cf2-5d9e-4ef8-a0 f2-d53 b5 d574 c89
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions Through the Experience Cloud ID Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make [!UICONTROL DCS] API calls.

## Get the User ID from the ID Service Cookie {#get-user-ids-from-service-cookie}

[Experience Cloud ID服務會](https://marketing.adobe.com/resources/help/en_US/mcvid/) 指派訪客和地區ID給來到您網站的使用者。These IDs identify users across all the solutions in the [!DNL Experience Cloud] and they are required if you want to make [!UICONTROL DCS] calls.

* The [!UICONTROL user ID] is required to identify and associate data with a particular visitor.
* The [!UICONTROL region ID] is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. 請參閱 [DCS 地區 ID、位置與主機名稱](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

ID服務客戶可以從ID服務Cookie擷取此資訊，或呼叫函數。下表說明您必須完成的工作或步驟，才能開始使用。

*斜體的程式碼* 代表變數預留位置。

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 任務 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1.Check your <span class="keyword"> Experience Cloud</span> status</b> </p> </td> 
   <td colname="col2"> <p>You need a <span class="keyword"> Experience Cloud</span> account to use the ID service. If you have a <span class="keyword"> Experience Cloud</span> account, great! </p> <p> If you're not part of the <span class="keyword"> Experience Cloud</span>, then sign up. 我們希望擁有您，而且隨時都能找到更多空間。For instructions on how to set up an account, see <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=core_services.html" format="https" scope="external"> Core Services - Enabling Your Solutions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2.Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID服務</span> 包含在每個您要用於資料收集的頁面上的JavaScript程式碼。See the ID service <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html" format="https" scope="external"> implementation guides</a> for more information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3.Read the <span class="keyword"> ID service</span> cookie</b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID服務</span> 會儲存AMCV Cookie中的使用者和地區ID。The full cookie name is <code>AMCV_<i>###</i>@AdobeOrg</code>. <code><i>###</i></code> elements是您組織ID的預留位置。See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>解析這些索引鍵值配對的AMCV Cookie： </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>使用者ID</i></code>：此金鑰-值對保留 <span class="keyword"> Experience Cloud</span> 使用者ID。 </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamweaver=<i>地區ID</i></code>：此金鑰值配對保留與區域伺服器名稱關聯的地區ID(有時稱為 <span class="term"> 位置提示</span>)。 </li> 
     </ul> </p> <p>You can make calls to the <span class="wintitle"> DCS</span> once you have the user and region IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4.Retrieve the <span class="keyword"> Experience Cloud ID</span> with getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(可選)</i> 此函數會傳回 <span class="keyword"> Experience Cloud</span> 訪客ID。它是專為自訂解決方案和特定使用案例而設計。See <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Working With getMarketingCloudVisitorID</a> below and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-getmcvid.html" format="https" scope="external"> related ID service documentation</a>. </p> <p>如果您從ID服務Cookie取得使用者和位置ID，則不需要使用此選項。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Working With `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Another way to get the visitor ID is with the `getMarketingCloudVisitorID` function. When invoked, this function queries the [!DNL ID service] and returns an ID. `getMarketingCloudVisitorID` 接受可選 `callback` 引數，如下所示：

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Callback Usage and Purpose {#callback-usage}

`callback` 是選擇性的。This function works without it, but returns an ID only when a visitor has a [!DNL Experience Cloud] cookie in their browser. If the visitor cookie is missing, or a visitor doesn&#39;t have an ID, the function returns an empty `()` object. 即使在頁面載入後，訪客收到新ID也會發生這種情況。To avoid this, `callback` forces this function to check for a visitor ID after the page loads. Without `callback`, the visitor ID function won&#39;t return an ID even if it&#39;s written to the visitor&#39;s browser later.

## 後續步驟 {#next-steps}

Once you have the user and region ID, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).