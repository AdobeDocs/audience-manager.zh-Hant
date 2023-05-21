---
seo-title: Making Server-to-Server DCS API Calls
solution: Audience Manager
title: 發出伺服器對伺服器 DCS API 呼叫
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
description: 調用伺服器到伺服器DCS API調用時調用語法、示例和參數
exl-id: 977f4dfe-0beb-43c8-b64e-df4042427474
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 8%

---

# 發出伺服器對伺服器 DCS API 呼叫 {#making-server-to-server-dcs-api-calls}

調用需要區域DCS伺服器的主機名和用戶ID。 如果您沒有所需的用戶和區域ID，請參閱 [從DCS響應獲取用戶ID和區域](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) 和/或 [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md)。 用戶和區域ID一旦具有，就可以對DCS進行伺服器到伺服器的調用。 有關語法和示例，請參閱本節。

>[!NOTE]
>
>在代碼和示例中， *斜體* 表示變數佔位符。 在伺服器到伺服器調用時，替換佔位符的實際值 [!DNL DCS]。

## 調用語法和示例 {#call-syntax-example}

將資料發送到 [!DNL DCS] 使用下面所示的語法。

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

示例調用與以下示例類似。

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## 調用參數 {#call-parameters}

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
   <td colname="col2"> <p>此部分呼叫包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">您分配的域別名由 <span class="keyword"> Audience Manager</span> (例如， <i><code> my_domain.demdex.net</code></i>)。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目標域，始終 <i><code> demdex.net</code></i>。 請參閱<a href="../../../reference/demdex-calls.md">瞭解向 Demdex 網域進行的呼叫</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>顯示區域名稱的http頭主機參數 <span class="wintitle"> DCS</span> 伺服器。 主機名與區域ID相關聯，因此在進行這些類型的呼叫之前需要此名稱。 請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地區 ID、位置與主機名稱</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>此部分呼叫： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">將呼叫標識為事件呼叫。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定義包含要發送到DCS的資料的URL字串的開頭。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p>這是唯一的用戶ID密鑰，用於保存 <span class="keyword"> Audience Manager</span> 鍵值對中的用戶ID值。 </p> <p>使用 <code><i>d_uuid</i></code> 如果你路過 <span class="keyword"> Audience Manager</span> 用戶ID。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>這是唯一的用戶ID密鑰，用於保存 <span class="keyword"> Experience Cloud</span> 鍵值對中的用戶ID值。 另請參閱 <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> 從ID服務Cookie獲取用戶ID</a>。 </p> <p>使用 <i><code> d_mid</code></i> 如果你在路上 <span class="keyword"> Experience Cloud</span> 從 <span class="keyword"> Experience Cloud</span> ID服務。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>可選響應參數。 </p> <p> 所有這些都不需要將資料發送到 <span class="wintitle"> DCS</span>。 但是，如果你想 <span class="wintitle"> DCS</span> 要返迴響應，必須包括 <i><code> d_rtbd=json</code></i> 請你。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例回應 {#sample-response}

請參閱 [從DCS接收資料](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)。
