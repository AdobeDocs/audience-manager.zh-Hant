---
description: 從此處開始，瞭解有關對DCS進行/event調用的資訊。 本節包括有關調用語法、參數、格式和請求示例的資訊。
seo-description: Start here for information about making /event calls to the DCS. This section includes information about call syntax, parameters, formatting, and a request example.
seo-title: Send Data to the DCS
solution: Audience Manager
title: 將資料傳送至 DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
exl-id: 8a6798c3-aafd-48c8-acd7-a0e29e04dc8e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 6%

---

# 將資料傳送至 DCS {#send-data-to-the-dcs}

從此處開始獲取有關製作 `/event` 呼叫 [!DNL DCS]。 本節包括有關調用語法、參數、格式和請求示例的資訊。

>[!NOTE]
>
>在代碼和示例中， *斜體* 表示變數佔位符。 將資料發送到 [!DNL DCS] 用這種方法。

## 調用語法 {#dcs-call-syntax}

基本 `URL` 將資料發送到 [!DNL DCS] 使用下面所示的語法。

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>您還可以將資料發送到 [!DNL DCS] 使用 `POST` 的雙曲餘切值。 調用語法如中所述 [DCS API方法](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)。

## 調用參數 {#dcs-call-parameters}

下表定義了簡單元件的基本元件 [!DNL DCS] 呼叫。

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">您分配的域別名由 <span class="keyword"> Audience Manager</span> (例如， <code> my_domain.demdex.net</code>)。 </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">目標域，始終 <code> demdex.net</code>。 請參閱<a href="../../../reference/demdex-calls.md">瞭解向 Demdex 網域進行的呼叫</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>此部分呼叫： </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">將呼叫標識為事件呼叫。 </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">定義包含要發送到的資料的URL字串的開頭 <span class="wintitle"> DCS</span>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>鍵值對中的唯一標識符。 </p> <p>這些鍵值對使用特定前置詞來標識要發送到的資料的類型 <span class="wintitle"> DCS</span>。 有關詳細資訊，請參見 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> DCS API調用的支援屬性</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>屬於由鍵值對中的鍵定義的集的變數值。 </p> <p>使用值時： </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">將字串資料用雙引號括起來(例如， <code> age="41 to 55"</code>)。 </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">可以在單個值上傳遞多個鍵(例如， <i><code>key</i>=<i>val1,val2,val3</i></code></i>)。 </li> 
     </ul> </p> <p>請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> 在DCS調用中設定鍵值對的格式</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>可選響應參數。 </p> <p> 所有這些都不需要將資料發送到 <span class="wintitle"> DCS</span>。 但是，如果你想 <span class="wintitle"> DCS</span> 要返迴響應，必須包括 <code> d_rtbd=json</code> 請你。 </p> <p>請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> 定義d_鍵值對</a>。 </p> </td> 
  </tr>
 </tbody>
</table>

## 示例調用 {#dcs-sample-call}

此示例向虛構公司展示 [!DNL Acme, Inc.] 向 [!DNL DCS] 通過 [!DNL HTTP] 呼叫。 請注意，此調用包括可選參數 `d_dst=1`。 `d_rtbd=json`, `d_cb=callback`。 這表明 [!DNL Acme] 想要 [!DNL JSON] 來自 [!DNL DCS] 具有回叫功能。 記住，這只是個例子。 不要剪切並貼上此代碼。

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## 後續步驟 {#dcs-next-steps}

現在您已熟悉將資料發送到 [!DNL DCS]現在是時候研究如何從資料中獲取資料並分析這些資訊了。 請參閱 [從DCS接收資料](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md)。

>[!MORELIKETHIS]
>
>* [索引鍵值配對說明](../../../reference/key-value-pairs-explained.md)

