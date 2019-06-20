---
seo-title: 建立伺服器至伺服器DCS API呼叫
solution: Audience Manager
title: 建立伺服器至伺服器DCS API呼叫
uuid: bdfe3430-e27 f-4a5 c-88d9-ae164 d28 f601
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Making Server-to-Server DCS API Calls {#making-server-to-server-dcs-api-calls}

呼叫需要區域DCS伺服器的主機名稱和使用者ID。If you do not have the required user and region IDs, see [Get User IDs and Regions From a DCS Response](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) and/or [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). 當您擁有使用者和地區ID後，就可以對DCS進行伺服器對伺服器呼叫。請參閱本節以瞭解語法和範例。

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitute a real value for the placeholder when you server-to-server calls to the [!UICONTROL DCS].

## Call Syntax and Example {#call-syntax-example}

A basic server-to-server request that sends data to the [!UICONTROL DCS] uses the syntax shown below.

<pre><code>「主機：<i>網域別名</i>. demdex. net」https://DCS<i>主機name.demdex.net/event?d_rtbd=json&amp;d_jsonv=1&amp;d_uuid=user</i><i>ID</i>。</code>
</pre>

範例呼叫看起來類似下列範例。

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Call Parameters {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code><i>網域alias</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>此部分的呼叫包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9"><span class="keyword"> Audience Manager指派的網域別名</span> (例如 <i><code> ，my_ domain. demdex. net</code></i>)。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">The destination domain, which is always <i><code> demdex.net</code></i>. 請參閱<a href="../../../reference/demdex-calls.md">瞭解向 Demdex 網域進行的呼叫</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>DCS主機名稱</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>The http header host parameter which shows the name of the regional <span class="wintitle"> DCS</span> server. 主機名稱會系結至地區ID，這就是您在發出這些呼叫類型之前所需要的原因。請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地區 ID、位置與主機名稱</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event？</code> </p> </td> 
   <td colname="col2"> <p>此部分的呼叫： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">將呼叫識別為事件呼叫。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定義URL字串的開頭，其中包含您要傳送至DCS的資料。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ uuid= <i>Audience Manager使用者ID</i></code> </p> </td> 
   <td colname="col2"> <p>This is the unique user ID key that holds the <span class="keyword"> Audience Manager</span> user ID value in a key-value pair. </p> <p><code><i></i></code> 如果您要傳入 <span class="keyword"> Audience Manager</span> 使用者ID，請使用d_ uuid。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ mid=<i>Experience Cloud使用者ID</i></code> </p> </td> 
   <td colname="col2"> <p>This is the unique user ID key that holds the <span class="keyword"> Experience Cloud</span> user ID value in a key-value pair. See also <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Get the User ID from the ID Service Cookie</a>. </p> <p>Use <i><code> d_mid</code></i> if you're passing in a <span class="keyword"> Experience Cloud</span> ID captured from the <span class="keyword"> Experience Cloud</span> ID service. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_ dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_ rtbd= json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_ cb=<i>回呼</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>可選回應參數。 </p> <p> None of these are required to send data to the <span class="wintitle"> DCS</span>. However, if you want the <span class="wintitle"> DCS</span> to return a response, you must include <i><code> d_rtbd=json</code></i> in your request. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例回應 {#sample-response}

See [Receive Data From the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
