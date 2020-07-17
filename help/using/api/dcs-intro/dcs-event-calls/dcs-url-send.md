---
description: 請從這裡開始，以取得有關對DCS進行/event呼叫的資訊。 本節包含有關呼叫語法、參數、格式和請求範例的資訊。
seo-description: 請從這裡開始，以取得有關對DCS進行/event呼叫的資訊。 本節包含有關呼叫語法、參數、格式和請求範例的資訊。
seo-title: 將資料傳送至 DCS
solution: Audience Manager
title: 將資料傳送至 DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 6%

---


# 將資料傳送至 DCS {#send-data-to-the-dcs}

請從這裡開始，以取得有關 `/event` 呼叫的資訊 [!DNL DCS]。 本節包含有關呼叫語法、參數、格式和請求範例的資訊。

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. 使用此方法傳送資料至預留位置時，請用實際值 [!DNL DCS] 取代預留位置。

## 呼叫語法 {#dcs-call-syntax}

傳送資 `URL` 料至的基本字串使用 [!DNL DCS] 下列語法。

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>您也可以使用方法將 [!DNL DCS] 資料傳送至 `POST` 。 呼叫語法在 [DCS API方法中說明](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)。

## 呼叫參數 {#dcs-call-parameters}

下表定義了簡單調用的基本 [!DNL DCS] 元件。

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
   <td colname="col2"> <p>此部分呼叫包含： </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">您的網域別名 <span class="keyword"> 由Audience Manager</span> (例如 <code> my_domain.demdex.net</code>)指派。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目標域，永遠是 <code> demdex.net</code>。 請參閱<a href="../../../reference/demdex-calls.md">瞭解向 Demdex 網域進行的呼叫</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>此部分呼叫： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">將呼叫識別為事件呼叫。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定義包含您要傳送至DCS之資料的URL字串的開 <span class="wintitle"> 頭</span>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>鍵值對中的唯一標識符。 </p> <p>這些索引鍵值配對使用特定首碼來識別您要傳送至 <span class="wintitle"> DCS的資料類型</span>。 For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>屬於由鍵值對中的鍵定義的集的變數值。 </p> <p>使用值時： </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">將字串資料用雙引號括住(例如 <code> age="41 to 55"</code>)。 </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">您可以在單一值上傳入多個按鍵(例如 <i><code>key</i>=<i>val1,val2,val3</i></code></i>)。 </li> 
     </ul> </p> <p>See <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formatting Key-Value Pairs in DCS Calls</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>可選回應參數。 </p> <p> 將資料傳送至DCS時，不需要這些項 <span class="wintitle"> 目</span>。 不過，如果您想讓 <span class="wintitle"> DCS傳回回回應</span> ，您必須在請求 <code> d_rtbd=json</code> 中加入。 </p> <p>請參 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> 閱定義的d_鍵值對</a>。 </p> </td> 
  </tr>
 </tbody>
</table>

## 範例呼叫 {#dcs-sample-call}

此範例顯示虛構公司 [!DNL Acme, Inc.] 透過呼叫傳送 [!DNL DCS] 資料至 [!DNL HTTP] 該公司。 請注意，此呼叫包含選 `d_dst=1`用 `d_rtbd=json`參數 `d_cb=callback`。 這些指示 [!DNL Acme] 想要從具有回叫 [!DNL JSON] 功能 [!DNL DCS] 的接收回應。 記住，這只是個例子。 請勿剪下並貼上此程式碼。

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## 後續步驟 {#dcs-next-steps}

既然您已熟悉將資料傳送至網站 [!DNL DCS]，現在就該研究如何從網站取得資料並剖析該資訊了。 See [Receive Data From the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [索引鍵值配對說明](../../../reference/key-value-pairs-explained.md)

