---
seo-title: ' 進行伺服器對伺服器DCS API呼叫'
solution: Audience Manager
title: ' 進行伺服器對伺服器DCS API呼叫'
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# 進行伺服器對伺服器DCS API呼叫 {#making-server-to-server-dcs-api-calls}

呼叫需要地區DCS伺服器的主機名稱和使用者ID。 如果您沒有必要的使用者和地區ID，請參 [閱「從DCS回應和](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) /或 [Experience cloud取得使用者ID和地區」](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md)。 一旦您擁有使用者和地區ID後，就可以對DCS進行伺服器對伺服器的呼叫。 請參閱本節以取得語法和範例。

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 當伺服器對伺服器呼叫時，請替代預留位置的實際值 [!UICONTROL DCS]。

## 呼叫語法和範例 {#call-syntax-example}

傳送資料至的基本伺服器對伺服器要求使用 [!UICONTROL DCS] 下列語法。

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

範例呼叫的外觀類似下列範例。

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
   <td colname="col1"> <p><code> <i>域alias</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>此部分呼叫包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">您的網域別名 <span class="keyword"> 由Audience Manager</span> (例如 <i><code> my_domain.demdex.net</code></i>)指派。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目標網域，永遠是 <i><code> demdex.net</code></i>。 請參閱<a href="../../../reference/demdex-calls.md">瞭解向 Demdex 網域進行的呼叫</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS主機名</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>http標頭主機參數，顯示區域 <span class="wintitle"> DCS伺服器的名稱</span> 。 主機名稱會系結至地區ID，因此您在進行這些類型的呼叫前需要此項功能。 請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地區 ID、位置與主機名稱</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>此部分呼叫： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">將呼叫識別為事件呼叫。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定義包含您要傳送至DCS之資料的URL字串的開頭。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience manager使用者ID</i></code> </p> </td> 
   <td colname="col2"> <p>這是唯一的使用者ID金鑰，將 <span class="keyword"> Audience Manager</span> 使用者ID值保存在金鑰值配對中。 </p> <p>如果您 <code><i>要傳入</i></code> Audience Manager使用者ID，請使用d_uuid <span class="keyword"></span> 。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience cloud使用者ID</i></code> </p> </td> 
   <td colname="col2"> <p>這是唯一的使用者ID金鑰，將 <span class="keyword"></span> Experience Cloud使用者ID值保存在金鑰值配對中。 另請參 <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> 閱從ID服務Cookie取得使用者ID</a>。 </p> <p>如果 <i><code> 您要傳入從Experience Cloud</code></i> ID服務擷取的Experience Cloud <span class="keyword"> ID，請使用d_mid</span><span class="keyword"></span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>可選回應參數。 </p> <p> 將資料傳送至DCS時，不需要這些項 <span class="wintitle"> 目</span>。 不過，如果您想 <span class="wintitle"> 讓DCS傳回回應</span> ，您必須在請求中 <i><code> 包含d_rtbd=json</code></i> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例回應 {#sample-response}

請參 [閱從DCS接收資料](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)。
