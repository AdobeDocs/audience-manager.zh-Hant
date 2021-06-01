---
description: 請從這裡開始，取得對DCS發出/event呼叫的相關資訊。 本節包含呼叫語法、參數、格式和要求範例的相關資訊。
seo-description: 請從這裡開始，取得對DCS發出/event呼叫的相關資訊。 本節包含呼叫語法、參數、格式和要求範例的相關資訊。
seo-title: 將資料傳送至 DCS
solution: Audience Manager
title: 將資料傳送至 DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
exl-id: 8a6798c3-aafd-48c8-acd7-a0e29e04dc8e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 6%

---

# 將資料傳送至 DCS {#send-data-to-the-dcs}

請從這裡開始，了解有關對[!DNL DCS]進行`/event`調用的資訊。 本節包含呼叫語法、參數、格式和要求範例的相關資訊。

>[!NOTE]
>
>在程式碼和範例中，*斜體*&#x200B;代表變數預留位置。 使用此方法將資料發送到[!DNL DCS]時，用實際值替換佔位符。

## 呼叫語法{#dcs-call-syntax}

將資料傳送至[!DNL DCS]的基本`URL`字串使用下列語法。

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>您也可以使用`POST`方法將資料傳送至[!DNL DCS]。 [DCS API方法](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)中會說明呼叫語法。

## 呼叫參數{#dcs-call-parameters}

下表定義了簡單[!DNL DCS]調用的基本元件。

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元件 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>此部分的呼叫包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">由<span class="keyword">Audience Manager</span>指派的域別名（例如<code> my_domain.demdex.net</code>）。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目標域，始終為<code> demdex.net</code>。 請參閱<a href="../../../reference/demdex-calls.md">瞭解向 Demdex 網域進行的呼叫</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>呼叫的這個部分： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">將呼叫識別為事件呼叫。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定義URL字串的開頭，該字串包含您要傳送至<span class="wintitle"> DCS</span>的資料。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>機碼值組中的唯一識別碼。 </p> <p>這些機碼值組會使用特定首碼來識別您要傳送至<span class="wintitle"> DCS</span>的資料類型。 如需詳細資訊，請參閱<a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> DCS API呼叫的支援屬性</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>屬於機碼值組中由機碼定義之集的變數值。 </p> <p>使用值時： </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">以雙引號括住字串資料（例如<code> age="41 to 55"</code>）。 </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">您可以在單一值上傳遞多個索引鍵（例如<i><code>key</i>=<i>val1,val2,val3</i></code></i>）。 </li> 
     </ul> </p> <p>請參閱<a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md">在DCS呼叫</a>中格式化索引鍵值配對。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>選用的回應參數。 </p> <p> 無需上述任何條件，即可將資料傳送至<span class="wintitle"> DCS</span>。 不過，如果您想要<span class="wintitle"> DCS</span>傳回回應，您必須在請求中加入<code> d_rtbd=json</code>。 </p> <p>請參閱<a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_已定義的鍵值對</a>。 </p> </td> 
  </tr>
 </tbody>
</table>

## 呼叫範例{#dcs-sample-call}

此範例顯示虛構公司[!DNL Acme, Inc.]透過[!DNL HTTP]呼叫傳送資料至[!DNL DCS]。 請注意，此呼叫包含選用參數`d_dst=1`、`d_rtbd=json`和`d_cb=callback`。 這表示[!DNL Acme]想要從[!DNL DCS]接收具有回呼函式的[!DNL JSON]回應。 記住，這只是一個例子。 請勿剪下並貼上此程式碼。

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## 後續步驟 {#dcs-next-steps}

現在您已熟悉將資料傳送至[!DNL DCS]，是時候研究如何從中取回資料並剖析該資訊了。 請參閱[從DCS接收資料](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)。

>[!MORELIKETHIS]
>
>* [索引鍵值配對說明](../../../reference/key-value-pairs-explained.md)

