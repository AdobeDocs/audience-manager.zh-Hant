---
description: 執行個體層級的DILAPI可讓您以程式設計方式建立及使用Audience Manager物件。 執行個體層級方法可增強由類別層級方法建立的API功能。
keywords: 建立特徵；建立特徵
seo-description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
seo-title: Instance-level DIL Methods
solution: Audience Manager
title: 例項層級 DIL 方法
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
exl-id: 0342439d-708e-461c-b155-a3ee423f5437
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 13%

---

# 例項層級 DIL 方法{#instance-level-dil-methods}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 副檔名。
><br>
>現有客戶可繼續使用其 [!DNL DIL] 實作。 不過，Adobe將不會開發 [!DNL DIL] 超越此點。 建議客戶評估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 長期資料收集策略的影響。
><br>
>2023年7月後想要實作新資料收集整合的客戶應使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而非。

執行個體層級 [!UICONTROL DIL] API可讓您以程式設計方式建立及使用Audience Manager物件。 執行個體層級方法可增強由類別層級方法建立的API功能。

## 執行個體層級DIL方法快速入門 {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

使用例項層級時 [!UICONTROL DIL] API：

* 存取需要合作夥伴名稱和容器名稱空間ID (NSID)。 請聯絡您的Audience Manager客戶經理，以取得此資訊。
* 取代任何範例 *斜體* API檔案中的文字，其中包含值、ID或您使用的方法所需的其他變數。

<!-- 

c_instance_start.xml

 -->

## 訊號 {#signals}

將客戶和平台層級對應新增至待處理請求的查詢字串。

<!-- 

r_dil_signals.xml

 -->

**函式簽章：** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* 您可以將其他API呼叫連結至此方法。
>* 如果頁面上有Adobe Experience Cloud JavaScript程式庫， `submit()` 會等待雲端設定Cookie後再傳送請求。

**保留的請求金鑰**

下列要求金鑰已保留，且無法由此方法覆寫：

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `obj` | 物件 | 代表平台層級對應之索引鍵/值組的物件。 引數接受字串和陣列做為物件中的屬性值。 |
| `prefix` | 字串 | 選填。每個物件索引鍵加上前置詞的字串值（取代原始索引鍵）。 |
| `return` | DIL.api | 傳回目前DIL例項的API物件。 |

**回應**

傳回目前的API物件 [!UICONTROL DIL] 執行個體。

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
// Method 1 
var obj = { key1 : 1, key2 : 2 }; 
dataLib.api.signals(obj, 'c_').submit(); 
 
// Method 2 
dataLib.api.signals({c_zdid: 54321}).submit(); 
 
// Method 3 
// Will send 'c_key=a&c_key=2&c_key=3' to Audience Manager 
var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.signals(obj, 'c_').submit(); 
</code></pre>

## traits {#traits}

將SID新增至擱置中要求的查詢字串。

<!-- 

r_dil_traits.xml

 -->

**函式簽章：** `traits:function (sids){}`

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `sids` | 陣列 | 陣列中的特徵區段ID。 |

**回應**

傳回目前的API物件 [!UICONTROL DIL] 執行個體。

**程式碼範例**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## 記錄 {#logs}

將資料新增至擱置中請求的記錄檔。

<!-- 

r_dil_logs.xml

 -->

**函式簽章：** `logs: function {key1:value1, key2:value2}`

**回應**

傳回目前的API物件 [!UICONTROL DIL] 執行個體。

**程式碼範例**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});
</code></pre>

## 提交 {#submit}

提交所有待處理的資料給Audience Manager [!UICONTROL DIL] 執行個體。

<!-- 

r_dil_submit.xml

 -->

**函式簽章：** `submit: function () {}`

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。 此外， [!UICONTROL DIL] 將編碼資料寫入目的地Cookie。 例如，空格會編碼為 `%20` 和分號為 `%3B`.

**回應**

傳回目前的API物件 [!UICONTROL DIL] 執行個體。

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([ 
<i>123,456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}).submit();
</code></pre>

## afterResult {#afterresult}

在預設目的地發佈回呼之後執行的函式。

<!-- 

r_dil_after_result.xml

 -->

**函式簽章：** `afterResult: function (fn) {}`

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `fn` | 函數 | 處理目的地發佈的預設回呼處理JSON後，您要執行的函式。 |

**回應**

傳回目前的API物件 [!UICONTROL DIL] 執行個體。

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.signals({ 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
}).afterResult(function(json){ 
     //Do something with the JSON data returned from the server. 
}).submit();
</code></pre>

## clearData {#cleardata}

清除擱置要求中的所有資料。

<!-- 

r_dil_clear_data.xml

 -->

**函式簽章：** `clearData: function () {}`

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。

**回應**

傳回目前的API物件 [!UICONTROL DIL] 執行個體。

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ 
     file: 'dil.js' 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

將資料收集伺服器未明確定義的自訂查詢引數新增至擱置的要求。

<!-- 

r_dil_custom_query_params.xml

 -->

**函式簽章：** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。

**保留的請求金鑰**

下列要求金鑰已保留，且無法由此方法覆寫：

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**回應**

傳回目前DIL例項的API物件。

**程式碼範例**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.customQueryParams({ 
     nid: 54231, 
     ntype: 'default' 
}); 
</code></pre>

## getContainerNSID {#getcontainernsid}

傳回的容器NSID值 [!UICONTROL DIL] 執行個體。 用於偵錯和疑難排解。

<!-- 

r_dil_get_container_nsid.xml

 -->

**函式簽章：** `dil.api.getContainerNSID: function () {}`

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

以字串陣列形式傳回依時間順序排序的事件記錄檔資料。 用於偵錯和疑難排解。

<!-- 

r_dil_get_event_log.xml

 -->

**函式簽章：** `dil.api.getEventLog: function () {}`

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});.signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) { 
     alert(log.join('\n')); 
}else{ 
     alert('No log messages'); 
}
</code></pre>

## getPartner {#getpartner}

傳回的合作夥伴名稱 [!UICONTROL DIL] 執行個體。 用於偵錯和疑難排解。

<!-- 

r_dil_get_partner.xml

 -->

**函式簽章：** `dil.api.getPartner: function () {}`

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

傳回目前狀態 [!UICONTROL DIL] 執行個體。 用於偵錯和疑難排解。

<!-- 

r_dil_get_state.xml

 -->

**函式簽章：** `dil.api.getState: function () {}`

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message:'This is the first request' 
});.signals({ 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = { 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:{ 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: { 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          }, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     }, 
     destinationPublishingInfo: { 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          + containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

包含兩個函式，可讓資料合作夥伴在彼此之間交換和同步使用者ID以及Audience Manager。

<!-- 

r_dil_idsync.xml

 -->

**函式簽章：**

搭配使用 [!UICONTROL DIL] 版本2.10和3.1或更新版本。

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼 </th> 
   <th colname="col2" class="entry"> 同步使用者 ID </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>在不同的資料合作夥伴和Audience Manager之間。 例如，合作夥伴x會使用此專案將使用者ID與合作夥伴y同步，然後將其傳送給Audience Manager。 </p> <p> <p><b>重要：</b>  此方法已過時。 請使用 <code> idSyncByURL </code> Adobe Experience Platform Identity Service執行個體的方法。 </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>當您知道使用者ID並想要將其傳送給Audience Manager時。 </p> <p> <p><b>重要：</b>  此方法已過時。 請使用 <code> idSyncByDataSource </code> Adobe Experience Platform Identity Service執行個體的方法。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync元素**

`idSync` 可包含下列專案：

<table id="table_5343BE784E694C67B09A0A8878CF8001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名稱 </th> 
   <th colname="col2" class="entry"> 類型 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> 字串 </td> 
   <td colname="col3"> <p>Audience Manager 指派的資料提供者 ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 字串 </td> 
   <td colname="col3"> <p>資料提供者的使用者唯一 ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> minutesToLive </code> </td> 
   <td colname="col2"> 數字 </td> 
   <td colname="col3"> <p><i>(選用)</i> 設定 Cookie 過期時間。必須是整數。預設為 20160 分鐘 (14 天)。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> url </code> </td> 
   <td colname="col2"> 字串 </td> 
   <td colname="col3"> <p>目標 URL。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**巨集**

`idSync` 接受下列巨集：

* **`%TIMESTAMP%`：** 產生時間戳記（單位為毫秒）。 用於快取破產。
* **`%DID%`：** 插入使用者的Audience ManagerID。
* **`%HTTP_PROTO%`：** 設定頁面通訊協定( `http` 或 `https`)。

**回應**

這兩個函式都會傳回 `Successfully queued` 如果成功。 如果失敗則傳回錯誤訊息字串。

**程式碼範例**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync({ 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync({ 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

## 結果 {#result}

將回呼（接收JSON）新增至待處理請求。

<!-- 

r_dil_result.xml

 -->

**函式簽章：** `result: function (callback) {}`

此回呼會取代處理目的地發佈的預設回呼。

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `callback` | 函數 | 由JSONP回呼執行的JavaScript函式。 |

**回應**

傳回目前的API物件 [!UICONTROL DIL] 執行個體。

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ 
     //Do something, possibly with the JSON data returned from the server. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` 是布林值引數，可控制如何 [!UICONTROL DIL] 呼叫 [!UICONTROL Data Collection Servers (DCS)] 和Akamai。

<!-- 

dil-secure-data-collection.xml

 -->

* 時間 `secureDataCollection= true` （預設）， [!UICONTROL DIL] 一律會進行安全的HTTPS呼叫。

* 時間 `secureDataCollection= false`， [!UICONTROL DIL] 會依照頁面所設定的安全性通訊協定來進行HTTP或HTTPS呼叫。

>[!IMPORTANT]
>
>設定 `secureDataCollection= false` 如果您使用visitorAPI.js和 [!UICONTROL DIL] 在相同頁面上。 請參閱下列程式碼範例。

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     secureDataCollection: false 
});
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` 是布林值true/false引數，可控制瀏覽器如何從其他網域要求資源。

<!-- 

dil-use-cors-only.xml

 -->

**概述**

`useCORSOnly` 預設為false。 False表示瀏覽器可以使用CORS或JSONP執行資源檢查。 不過， [!UICONTROL DIL] 一律會先嘗試透過CORS要求資源。 在不支援 CORS 的舊版瀏覽器上會回復為 JSONP 要求。如果您需要強制瀏覽器僅使用CORS （例如搭配安全性要求高的網站），請設定 `useCORSOnly:true`.

**程式碼範例**

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     useCORSOnly: true 
});
</code></pre>

>[!IMPORTANT]
>
>* 我們建議您設定 `useCORSOnly: true` 只有在您確定您的網站訪客擁有支援此功能的瀏覽器時。
>* 時間 `useCORSOnly: true`， [!UICONTROL DIL] 不會從Internet Explorer 9或更舊版本進行ID呼叫。
>

## useImageRequest {#useimagerequest}

將請求型別變更為影像 `<img>` 從指令碼 `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**函式簽章：** `useImageRequest: function () {}`

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。

**回應**

傳回目前的API物件 [!UICONTROL DIL] 執行個體。

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [關鍵變數的名稱要求](../features/traits/trait-key-name-requirements.md)
>* [關鍵變數的前置詞要求](../features/traits/trait-variable-prefixes.md)
>* [Adobe Experience Platform Identity Service中的同步化函式](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/idsync.html)
>* [DIL 建立](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Adobe Experience Platform Identity服務： UseCORSOnly](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [Adobe Experience Platform Identity服務的CORS支援](https://experienceleague.adobe.com/docs/id-service/using/reference/cors.html)
