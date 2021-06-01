---
description: ID服務客戶應參閱本節，了解如何讀取訪客Cookie以取得進行DCS API呼叫所需的ID。
seo-description: ID服務客戶應參閱本節，了解如何讀取訪客Cookie以取得進行DCS API呼叫所需的ID。
seo-title: 透過 Adobe Experience Platform Identity Service 取得使用者 ID 和區域
solution: Audience Manager
title: 透過 Adobe Experience Platform Identity Service 取得使用者 ID 和區域
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 9%

---

# 透過 Adobe Experience Platform Identity Service 取得使用者 ID 和區域 {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID服務客戶應參閱本區段，了解如何讀取訪客Cookie，以取得進行[!DNL DCS] API呼叫所需的ID。

## 從ID服務Cookie {#get-user-ids-from-service-cookie}取得使用者ID

[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html)會將訪客和地區ID指派給來到您網站的使用者。 這些ID可識別[!DNL Experience Cloud]中所有解決方案的使用者，如果您想進行[!DNL DCS]呼叫，則需要這些ID。

* 需要[!UICONTROL user ID]來識別資料並將資料與特定訪客關聯。
* [!UICONTROL region ID]是必需的，因為它與區域伺服器名稱相連結，您需要將資料發送到[!DNL DCS]。 [!DNL DCS]會將資訊儲存在地理位置上最接近網站訪客的資料中心。 請參閱 [DCS 地區 ID、位置與主機名稱](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

ID服務客戶可從ID服務Cookie或呼叫函式擷取此資訊。 下表說明開始使用所需完成的任務或步驟。

*斜體*&#x200B;中的代碼表示變數預留位置。

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 任務 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. 檢查<span class="keyword">Experience Cloud</span>狀態</b> </p> </td> 
   <td colname="col2"> <p>您需要<span class="keyword">Experience Cloud</span>帳戶才能使用ID服務。 如果您有<span class="keyword">Experience Cloud</span>帳戶，太好了！ </p> <p> 如果您不是<span class="keyword">Experience Cloud</span>的成員，請註冊。 我們很想擁有你，總有更多空間。 如需如何設定帳戶的指示，請參閱<a href="https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html" format="https" scope="external">啟用核心服務的解決方案</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2.設定<span class="keyword"> ID服務</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID服務</span>包含JavaScript程式碼，這些程式碼會放在您要用於資料收集的每個頁面上。 如需詳細資訊，請參閱ID服務<a href="https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html" format="https" scope="external">實作指南</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3.閱讀<span class="keyword"> ID服務</span> cookie</b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID服務</span>會將使用者和地區ID儲存在AMCV Cookie中。 完整的Cookie名稱為<code>AMCV_<i>###</i>@AdobeOrg</code>。 <code><i>###</i></code>元素是組織ID的預留位置。 如需詳細資訊，請參閱<a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Experience CloudID</a> 。 </p> <p>剖析這些機碼值組的AMCV Cookie: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>:此機碼值組包含Experience  <span class="keyword"> Cloud</span> 使用者ID。 </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>:此機碼值組保有與地區伺服器名稱相關聯的地區ID(有 <span class="term"> 時稱為位置提示</span>)。 </li> 
     </ul> </p> <p>擁有使用者和地區ID後，您就可以呼叫<span class="wintitle"> DCS</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4.使用getMarketingCloudVisitorID</b>擷取<span class="keyword">Experience CloudID</span> </p> </td> 
   <td colname="col2"> <p><i>（選用）</i> 此函式會傳回 <span class="keyword"> Experience </span> Cloud訪客ID。專為自訂解決方案和特定使用案例而設計。 請參閱下方的<a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid">使用getMarketingCloudVisitorID</a>以及<a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external">相關ID服務檔案</a>。 </p> <p>如果您從ID服務Cookie取得使用者和位置ID，便不需要使用此ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用`getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

另一種取得訪客ID的方式是使用`getMarketingCloudVisitorID`函式。 調用時，此函式將查詢[!DNL ID service]並返回ID。 `getMarketingCloudVisitorID` 接受選用 `callback` 引數，如下所示：

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### 回呼使用與用途{#callback-usage}

`callback` 為選用。此函式沒有它即可運作，但只有當訪客的瀏覽器中有[!DNL Experience Cloud] Cookie時，才會傳回ID。 如果訪客Cookie遺失，或訪客沒有ID，函式會傳回空的`()`物件。 即使在頁面載入且訪客收到新ID後，也可能發生此情況。 為避免此問題，`callback`會強制此函式在頁面載入後檢查訪客ID。 若沒有`callback`，即使稍後寫入訪客的瀏覽器，訪客ID函式也不會傳回ID。

## 後續步驟 {#next-steps}

擁有用戶和地區ID後，您就可以開始發送和接收[!DNL DCS]資料。 請參閱「進行DCS API呼叫](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)」。[
