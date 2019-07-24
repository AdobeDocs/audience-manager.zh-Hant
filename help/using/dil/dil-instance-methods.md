---
description: 例項層級的DIL API可讓您以程式設計方式建立和搭配Audience Manager物件使用。例項層級方法增強了由類別層級方法建立的API功能。
keywords: 建立特徵；建立特徵
seo-description: 例項層級的DIL API可讓您以程式設計方式建立和搭配Audience Manager物件使用。例項層級方法增強了由類別層級方法建立的API功能。
seo-title: 例項層級DIL方法
solution: Audience Manager
title: 例項層級DIL方法
uuid: aa5147bb-51d5-41d4-a78 a-e550 f7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Instance-level DIL Methods{#instance-level-dil-methods}

The instance-level [!UICONTROL DIL] APIs let you programmatically create and work with Audience Manager objects. 例項層級方法增強了由類別層級方法建立的API功能。

## Getting started with Instance-level DIL Methods {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

When working with the instance-level [!UICONTROL DIL] APIs:

* 存取需要合作夥伴名稱和容器命名空間ID(NSID)。請連絡Audience Manager帳戶管理員以取得此資訊。
* Replace any sample *italicized* text in the API documentation with value, ID, or other variable as required by the method you're working with.

<!-- 

c_instance_start.xml

 -->

## signals {#signals}

新增客戶和平台層級對應至待定請求的查詢字串。

<!-- 

r_dil_signals.xml

 -->

**函數簽名：**`signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* 您可以將其他API呼叫鏈結至此方法。
>* If the Adobe Experience Cloud JavaScript library is on the page, `submit()` waits for the Cloud to set a cookie before sending a request.


**保留請求索引鍵**

保留下列請求索引鍵，且無法覆寫此方法：

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `obj` | 物件 | 代表平台層級對應之索引鍵值配對的物件。參數接受字串和陣列作為物件中的屬性值。 |
| `prefix` | 字串 | 選填。字串值前置詞為每個物件索引鍵(取代原始金鑰)。 |
| `return` | DIL. api | 傳回目前DIL實例的API物件。 |

**回應**

Returns the API object of the current [!UICONTROL DIL] instance.

**程式碼範例**

<pre><code>var datalIb= DIL. create({
合作夥伴：'<i>parterName</i>'
containernSID： <i>containernSID</i> })；

//方法1var obj={key1：1，key2：}；
DataAlb. api. documents(obj，'c_'). mit()；

//方法dataAlb. api. documents({c_ zid：54321}). mit()；

//方法//將傳送「c_ key= a&amp; c_ key=2&amp; c_ key=3」至Audience Manager 
var obj={key：['a'，'b'，'c']}；
DataAlb. api. documents(obj，'c_'). mit()；</code>
</pre>

>[!MORE_贊_ this]
>
>* [關鍵變數的名稱需求](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

將SID新增至待定請求的查詢字串。

<!-- 

r_dil_traits.xml

 -->

**函數簽名：**`traits:function (sids){}`

>[!NOTE]
>
>您可以將其他API呼叫鏈結至此方法。

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `sids` | 陣列 | 特徵中的特徵區段ID。 |

**回應**

Returns the API object of the current [!UICONTROL DIL] instance.

**程式碼範例**

<pre><code>var PartnerObject= DIL. create({
合作夥伴：<i>'合作夥伴姓名</i>'，
containernSID： <i>NSID</i> })；
PartnerObject. api. properties(<i>[123，456，789]</i>)；</code>
</pre>

## logs {#logs}

新增資料至待定請求中的記錄檔。

<!-- 

r_dil_logs.xml

 -->

**函數簽名：**`logs: function {key1:value1, key2:value2}`

**回應**

Returns the API object of the current [!UICONTROL DIL] instance.

**程式碼範例**

<pre><code>var PartnerObject= DIL. create({
合作夥伴：<i>'合作夥伴</i>'，
containernSID： <i>NSID</i> })；
PartnerObject. api. log({
檔案：'dil. js'，
訊息：'this is the first request'})；</code>
</pre>

## 提交 {#submit}

Submits all pending data to Audience Manager for the [!UICONTROL DIL] instance.

<!-- 

r_dil_submit.xml

 -->

**函數簽名：**`submit: function () {}`

>[!NOTE]
>
>您可以將其他API呼叫鏈結至此方法。Also, [!UICONTROL DIL] writes encoded data to a destination cookie. For example, spaces are encoded as `%20` and semicolons as `%3B`.

**回應**

Returns the API object of the current [!UICONTROL DIL] instance.

**程式碼範例**

<pre><code>var datalIb= DIL. create({
合作夥伴：'<i>parterName</i>'，
containernSID： <i>containernSID</i> })；

DataAlb. api. properties([<i>123,456，789</i>]). 
log({
檔案：'dil. js'，
訊息：'this is the first request'}). 
documents({
c_ zid： <i>1111</i> 
d_ dma：'<i>default</i>'}). 
mit()；</code>
</pre>

>[!MORE_贊_ this]
>
>* [關鍵變數的首碼需求](../features/traits/trait-variable-prefixes.md)


## afterResult {#afterresult}

在預設目的地發佈回呼之後執行的函數。

<!-- 

r_dil_after_result.xml

 -->

**函數簽名：**`afterResult: function (fn) {}`

>[!NOTE]
>
>您可以將其他API呼叫鏈結至此方法。

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `fn` | 函數 | JSON之後要執行的函數會由處理目的地發佈的預設回呼處理。 |

**回應**

Returns an API object of the current [!UICONTROL DIL] instance.

**程式碼範例**

<pre><code>var datalIb= DIL. create({
合作夥伴：'<i>parterName</i>'，
containernSID： <i>containernSID</i> })；

DataAlb. api. documents({
c_ zid： <i>54321</i> 
d_ dma：'<i>default</i>'}). 
afterResult(function(json){
使用從伺服器傳回的JSON資料來呈現內容。 
}).提交();
</code></pre>

## clearData {#cleardata}

清除待定請求中的所有資料。

<!-- 

r_dil_clear_data.xml

 -->

**函數簽名：**`clearData: function () {}`

>[!NOTE]
>
>您可以將其他API呼叫鏈結至此方法。

**回應**

Returns the API object of the current [!UICONTROL DIL] instance.

**程式碼範例**

<pre><code>var datalIb= DIL. create({
合作夥伴：'<i>parterName</i>'，
containernSID： <i>containernSID</i> })；

DataAlb. api. properties([<i>123,456，789</i>]). log({
檔案：'dil. js''
訊息：'this is the first request'}). 
documents({
c_ zid： <i>1111</i> 
d_ dma：'<i>default</i>'})；

//Reset待定資料DatalIb. 
clearData()；</code>
</pre>

## customQueryParams {#customqueryparams}

新增未由資料收集伺服器明確定義到待定請求的自訂查詢參數。

<!-- 

r_dil_custom_query_params.xml

 -->

**函數簽名：**`customQueryParams: function (obj) {}`

>[!NOTE]
>
>您可以將其他API呼叫鏈結至此方法。

**保留請求索引鍵**

保留下列請求索引鍵，且無法覆寫此方法：

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**回應**

傳回目前DIL實例的API物件。

**程式碼範例**

<pre><code>var PartnerObject= DIL. create({
合作夥伴：<i>'合作夥伴</i>'，
containernSID： <i>NSID</i> })；
PartnerObject. api. customQueryParams({
nid：54231，
ntype：'default'})；</code>
</pre>

## getContainerNSID {#getcontainernsid}

Returns the value of the container NSID for the [!UICONTROL DIL] instance. 用於除錯和疑難排解。

<!-- 

r_dil_get_container_nsid.xml

 -->

**函數簽名：**`dil.api.getContainerNSID: function () {}`

**程式碼範例**

<pre><code>var datalIb= DIL. create({
合作夥伴：'<i>parterName</i>'，
containernSID： <i>containernSID</i> })；

//Verify容器NSID 
var nsid= DataAlB. api. getContainernSID()；</code>
</pre>

## getEventLog {#geteventlog}

傳回時間順序排序事件記錄資料作為字串陣列。用於除錯和疑難排解。

<!-- 

r_dil_get_event_log.xml

 -->

**函數簽名：**`dil.api.getEventLog: function () {}`

**程式碼範例**

<pre><code>var datalIb= DIL. create({
合作夥伴：'<i>parterName</i>'，
containernSID： <i>containernSID</i> })；

DataAlb. api. properties([<i>123，456，789</i>]). log({
檔案：'dil. js'，
訊息：'this is the first request'})；.訊號({
c_ zid： <i>1111</i> 
d_ dma：'<i>default</i>'})；. mit()；

sociallog for messages 
var log= datailB. api. getEventLog()；
if(log&amp;&amp; log. length){
alert(log. complement('\ n'))；
}其他{
警告('No log messages')；
}</code>
</pre>

## getPartner {#getpartner}

Returns the partner name for a [!UICONTROL DIL] instance. 用於除錯和疑難排解。

<!-- 

r_dil_get_partner.xml

 -->

**函數簽名：**`dil.api.getPartner: function () {}`

**程式碼範例**

<pre><code>var datalIb= DIL. create({
合作夥伴：'<i>parterName</i>'
containernSID： <i>containernSID</i> })；

//Verify合作夥伴名稱var 
partner= DataAlb. api. getPartner()；</code>
</pre>

## getState {#getstate}

Returns the state of the current [!UICONTROL DIL] instance. 用於除錯和疑難排解。

<!-- 

r_dil_get_state.xml

 -->

**函數簽名：**`dil.api.getState: function () {}`

**程式碼範例**

<pre><code>var datalIb= DIL. create({
合作夥伴：'<i>parterName</i>'，
containernSID： <i>containernSID</i> })；

DataAlb. api. properties([<i>123，456，789</i>]). log({
檔案：'dil. js'，
訊息：'this is the first request'})；.訊號({
c. zid： <i>1111</i> 
d_ dma：'<i>default</i>'})；. mit()；

var state= datailB. api. getState()；

/*狀態狀態的物件外框={
RecordingRequest：呼叫<i>伺服器</i>}的{擱置資料：
ExtrequestInfo：{
確認佇列：[]，
引發：[]，
引發：false，
錯誤：[]，
ReservedKeys：{
sids：true，
pdata：true，
logdata：true，
回呼：true，
PostcallBackfn：true，
useImageRequest：true，
}
防火牆：false，
num_ of_ jsonp_ response：0，
num_ of_ jsonp_ errors：0，
num_ of_ img_ response：0，
num_ of_ img_ errors：0
}
DestinationPublishingInfo：{
TRANTERT_ START：3000，
RocktleTimerSet：false，
id：「standing_ publishing_ iframe_'+ partner+'_'+ containernSID，
url：(常數. isHtTPS？https://'：「https://fast.')」+合作夥伴+'.demdex.net/dest3.html?d_nsid='
+ containernsID+'#'+ encodeURIComponent(document. location. href)，
iframe：null、
iFrameHasLoaded：false，
SendingMessages：false，
訊息：[]，
MessageSendingInterval：常數。POST_ MANAGE_ EXTENLED？15: 100, 
               //Recommend 100ms for IE 6 &amp; 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

包含兩項功能，可讓資料合作夥伴在自己和Audience Manager之間交換和同步化使用者ID。

<!-- 

r_dil_idsync.xml

 -->

**函數簽名：**

Works with [!UICONTROL DIL] versions 2.10 and 3.1 or higher.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼 </th> 
   <th colname="col2" class="entry"> 同步使用者 ID </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. Instance. api. idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>不同資料合作夥伴和Audience Manager之間。例如，合作夥伴x會使用此項目將使用者ID與合作夥伴y同步，然後將其傳送至Audience Manager。 </p> <p> <p><b>重要：</b> 此方法已停用。Please use the <code> idSyncByURL </code> method of the Experience Cloud ID Service instance. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. Instance. api. aIFSync(initConfig) </code> </td> 
   <td colname="col2"> <p>當您已知道使用者ID並想要傳送至Audience Manager時。 </p> <p> <p><b>重要：</b> 此方法已停用。Please use the <code> idSyncByDataSource </code> method of the Experience Cloud ID Service instance. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**IdSync Elements**

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

`idSync` 接受下列巨集：

* **`%TIMESTAMP%`：** 產生時間戳記(以毫秒為單位)。用於快取破產。
* **`%DID%`：** 插入使用者的Audience Manager ID。
* **`%HTTP_PROTO%`：** 設定頁面通訊協定( `http` 或 `https`)。

**回應**

Both functions return `Successfully queued` if successful. 如果失敗則傳回錯誤訊息字串。

**程式碼範例**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">//使用巨集取代具有巨集的URL. 
api. idSync({Sync)
dpid：'23'，//必須是字串
url：'//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D'7D'
TargetToLive：20160//可選，預設為20160分鐘(14天)})；</code>
</pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">//fire'loc+'//loc&lt; dpid&gt;&amp; dpuuid=&lt; dpuuid&gt;'Dilintition. 
api. aIAmSync({
dpid：'23'，//必須是字串
dpuuid：'98765'，//必須是字串
TargetToLive：20160//可選，預設為20160分鐘(14天)})；</code>
</pre>

>[!MORE_贊_ this]
>
>* [Experience Cloud ID服務中的同步函數](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

新增回呼(接收JSON)至待定請求。

<!-- 

r_dil_result.xml

 -->

**函數簽名：**`result: function (callback) {}`

此回呼取代處理目的地發佈的預設回呼。

>[!NOTE]
>
>您可以將其他API呼叫鏈結至此方法。

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `callback` | 函數 | JSONP回呼所執行的JavaScript函數。 |

**回應**

Returns the API object of the current [!UICONTROL DIL] instance.

**程式碼範例**

<pre><code>var datalIb= DIL. create({
合作夥伴：'<i>parterName</i>'，
containernSID： <i>containernSID</i> })；

DataAlb. api. properties([<i>123，456，789</i>]). result(json(json){
//Do某物，可能是使用伺服器傳回的JSON資料。 
});.提交();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` is a boolean parameters that controls how [!UICONTROL DIL] mow mays to the [!UICONTROL Data Collection Servers (DCS)] and Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* When `secureDataCollection= true` (default), [!UICONTROL DIL] always makes secure, HTTPS calls.

* When `secureDataCollection= false`, [!UICONTROL DIL] makes either HTTP or HTTPS calls by following the security protocol set by the page.

>[!IMPORTANT]
>
>Set `secureDataCollection= false` if you use visitorAPI.js and [!UICONTROL DIL] on the same page. 請參閱下面的程式碼範例。

<pre><code class="js">var dilintiation= DIL. create({
…
SecureDataCollection：false})；</code>
</pre>

>[!MORE_贊_ this]
>
>* [DIL建立](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` is a boolean true/false參數that controlling how the browser request resources from other domain.

<!-- 

dil-use-cors-only.xml

 -->

**概述**

`useCORSOnly` 預設為false。False表示瀏覽器可以使用CORS或JSONP執行資源檢查。However, [!UICONTROL DIL] always tries to request resources with CORS first. 在不支援 CORS 的舊版瀏覽器上會回復為 JSONP 要求。If you need to force the browser to use CORS only, such as with sites that have high-security requirements, set `useCORSOnly:true`.

**程式碼範例**

<pre><code class="js">var dilintiation= DIL. create({
…
useCorsOnly：true})；</code>
</pre>

>[!IMPORTANT]
>
>* We recommend that you set `useCORSOnly: true` only when you're sure that your site visitors have browsers that support this feature.
>* When `useCORSOnly: true`, [!UICONTROL DIL] will not make ID calls from Internet Explorer version 9 or older.
>



>[!MORE_贊_ this]
>
>* [DIL建立](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Experience Cloud ID服務：useCorsOnly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [Experience Cloud ID 服務的 CORS 支援](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## useImageRequest {#useimagerequest}

Changes the request type to image `<img>` from script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**函數簽名：**`useImageRequest: function () {}`

>[!NOTE]
>
>您可以將其他API呼叫鏈結至此方法。

**回應**

Returns an API object of the current [!UICONTROL DIL] instance.

**程式碼範例**

<pre><code>var datalIb= DIL. create({
合作夥伴：'<i>parterName</i>'，
containernSID： <i>containernSID</i> })；

DataAlb. api. properties([<i>123，456，789</i>]). useImagerRequest(). mit()；</code>
</pre>

