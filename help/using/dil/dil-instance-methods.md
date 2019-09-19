---
description: 例項層級的DIL API可讓您以程式設計方式建立並使用Audience manager物件。 例項層級方法可增強由類別層級方法建立的API功能。
keywords: 建立特徵；建立特徵
seo-description: 例項層級的DIL API可讓您以程式設計方式建立並使用Audience manager物件。 例項層級方法可增強由類別層級方法建立的API功能。
seo-title: 例項層級DIL方法
solution: Audience Manager
title: 例項層級DIL方法
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 例項層級DIL方法{#instance-level-dil-methods}

例項層級的 [!UICONTROL DIL] API可讓您以程式設計方式建立及使用Audience manager物件。 例項層級方法可增強由類別層級方法建立的API功能。

## 例項層級DIL方法快速入門 {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

使用例項層級的API時 [!UICONTROL DIL] :

* 存取需要合作夥伴名稱和容器名稱空間ID(NSID)。 請連絡您的Audience manager客戶經理以取得此資訊。
* 根據您所 *使用之方法* ，以值、ID或其他變數取代API檔案中任何斜體文字範例。

<!-- 

c_instance_start.xml

 -->

## 信號 {#signals}

將客戶和平台層級對應新增至待定請求的查詢字串。

<!-- 

r_dil_signals.xml

 -->

**** 函式簽名： `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* 您可以將其他API呼叫連結至此方法。
>* 如果頁面上有Adobe Experience Cloud javaScript程式庫， `submit()` 請等待Cloud設定Cookie，再傳送請求。


**保留請求金鑰**

下列請求金鑰會保留，此方法無法覆寫：

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `obj` | 物件 | 表示平台級映射的鍵值對的對象。 參數接受字串和陣列作為對象中的屬性值。 |
| `prefix` | 字串 | 選填。每個物件索引鍵前置的字串值（取代原始索引鍵）。 |
| `return` | DIL.api | 傳回目前DIL例項的API物件。 |

**回應**

傳回目前例項的API物 [!UICONTROL DIL] 件。

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>' containerNSID:容 <i>器NSID</i> });
 
//方法1 var obj = { key1 :1, key2:2 };
dataLib.api.signals(obj, 'c_')。submit();
 
//方法2 dataLib.api.signals({c_zdid:54321})。submit();
 
//方法3 //將傳送'c_key=a&amp;c_key=2&amp;c_key=3'至Audience Manager var obj = { key:['a'、'b'、'c'] };
dataLib.api.signals(obj, 'c_')。submit(); 
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [關鍵變數的名稱要求](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

將SID新增至待定請求的查詢字串。

<!-- 

r_dil_traits.xml

 -->

**** 函式簽名： `traits:function (sids){}`

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `sids` | 陣列 | 陣列中的特徵區段ID。 |

**回應**

傳回目前例項的API物 [!UICONTROL DIL] 件。

**程式碼範例**

<pre><code>
var partnerObject = DIL.create({ partner:'<i>合作夥伴名稱</i>', containerNSID: <i>NSID</i> });
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

將資料新增至待審請求中的記錄檔。

<!-- 

r_dil_logs.xml

 -->

**** 函式簽名： `logs: function {key1:value1, key2:value2}`

**回應**

傳回目前例項的API物 [!UICONTROL DIL] 件。

**程式碼範例**

<pre><code>
var partnerObject = DIL.create({ partner:'<i>partner</i>', containerNSID: <i>NSID</i> });
partnerObject.api.logs({ file:'dil.js'，訊息：'This is the first request' });
</code></pre>

## 提交 {#submit}

將所有待審資料提交至Audience Manager，以供執行 [!UICONTROL DIL] 個體使用。

<!-- 

r_dil_submit.xml

 -->

**** 函式簽名： `submit: function () {}`

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。 此外， [!UICONTROL DIL] 將編碼資料寫入目標Cookie。 例如，空格會編碼為 `%20` 分號和分號 `%3B`。

**回應**

傳回目前例項的API物 [!UICONTROL DIL] 件。

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.traits([<i>123,456, 789</i>])。logs({檔案：'dil.js'，訊息：'This is the first request' })。signals({ c_zdid: <i>111</i> d_dma:'<i>default</i>' })。submit();
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [關鍵變數的前置詞要求](../features/traits/trait-variable-prefixes.md)


## afterResult {#afterresult}

在預設目標發佈回呼後執行的函式。

<!-- 

r_dil_after_result.xml

 -->

**** 函式簽名： `afterResult: function (fn) {}`

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `fn` | 函數 | 您要在JSON之後執行的函式，會由處理目標發佈的預設回呼處理。 |

**回應**

傳回目前例項的API物 [!UICONTROL DIL] 件。

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.signals({ c_zdid: <i>54321</i> d_dma:'<i>default</i>' })。afterResult(function(json){ //對從伺服器傳回的JSON資料執行動作。 
}).提交();
</code></pre>

## clearData {#cleardata}

清除待審請求中的所有資料。

<!-- 

r_dil_clear_data.xml

 -->

**** 函式簽名： `clearData: function () {}`

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。

**回應**

傳回目前例項的API物 [!UICONTROL DIL] 件。

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.traits([<i>123,456, 789</i>])。logs({檔案：'dil.js'訊息：'This is the first request' })。signals({ c_zdid: <i>111</i> d_dma:'<i>default</i>' });
 
//重設待審資料dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

將資料收集伺服器未明確定義的自訂查詢參數新增至待定請求。

<!-- 

r_dil_custom_query_params.xml

 -->

**** 函式簽名： `customQueryParams: function (obj) {}`

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。

**保留請求金鑰**

下列請求金鑰會保留，此方法無法覆寫：

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
var partnerObject = DIL.create({ partner:'<i>partner</i>', containerNSID: <i>NSID</i> });
partnerObject.api.customQueryParams({ nid:54231，類型：'default' }); 
</code></pre>

## getContainerNSID {#getcontainernsid}

傳回例項的容器NSID [!UICONTROL DIL] 值。 用於除錯和疑難排解。

<!-- 

r_dil_get_container_nsid.xml

 -->

**** 函式簽名： `dil.api.getContainerNSID: function () {}`

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
//Verify the container NSID var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

以字串陣列的形式傳回按時間順序排序的事件記錄資料。 用於除錯和疑難排解。

<!-- 

r_dil_get_event_log.xml

 -->

**** 函式簽名： `dil.api.getEventLog: function () {}`

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.traits([<i>123, 456, 789</i>])。logs({檔案：'dil.js'，訊息：'This is the first request' });.signals({ c_zdid: <i>111</i> d_dma:'<i>default</i>' });.submit();
 
//Check log for messages var log = dataLib.api.getEventLog();
if(log &amp;&amp; log.length){ alert(log.join('\n'));
}else{ alert('no log messages');
}</code></pre>

## getPartner {#getpartner}

傳回例項的合作夥伴 [!UICONTROL DIL] 名稱。 用於除錯和疑難排解。

<!-- 

r_dil_get_partner.xml

 -->

**** 函式簽名： `dil.api.getPartner: function () {}`

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>' containerNSID:容 <i>器NSID</i> });
 
//Verify the partner name var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

傳回目前例項的狀 [!UICONTROL DIL] 態。 用於除錯和疑難排解。

<!-- 

r_dil_get_state.xml

 -->

**** 函式簽名： `dil.api.getState: function () {}`

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.traits([<i>123, 456, 789</i>])。logs({檔案：'dil.js', message:'This is the first request' });.signals({ c.zdid: <i>111</i> d_dma:'<i>default</i>' });.submit();
 
var state = dataLib.api.getState();
 
/*狀態狀態的物件外框= { pendingRequest:{<i>Pending data for call to server</i>}, otherRequestInfo:{ firingQueue:[]，已引發：[]，引發：false，錯誤：[]，保留密鑰：{ sids:true, pdata:true,logdata:true，回呼：true, postCallbackFn:true, useImageRequest:true, }, firstRequestHasFirned:false,num_of_jsonp_responses:0,num_of_jsonp_errors:0, num_of_img_responses:0,num_of_img_errors:0 },destinationPublishingInfo:{ THROTTLE_START:3000, throttleTimerSet:false, id:"destination_publishing_iframe_' + partner + '_' + containerNSID, url:(constants.isHTTPS? 'https://':'https://fast.')+ partner + '.demdex.net/dest3.html?d_nsid=' + containerNSID + '#' + encodeURIComponent(document.location.href), iframe:null, iframeHasLoaded:false, sendingMessages:false，訊息：[], messageSendingInterval:常數。POST_MESSAGE_ENABLED ? 15:IE 6 &amp; 7需100, //建議100ms，其他瀏覽器則需15msjson已處理：[] } } */</code></pre>

## idSync {#idsync}

由兩個功能組成，可讓資料合作夥伴在他們和Audience Manager之間交換及同步使用者ID。

<!-- 

r_dil_idsync.xml

 -->

**函式簽名：**

適用於 [!UICONTROL DIL] 2.10和3.1版或更新版本。

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
   <td colname="col2"> <p>不同資料合作夥伴和Audience Manager之間。 例如，合作夥伴x會使用此項來同步使用者ID與合作夥伴y，然後將其傳送至Audience Manager。 </p> <p> <p><b></b> 重要： 此方法已過時。 請使用Experience Cloud <code> ID服務 </code> 例項的idSyncByURL方法。 </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>當您已知道使用者ID，並想要將它傳送至Audience Manager時。 </p> <p> <p><b></b> 重要： 此方法已過時。 請使用Experience Cloud <code> ID服務 </code> 例項的idSyncByDataSource方法。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync Elements**

`idSync` 可包含下列項目：

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

`idSync` 接受以下宏：

* **`%TIMESTAMP%`** :生成時間戳（以毫秒為單位）。 用於快取破產。
* **`%DID%`** :插入使用者的Audience Manager ID。
* **`%HTTP_PROTO%`** :設定頁面通訊協定( `http` 或 `https`)。

**回應**

Both functions return `Successfully queued` if successful. 如果失敗則傳回錯誤訊息字串。

**程式碼範例**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced dilInstance.api.idSync({ dpid:'23', //必須是字串URL:'//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net %2Fibs%3Adpid%3D420%26dpuuid%3D%7Buid%7D7D',minutesToLive:20160 //選用，預設為20160分鐘（14天）});
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
//觸發'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&amp;dpuuid=&lt;dpuuid&gt;' dilInstance.api.aamIdSync({ dpid:'23', //必須是字串dpuuid:'98765', //必須是字串minutesToLive:20160 //選用，預設為20160分鐘（14天）});
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [Experience Cloud ID服務中的同步函式](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

新增回呼（接收JSON）至待審請求。

<!-- 

r_dil_result.xml

 -->

**** 函式簽名： `result: function (callback) {}`

此回呼會取代處理目標發佈的預設回呼。

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `callback` | 函數 | 由JSONP回呼執行的JavaScript函式。 |

**回應**

傳回目前例項的API物 [!UICONTROL DIL] 件。

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.traits([<i>123, 456, 789</i>])。result(function(json){ //Do seamply, with the JSON data resurted from the server. 
});.提交();
</code></pre>

##  secureDataCollection {#securedatacollection}

`secureDataCollection` 是布林參數，可控制對 [!UICONTROL DIL] 和Akamai進行呼叫 [!UICONTROL Data Collection Servers (DCS)] 的方式。

<!-- 

dil-secure-data-collection.xml

 -->

* 當( `secureDataCollection= true` 預設)時， [!UICONTROL DIL] 一律進行安全的HTTPS呼叫。

* 當發 `secureDataCollection= false`生 [!UICONTROL DIL] 時，請遵循頁面設定的安全通訊協定，進行HTTP或HTTPS呼叫。

>[!IMPORTANT]
>
>若您 `secureDataCollection= false` 在相同頁面上使用visitorAPI.js [!UICONTROL DIL] ，請加以設定。 請參閱以下程式碼範例。

<pre><code class="js">
var dilInstance = DIL.create({ ...
     secureDataCollection:false });
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [DIL建立](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` 是布林值true/false參數，可控制瀏覽器從其他網域要求資源的方式。

<!-- 

dil-use-cors-only.xml

 -->

**概述**

`useCORSOnly` 預設為false。 False表示瀏覽器可以使用CORS或JSONP執行資源檢查。 不過， [!UICONTROL DIL] 一律會先嘗試向CORS請求資源。 在不支援 CORS 的舊版瀏覽器上會回復為 JSONP 要求。如果您需要強制瀏覽器僅使用CORS，例如針對安全性要求較高的網站，請加以設定 `useCORSOnly:true`。

**程式碼範例**

<pre><code class="js">
var dilInstance = DIL.create({ ...
     useCORSOnly:true });
</code></pre>

>[!IMPORTANT]
>
>* 我們建議您僅在確 `useCORSOnly: true` 定您的網站訪客擁有支援此功能的瀏覽器時進行設定。
>* 當發 `useCORSOnly: true`生 [!UICONTROL DIL] 時，將不會從Internet Explorer 9版或更舊版本呼叫ID。
>



>[!MORE_LIKE_THIS]
>
>* [DIL建立](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Experience Cloud ID服務：UseCORSOnly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [Experience Cloud ID 服務的 CORS 支援](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## useImageRequest {#useimagerequest}

將請求類型從指令碼變更 `<img>` 為影像 `<src>`。

<!-- 

r_dil_use_image_request.xml

 -->

**** 函式簽名： `useImageRequest: function () {}`

>[!NOTE]
>
>您可以將其他API呼叫連結至此方法。

**回應**

傳回目前例項的API物 [!UICONTROL DIL] 件。

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID:容 <i>器NSID</i> });
 
dataLib.api.traits([<i>123, 456, 789</i>])。useImageRequest()。submit();
</code></pre>

