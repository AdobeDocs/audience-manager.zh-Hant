---
seo-title: Making Server-to-Server DCS API Calls
solution: Audience Manager
title: 發出伺服器對伺服器DCS API呼叫
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
description: 進行伺服器對伺服器DCS API呼叫時，呼叫語法、範例和引數
exl-id: 977f4dfe-0beb-43c8-b64e-df4042427474
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# 發出伺服器對伺服器DCS API呼叫 {#making-server-to-server-dcs-api-calls}

呼叫需要地區DCS伺服器的主機名稱和使用者ID。 如果您沒有必要的使用者與地區ID，請參閱[從DCS回應取得使用者ID與地區](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md)與/或[Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md)。 擁有使用者和地區ID後，您就可以對DCS進行伺服器對伺服器呼叫。 如需語法和範例，請參閱本節。

>[!NOTE]
>
>在程式碼和範例中，*斜體*&#x200B;代表變數預留位置。 當您對[!DNL DCS]發出伺服器對伺服器呼叫時，請以實值取代預留位置。

## 呼叫語法和範例 {#call-syntax-example}

將資料傳送至[!DNL DCS]的基本伺服器對伺服器要求使用下列語法。

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

範例呼叫看起來類似於以下範例。

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## 呼叫引數 {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> <i>domain alias</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>呼叫的這個部分包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">由<span class="keyword"> Audience Manager</span> （例如<i><code> my_domain.demdex.net</code></i>）指派的網域別名。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目的地網域，一律為<i><code> demdex.net</code></i>。 請參閱<a href="../../../reference/demdex-calls.md">瞭解向Demdex網域</a>進行的呼叫。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>顯示區域<span class="wintitle"> DCS</span>伺服器名稱的http標頭主機引數。 主機名稱會繫結至地區ID，因此您在進行這些型別的呼叫之前需要此ID。 請參閱<a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> DCS地區ID、位置與主機名稱</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>通話的這個部分： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">將呼叫識別為事件呼叫。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定義包含您要傳送至DCS之資料的URL字串開頭。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p>這是唯一使用者ID索引鍵，在索引鍵值配對中保留<span class="keyword">個Audience Manager</span>使用者ID值。 </p> <p>如果您傳入<code><i>d_uuid</i></code> Audience Manager<span class="keyword">使用者識別碼，請使用</span>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>這是唯一使用者ID索引鍵，在索引鍵值配對中保留<span class="keyword">個Experience Cloud</span>使用者ID值。 另請參閱<a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie">從ID服務Cookie</a>取得使用者ID。 </p> <p>如果您傳入從<i><code> d_mid</code></i> Experience Cloud<span class="keyword"> ID服務擷取的</span> Experience Cloud<span class="keyword"> ID，請使用</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>選用的回應引數。 </p> <p> 不需要這些資料即可將資料傳送至<span class="wintitle"> DCS</span>。 不過，若您希望<span class="wintitle"> DCS</span>傳回回應，您必須在要求中包含<i><code> d_rtbd=json</code></i>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例回應 {#sample-response}

請參閱[從DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)接收資料。
