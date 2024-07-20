---
description: 從這裡開始，瞭解如何對DCS進行/event呼叫。 本節包含呼叫語法、引數、格式和請求範例的相關資訊。
seo-description: Start here for information about making /event calls to the DCS. This section includes information about call syntax, parameters, formatting, and a request example.
seo-title: Send Data to the DCS
solution: Audience Manager
title: 將資料傳送至DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
exl-id: 8a6798c3-aafd-48c8-acd7-a0e29e04dc8e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 1%

---

# 將資料傳送至DCS {#send-data-to-the-dcs}

從這裡開始，瞭解如何對[!DNL DCS]進行`/event`呼叫。 本節包含呼叫語法、引數、格式和請求範例的相關資訊。

>[!NOTE]
>
>在程式碼和範例中，*斜體*&#x200B;代表變數預留位置。 使用此方法傳送資料至[!DNL DCS]時，請以實值取代預留位置。

## 呼叫語法 {#dcs-call-syntax}

將資料傳送至[!DNL DCS]的基本`URL`字串使用下列語法。

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>您也可以使用`POST`方法將資料傳送至[!DNL DCS]。 呼叫語法在[DCS API方法](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)中說明。

## 呼叫引數 {#dcs-call-parameters}

下表定義簡單[!DNL DCS]呼叫的基本元件。

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
   <td colname="col2"> <p>呼叫的這個部分包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">您的網域別名已由<span class="keyword">Audience Manager</span> （例如<code> my_domain.demdex.net</code>）指派。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目的地網域，一律為<code> demdex.net</code>。 請參閱<a href="../../../reference/demdex-calls.md">瞭解向Demdex網域</a>進行的呼叫。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>通話的這個部分： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">將呼叫識別為事件呼叫。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定義包含您要傳送至<span class="wintitle"> DCS</span>之資料的URL字串開頭。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>機碼值組中的唯一識別碼。 </p> <p>這些機碼值組會使用特定的前置詞來識別您傳送至<span class="wintitle"> DCS</span>的資料型別。 如需詳細資訊，請參閱<a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> DCS API呼叫的支援屬性</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>屬於索引鍵/值配對中索引鍵所定義之集合的變數值。 </p> <p>使用值時： </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">將字串資料以雙引號括住（例如，<code> age="41 to 55"</code>）。 </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">您可以在單一值上傳入多個金鑰（例如，<i><code>key</i>=<i>val1,val2,val3</i></code></i>）。 </li> 
     </ul> </p> <p>請參閱<a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md">格式化DCS呼叫</a>中的索引鍵值配對。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>選用的回應引數。 </p> <p> 不需要這些資料即可將資料傳送至<span class="wintitle"> DCS</span>。 不過，若您希望<span class="wintitle"> DCS</span>傳回回應，您必須在要求中包含<code> d_rtbd=json</code>。 </p> <p>請參閱定義的<a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_機碼值組</a>。 </p> </td> 
  </tr>
 </tbody>
</table>

## 呼叫範例 {#dcs-sample-call}

此範例顯示虛構的公司[!DNL Acme, Inc.]透過[!DNL HTTP]呼叫傳送資料給[!DNL DCS]。 請注意，此呼叫包含選用引數`d_dst=1`、`d_rtbd=json`和`d_cb=callback`。 這些表示[!DNL Acme]想要從[!DNL DCS]接收回呼函式的[!DNL JSON]回應。 請記住，這只是個範例。 請勿剪下並貼上此程式碼。

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## 後續步驟 {#dcs-next-steps}

現在您已熟悉傳送資料至[!DNL DCS]，您可以開始瞭解如何從其中取回資料，並剖析該資訊。 請參閱[從DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)接收資料。

>[!MORELIKETHIS]
>
>* [索引鍵值配對說明](../../../reference/key-value-pairs-explained.md)
