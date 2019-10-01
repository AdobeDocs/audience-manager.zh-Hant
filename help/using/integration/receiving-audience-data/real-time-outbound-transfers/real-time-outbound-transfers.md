---
description: 對外即時資料傳輸程式會傳回使用者資料，以POST方法傳入的一連串JSON物件形式傳回。
seo-description: 對外即時資料傳輸程式會傳回使用者資料，以POST方法傳入的一連串JSON物件形式傳回。
seo-title: 即時出站資料傳輸
solution: Audience Manager
title: 即時出站資料傳輸
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: b76e905ec890dbe8270177d142dddb351438b039

---


# 即時出站資料傳輸 {#real-time-outbound-data-transfers}

出站即時資料傳輸過程將用戶資料作為一系列格式化消 [!DNL JSON] 息發送到目標平台。

<!-- c_outbound_json.xml -->

## 建議

要使用此方法，目標平台必須滿足以下要求：

* 它必須提供端點， [!DNL URL] 可縮放以接收來自Audience manager的大量訊息；
* 它必須接受格式( [!DNL JSON] )的數`Content-type: application/json`據；
* 它必須接受安全的 `HTTPS` 資料傳輸。 [!DNL Audience Manager] 將不會通過不安全協定發送 `HTTP` 消息。

## 頻率

當使用者符合區段的資格時，這種資料傳輸方法可近乎即時傳送資料。 即時訊息只會在使用者線上上且主動可見Audience Manager edge網路時傳送。 （可選）此方法也可以每24小時傳送一批離線或已登入的資料。

## 批轉移

即時傳輸和批次傳輸都會發送到相同的端點，並使用相同的消息格式。 啟用批次傳送後，目標平台會在傳送批次訊息時看到訊息量的尖峰。 許多透過即時訊息傳送的區段資格會在批次訊息中重複。 Batch transfers will include only the segment qualifications (or un-qualifications) that have changed since the last batch was delivered.

## Rate Limits

There are no rate limits set on the throughput of delievered messages. Setting rate limits could lead to data loss.

## Required Responses

By default, the recipient server must return the  code to indicate successful receipt. `200 OK`Other codes will be interpreted as failures. This response is expected within 3000 milliseconds. In response to a failure,  will make one retry attempt only.[!DNL Audience Manager]

## 參數

下表定義傳回資料檔案中的 [!DNL JSON] 元素。

<table id="table_68475F9D01ED4A44B5909234114AEDE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 資料類型 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>ProcessTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>執行請求的時間。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>User.DataPartner_UUID屬性中指示消息中包含的設備ID類型的ID。 </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID(GAID):二零九一 <code> 四年</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID(IDFA):二零九 <code> 一五年</code> </li>
     <li>網頁/Cookie ID:因目的地平台而異</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>代表目標平台中的目標帳戶。 此ID源自目標平台。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>Audience Manager「目標」物件的ID。 This ID originates from Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>Total number of users in the  POST request.<code></code> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>使用者</i></code> </td> 
   <td colname="col2"> <p>陣列 </p> </td> 
   <td colname="col3"> <p>An array of user objects. By default, each message will contain between 1 and 10 users, to keep the message size optimal. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>The  Audience Manager UUID.<span class="keyword"></span> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>目標平台UUID或全域裝置ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> 陣列 </td> 
   <td colname="col3"> 我 <span class="keyword"> 們看過此裝置的Audience Manager</span> 地區ID。 例如，如果裝置在巴黎（歐洲）有某些活動，地區ID會是 <code> 6</code>。 請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地區 ID、位置與主機名稱</a>。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>區段</i></code> </td> 
   <td colname="col2"> <p>陣列 </p> </td> 
   <td colname="col3"> <p>區段物件的陣列。 對於即時訊息，陣列包含使用者所屬的所有區段。 對於批次消息，陣列只包含自上次批次以來的段更改。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>區段的識別碼。 在大多數情況下，這是Audience manager產生的區段ID（整數）。 In some cases, if the destination platform allows, customers can define the segment identifier in the Audience Manager UI (open text field), which would then reflect in this property. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>Defines the status of a user in the segment. Accepts the following values: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>:作用中（預設） </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>:非活動中、選擇退出或未分段。 </li> 
    </ul> <p>當使用者符合下列條件時，會取消劃分使用者： </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">根據區段規則從區段移除。 </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">根據區段的上線時間間隔， <a href="../../../features/traits/segment-ttl-explained.md"> 從區段中移除</a>。 </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">如果最近120天未看到非活動狀態，則移至非活動狀態。 </li>
     <li>因隱私權變更要求而移除(即[!DNL GDPR])</li>
    </ul> <p>當使用者解除區隔時，所有同步至 <span class="keyword"> Audience Manager</span> ID的合作夥伴ID都會收到 <code></code> 「狀態」:「0」旗標。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>使用者區段資格最近驗證的時間。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 安全性

您可以使用私密金鑰簽署 [HTTP請求](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) ，或透過 [!DNL Audience Manager][](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) OAuth 2.0通訊協定進行驗證，以確保即時傳出資料傳輸程式的安全。

## 請求

即時請求看起來可類似下列：

```js
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{  
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         },
         {
            "Segment_ID": "12176",
            "Status": "0",  
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   },
   {
   "AAM_UUID": "0578240750487542456854736923319946899715232",
   "DataPartner_UUID": "848457757347734",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "10329",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
         },
         {
            "Segment_ID": "23954",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
        }]
    }]
}
```
