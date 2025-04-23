---
description: ID服務客戶應參閱本節，瞭解如何讀取進行DCS API呼叫所需ID的訪客Cookie。
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: 透過Adobe Experience Platform Identity Service取得使用者ID和區域
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: e17eedfb94f2936c61298c44f3d556bae254b2a7
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 2%

---

# 透過Adobe Experience Platform Identity Service取得使用者ID和區域 {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID服務客戶應參閱本節，瞭解如何讀取進行[!DNL DCS] API呼叫所需ID的訪客Cookie。

## 從ID服務Cookie取得使用者ID {#get-user-ids-from-service-cookie}

[Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)會將訪客與地區ID指派給造訪您網站的使用者。 這些ID可識別[!DNL Experience Cloud]中所有解決方案的使用者，如果您想進行[!DNL DCS]呼叫，則需使用這些ID。

* 需要[!UICONTROL user ID]才能識別資料並與特定訪客建立關聯。
* [!UICONTROL region ID]為必要項，因為它繫結至區域伺服器名稱，您必須傳送資料給[!DNL DCS]。 [!DNL DCS]會將資訊儲存在地理位置上最接近網站訪客的資料中心。 請參閱 [DCS 地區 ID、位置與主機名稱](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

ID服務客戶可以從ID服務Cookie或透過呼叫函式來擷取此資訊。 下表說明開始使用所需完成的工作或步驟。

*斜體*&#x200B;中的程式碼代表變數預留位置。

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 任務 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. 檢查您的<span class="keyword"> Experience Cloud</span>狀態</b> </p> </td> 
   <td colname="col2"> <p>您需要<span class="keyword"> Experience Cloud</span>帳戶才能使用ID服務。 如果您有<span class="keyword"> Experience Cloud</span>帳戶，很好！ </p> <p> 如果您不屬於<span class="keyword"> Experience Cloud</span>，請註冊。 我們很樂意擁有您，而且永遠有更多的空間。 如需如何設定帳戶的指示，請參閱<a href="https://experienceleague.adobe.com/en/docs/core-services/interface/services/getting-started" format="https" scope="external">啟用核心服務的解決方案</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2.設定<span class="keyword"> ID服務</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID服務</span>包含JavaScript程式碼，這些程式碼會放在您要用於資料收集的每一個頁面上。 如需詳細資訊，請參閱ID服務<a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external">實作指南</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3.讀取<span class="keyword"> ID服務</span> Cookie</b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID服務</span>會將使用者和地區ID儲存在AMCV Cookie中。 完整的Cookie名稱為<code>AMCV_<i>###</i>@AdobeOrg</code>。 <code><i>###</i></code>元素是您組織ID的預留位置。 如需詳細資訊，請參閱<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie與Experience Cloud ID</a>。 </p> <p>剖析這些機碼值組的AMCV Cookie： </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>：這個機碼值組包含<span class="keyword"> Experience Cloud</span>使用者識別碼。 </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>：這個機碼值組儲存與地區伺服器名稱關聯的地區識別碼（有時稱為<span class="term">位置提示</span>）。 </li> 
     </ul> </p> <p>一旦您擁有使用者和地區ID，即可呼叫<span class="wintitle"> DCS</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4.使用getMarketingCloudVisitorID</b>擷取<span class="keyword"> Experience Cloud ID</span> </p> </td> 
   <td colname="col2"> <p><i>（選擇性）</i>此函式傳回<span class="keyword"> Experience Cloud</span>訪客識別碼。 此範本專為自訂解決方案和特定使用案例而設計。 請參閱下列<a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid">使用getMarketingCloudVisitorID</a>以及<a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external">相關的ID服務檔案</a>。 </p> <p>如果您從ID服務Cookie取得使用者和位置ID，則不需要使用此選項。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用`getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

另一種取得訪客ID的方法是使用`getMarketingCloudVisitorID`函式。 叫用時，此函式會查詢[!DNL ID service]並傳回識別碼。 `getMarketingCloudVisitorID`接受選用的`callback`引數，如下所示：

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### 回呼使用情況和用途 {#callback-usage}

`callback`是選用專案。 此函式可在沒有它的情況下運作，但只有在訪客的瀏覽器中有[!DNL Experience Cloud] Cookie時才會傳回ID。 如果訪客Cookie遺失，或訪客沒有ID，此函式會傳回空的`()`物件。 即使頁面載入且訪客收到新ID，也可能會發生這種情況。 為避免此問題，`callback`強制此函式在頁面載入後檢查訪客ID。 如果沒有`callback`，即使稍後將訪客ID寫入訪客的瀏覽器，訪客ID函式也不會傳回ID。

## 後續步驟 {#next-steps}

擁有使用者和地區ID後，您就可以開始傳送和接收[!DNL DCS]資料。 請參閱[進行DCS API呼叫](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)。
