---
description: 請從此處開始以取得對DCS進行/event呼叫的相關資訊。本節包含有關呼叫語法、參數、格式及請求範例的資訊。
seo-description: 請從此處開始以取得對DCS進行/event呼叫的相關資訊。本節包含有關呼叫語法、參數、格式及請求範例的資訊。
seo-title: 傳送資料至DCS
solution: Audience Manager
title: 傳送資料至DCS
uuid: 024e307d-bfcc-46cf-ac3 a-fc71 df0248 Fe
translation-type: tm+mt
source-git-commit: 9c692ae41a309b4f1d8323a501619c02d2aef6a0

---


# 傳送資料至DCS {#send-data-to-the-dcs}

請從此處開始，以取得 `/event` 有關呼叫的資訊 [!UICONTROL DCS]。本節包含有關呼叫語法、參數、格式及請求範例的資訊。

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 使用此方法傳送資料時，取代預留位置的 [!UICONTROL DCS] 實際值。

## 呼叫語法 {#dcs-call-syntax}

將 `URL` 資料傳送至 [!UICONTROL DCS] 使用下列語法的基本字串。

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>您也可以使用 [!UICONTROL DCS]`POST` 方法將資料傳送至。[DCS API方法說明呼叫語法](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)。

## 呼叫參數 {#dcs-call-parameters}

下表定義簡單 [!UICONTROL DCS] 呼叫的基本元件。

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元件 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> 網域alias. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>此部分的呼叫包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9"><span class="keyword"> Audience Manager指派的網域別名</span> (例如 <code> ，my_ domain. demdex. net</code>)。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目的地網域，永遠為 <code> demdex. net</code>。請參閱<a href="../../../reference/demdex-calls.md">瞭解向 Demdex 網域進行的呼叫</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event？</code> </p> </td> 
   <td colname="col2"> <p>此部分的呼叫： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">將呼叫識別為事件呼叫。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定義URL字串的開頭，其中包含您要傳送至 <span class="wintitle"> DCS</span>的資料。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>索引鍵值配對中的唯一識別碼。 </p> <p>這些索引鍵值配對使用特定首碼來識別要傳送至 <span class="wintitle"> DCS</span>的資料類型。For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>變數值，屬於索引鍵值對中索引鍵所定義的設定。 </p> <p>使用值時： </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">以雙引號括住字串資料(例如 <code> ，年齡=「41到55」</code>)。 </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">您可以在單一值上傳遞多個索引鍵(例如 <i><code>，key</i>=<i>val1，val2，val3</i></code></i>)。 </i></li> 
     </ul> </p> <p>請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> DCS呼叫中的格式化索引鍵值配對</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_ dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_ rtbd= json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_ cb=<i>回呼</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>可選回應參數。 </p> <p> 這些都不需要傳送資料至 <span class="wintitle"> DCS</span>。不過，如果您希望 <span class="wintitle"> DCS</span> 傳回回應，您必須在請求中包含 <code> d_ rtbd= json</code> 。 </p> <p>請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> 「d_ key-Value配對」。</a> </p> </td> 
  </tr>
 </tbody>
</table>

## 範例呼叫 {#dcs-sample-call}

此範例顯示假設公司 [!DNL Acme, Inc.] 傳送資料至 [!UICONTROL DCS][!DNL HTTP] 透過呼叫傳送資料的公司。請注意，此呼叫包含可選參數 `d_dst=1`、 `d_rtbd=json``d_cb=callback`和。這表示 [!DNL Acme] 想要接收呼叫函數的 [!DNL JSON][!UICONTROL DCS] 回應。請記住，這只是範例。請勿剪下並貼上此程式碼。

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## 後續步驟 {#dcs-next-steps}

現在您已熟悉傳送資料的方式 [!UICONTROL DCS]，現在應該瞭解如何從它取得資料並剖析該資訊。請參閱 [從DCS接收資料](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)。

>[!MORE_贊_ this]
>
>* [索引鍵值對說明](../../../reference/key-value-pairs-explained.md)

