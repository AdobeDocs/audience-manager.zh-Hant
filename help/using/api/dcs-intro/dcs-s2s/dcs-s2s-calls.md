---
seo-title: 建立伺服器至伺服器DCS API呼叫
solution: Audience Manager
title: 建立伺服器至伺服器DCS API呼叫
uuid: bdfe3430-e27 f-4a5 c-88d9-ae164 d28 f601
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# 建立伺服器至伺服器DCS API呼叫 {#making-server-to-server-dcs-api-calls}

呼叫需要區域DCS伺服器的主機名稱和使用者ID。如果您沒有必要的使用者和地區ID，請參閱 [從DCS回應](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) 及/或 [Experience Cloud取得使用者ID和地區](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md)。當您擁有使用者和地區ID後，就可以對DCS進行伺服器對伺服器呼叫。請參閱本節以瞭解語法和範例。

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 在伺服器呼叫伺服器呼叫時，取代預留位置的實際值 [!UICONTROL DCS]。

## 呼叫語法和範例 {#call-syntax-example}

基本伺服器對伺服器的要求會傳送資料至 [!UICONTROL DCS] 下方顯示的語法。

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

範例呼叫看起來類似下列範例。

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## 呼叫參數 {#call-parameters}

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
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目的地網域，永遠為 <i><code> demdex. net</code></i>。請參閱<a href="../../../reference/demdex-calls.md">瞭解向 Demdex 網域進行的呼叫</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>DCS主機名稱</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>顯示區域 <span class="wintitle"> DCS</span> 伺服器名稱的http標題主機參數。主機名稱會系結至地區ID，這就是您在發出這些呼叫類型之前所需要的原因。請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地區 ID、位置與主機名稱</a>。 </p> </td> 
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
   <td colname="col2"> <p>此為唯一值配對 <span class="keyword"> 中Audience Manager</span> 使用者ID值的唯一使用者ID金鑰。 </p> <p><code><i></i></code> 如果您要傳入 <span class="keyword"> Audience Manager</span> 使用者ID，請使用d_ uuid。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ mid=<i>Experience Cloud使用者ID</i></code> </p> </td> 
   <td colname="col2"> <p>這是在索引鍵值配對中保留 <span class="keyword"> Experience Cloud</span> 使用者ID值的唯一使用者ID金鑰。另請參閱 <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> ID服務Cookie</a>中的使用者ID。 </p> <p>如果您要傳入從Experience <i><code> Cloud</code></i> ID服務擷取的 <span class="keyword"> Experience Cloud</span> <span class="keyword"> ID，請使用</span> d_ mid。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_ dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_ rtbd= json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_ cb=<i>回呼</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>可選回應參數。 </p> <p> 這些都不需要傳送資料至 <span class="wintitle"> DCS</span>。不過，如果您希望 <span class="wintitle"> DCS</span> 傳回回應，您必須在請求中包含 <i><code> d_ rtbd= json</code></i> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例回應 {#sample-response}

請參閱 [從DCS接收資料](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)。
