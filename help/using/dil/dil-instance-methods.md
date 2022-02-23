---
description: 實例級DILAPI允許您以寫程式方式建立和使用Audience Manager對象。 實例級方法增強了由類級方法建立的API功能。
keywords: 建立特徵；建立特徵
seo-description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
seo-title: Instance-level DIL Methods
solution: Audience Manager
title: 例項層級 DIL 方法
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
exl-id: 0342439d-708e-461c-b155-a3ee423f5437
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1075'
ht-degree: 14%

---

# 例項層級 DIL 方法{#instance-level-dil-methods}

實例級 [!UICONTROL DIL] API允許您以寫程式方式建立和使用Audience Manager對象。 實例級方法增強了由類級方法建立的API功能。

## 實例級DIL方法入門 {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

使用實例級時 [!UICONTROL DIL] API:

* Access需要合作夥伴名稱和容器命名空間ID(NSID)。 請與Audience Manager客戶經理聯繫以獲取此資訊。
* 替換任何示例 *斜體* API文檔中的文本，其值、ID或您所使用的方法所需的其他變數。

<!-- 

c_instance_start.xml

 -->

## 信號 {#signals}

將客戶和平台級映射添加到掛起請求的查詢字串。

<!-- 

r_dil_signals.xml

 -->

**函式簽名：** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* 可以將其他API調用連結到此方法。
>* 如果Adobe Experience CloudJavaScript庫在頁面上， `submit()` 在發送請求之前等待雲設定cookie。


**保留請求密鑰**

以下請求密鑰是保留的，無法由此方法覆蓋：

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `obj` | 物件 | 表示平台級映射的鍵值對的對象。 參數將字串和陣列作為對象中的屬性值。 |
| `prefix` | 字串 | 選填。每個對象鍵前置詞的字串值（替換原始鍵）。 |
| `return` | DIL.api | 返回當前DIL實例的API對象。 |

**回應**

返回當前的API對象 [!UICONTROL DIL] 實例。

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

將SID添加到掛起請求的查詢字串。

<!-- 

r_dil_traits.xml

 -->

**函式簽名：** `traits:function (sids){}`

>[!NOTE]
>
>可以將其他API調用連結到此方法。

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `sids` | 陣列 | 陣列中的特徵段ID。 |

**回應**

返回當前的API對象 [!UICONTROL DIL] 實例。

**程式碼範例**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## 日誌 {#logs}

將資料添加到掛起請求中的日誌檔案。

<!-- 

r_dil_logs.xml

 -->

**函式簽名：** `logs: function {key1:value1, key2:value2}`

**回應**

返回當前的API對象 [!UICONTROL DIL] 實例。

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

將所有待定資料提交到Audience Manager [!UICONTROL DIL] 實例。

<!-- 

r_dil_submit.xml

 -->

**函式簽名：** `submit: function () {}`

>[!NOTE]
>
>可以將其他API調用連結到此方法。 還有， [!UICONTROL DIL] 將編碼資料寫入目標cookie。 例如，空格編碼為 `%20` 分號，如 `%3B`。

**回應**

返回當前的API對象 [!UICONTROL DIL] 實例。

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

## 後結果 {#afterresult}

在預設目標發佈回調後執行的函式。

<!-- 

r_dil_after_result.xml

 -->

**函式簽名：** `afterResult: function (fn) {}`

>[!NOTE]
>
>可以將其他API調用連結到此方法。

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `fn` | 函數 | 處理JSON後要執行的函式由處理目標發佈的預設回調處理。 |

**回應**

返回當前的API對象 [!UICONTROL DIL] 實例。

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

## 清除資料 {#cleardata}

清除掛起請求中的所有資料。

<!-- 

r_dil_clear_data.xml

 -->

**函式簽名：** `clearData: function () {}`

>[!NOTE]
>
>可以將其他API調用連結到此方法。

**回應**

返回當前的API對象 [!UICONTROL DIL] 實例。

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

## 自定義查詢參數 {#customqueryparams}

將資料收集伺服器未顯式定義的自定義查詢參數添加到掛起請求。

<!-- 

r_dil_custom_query_params.xml

 -->

**函式簽名：** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>可以將其他API調用連結到此方法。

**保留請求密鑰**

以下請求密鑰是保留的，無法由此方法覆蓋：

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**回應**

返回當前DIL實例的API對象。

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

返回的容器NSID的值 [!UICONTROL DIL] 實例。 用於調試和故障排除。

<!-- 

r_dil_get_container_nsid.xml

 -->

**函式簽名：** `dil.api.getContainerNSID: function () {}`

**程式碼範例**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## get事件日誌 {#geteventlog}

返回按時間順序排序的事件日誌資料作為字串陣列。 用於調試和故障排除。

<!-- 

r_dil_get_event_log.xml

 -->

**函式簽名：** `dil.api.getEventLog: function () {}`

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

返回的合作夥伴名稱 [!UICONTROL DIL] 實例。 用於調試和故障排除。

<!-- 

r_dil_get_partner.xml

 -->

**函式簽名：** `dil.api.getPartner: function () {}`

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

返回當前狀態 [!UICONTROL DIL] 實例。 用於調試和故障排除。

<!-- 

r_dil_get_state.xml

 -->

**函式簽名：** `dil.api.getState: function () {}`

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

## id同步 {#idsync}

由兩個功能組成，使資料夥伴在它們之間交換和同步用戶ID，並進行Audience Manager。

<!-- 

r_dil_idsync.xml

 -->

**函式簽名：**

使用 [!UICONTROL DIL] 版本2.10和3.1或更高版本。

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
   <td colname="col2"> <p>不同資料合作夥伴和Audience Manager。 例如，合作夥伴x將使用此功能將用戶ID與合作夥伴y同步，然後將其發送到Audience Manager。 </p> <p> <p><b>重要提示：</b>  此方法已棄用。 請使用 <code> idSyncByURL </code> Adobe Experience Platform標識服務實例的方法。 </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>當您已經知道用戶ID並想將其發送到Audience Manager。 </p> <p> <p><b>重要提示：</b>  此方法已棄用。 請使用 <code> idSyncByDataSource </code> Adobe Experience Platform標識服務實例的方法。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync元素**

`idSync` 可包括以下內容：

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

* **`%TIMESTAMP%`:** 生成時間戳（毫秒）。 用於快取破產。
* **`%DID%`:** 插入用戶的Audience ManagerID。
* **`%HTTP_PROTO%`:** 設定頁協定( `http` 或 `https`)。

**回應**

兩個函式都返回 `Successfully queued` 成功。 如果失敗則傳回錯誤訊息字串。

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

將回調（接收JSON）添加到掛起請求。

<!-- 

r_dil_result.xml

 -->

**函式簽名：** `result: function (callback) {}`

此回調將替換處理目標發佈的預設回調。

>[!NOTE]
>
>可以將其他API調用連結到此方法。

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `callback` | 函數 | 由JSONP回調執行的JavaScript函式。 |

**回應**

返回當前的API對象 [!UICONTROL DIL] 實例。

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

`secureDataCollection` 是一個布爾參數，它控制 [!UICONTROL DIL] 打電話給 [!UICONTROL Data Collection Servers (DCS)] 和阿卡邁。

<!-- 

dil-secure-data-collection.xml

 -->

* 當 `secureDataCollection= true` （預設）, [!UICONTROL DIL] 總是進行安全的HTTPS呼叫。

* 當 `secureDataCollection= false`。 [!UICONTROL DIL] 按照該頁設定的安全協定進行HTTP或HTTPS調用。

>[!IMPORTANT]
>
>設定 `secureDataCollection= false` 如果您使用visitorAPI.js和 [!UICONTROL DIL] 同一頁。 請參閱下面的代碼示例。

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     secureDataCollection: false 
});
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` 是布爾true/false參數，用於控制瀏覽器如何從其他域請求資源。

<!-- 

dil-use-cors-only.xml

 -->

**概述**

`useCORSOnly` 預設為false。 False表示瀏覽器可以使用CORS或JSONP執行資源檢查。 但是， [!UICONTROL DIL] 總是嘗試先使用CORS請求資源。 在不支援 CORS 的舊版瀏覽器上會回復為 JSONP 要求。如果需要強制瀏覽器僅使用CORS，例如對具有高安全性要求的站點，請設定 `useCORSOnly:true`。

**程式碼範例**

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     useCORSOnly: true 
});
</code></pre>

>[!IMPORTANT]
>
>* 我們建議你 `useCORSOnly: true` 只有當您的站點訪問者擁有支援此功能的瀏覽器時。
>* 當 `useCORSOnly: true`。 [!UICONTROL DIL] 不會從Internet Explorer版本9或更舊版本進行ID調用。
>


## useImageRequest {#useimagerequest}

將請求類型更改為映像 `<img>` 從指令碼 `<src>`。

<!-- 

r_dil_use_image_request.xml

 -->

**函式簽名：** `useImageRequest: function () {}`

>[!NOTE]
>
>可以將其他API調用連結到此方法。

**回應**

返回當前的API對象 [!UICONTROL DIL] 實例。

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
>* [Adobe Experience Platform身份服務中的同步功能](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/idsync.html)
>* [DIL 建立](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Adobe Experience Platform身份服務：僅使用CORSOnly](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [Adobe Experience Platform身份服務中的CORS支援](https://experienceleague.adobe.com/docs/id-service/using/reference/cors.html)

