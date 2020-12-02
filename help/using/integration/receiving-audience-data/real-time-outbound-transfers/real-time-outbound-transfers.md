---
description: 對外即時資料傳輸程式會傳回使用者資料，以POST方法傳入的一連串JSON物件形式傳回。
seo-description: 對外即時資料傳輸程式會傳回使用者資料，以POST方法傳入的一連串JSON物件形式傳回。
seo-title: 即時傳出資料傳輸
solution: Audience Manager
title: 即時傳出資料傳輸
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 5%

---


# 即時傳出資料傳輸 {#real-time-outbound-data-transfers}

出站即時資料傳輸過程將用戶資料作為一系列[!DNL JSON]格式化消息發送到目標平台。

<!-- c_outbound_json.xml -->

## 建議

要使用此方法，目標平台必須滿足以下要求：

* 它必須提供端點[!DNL URL]，可縮放以接收來自Audience Manager的大量訊息；
* 它必須接受[!DNL JSON]格式(`Content-type: application/json`)的資料；
* 它必須接受安全的`HTTPS`資料傳輸。 [!DNL Audience Manager] 將不會通過不安全的協定發送 `HTTP` 消息。

## 頻率

當使用者符合區段的資格時，這種資料傳輸方法可近乎即時傳送資料。 即時訊息只會在使用者線上上且主動可見Audience Manager Edge網路時傳送。 （可選）此方法也可以每24小時傳送一批離線或已登入的資料。

## 批轉移

即時傳輸和批次傳輸都會發送到相同的端點，並使用相同的消息格式。 啟用批次傳送後，目標平台會在傳送批次訊息時看到訊息量的尖峰。 許多透過即時訊息傳送的區段資格會在批次訊息中重複。 批轉移將僅包括自上次批交付後更改的段資格（或未資格）。

## 比率限制

對發送的消息的吞吐量沒有設定速率限制。 設定速率限制可能導致資料遺失。

## 必要回應

依預設，收件者伺服器必須傳回`200 OK`程式碼，以指出收件成功。 其他代碼將被解釋為失敗。 此回應預期在3000毫秒內完成。 響應失敗，[!DNL Audience Manager]將僅進行一次重試。

## 參數

下表定義了傳送到目標的[!DNL JSON]資料檔案中的元素。

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
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID(GAID):<code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID(IDFA):<code> 20915</code> </li>
     <li>網頁/Cookie ID:因目的平台而異</li>
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
   <td colname="col3"> <p>Audience Manager「目標」物件的ID。 此ID源自Audience Manager。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p><code> POST</code>請求中的使用者總數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>陣列 </p> </td> 
   <td colname="col3"> <p>一組用戶對象。 依預設，每則訊息會包含1到10位使用者，以保持訊息大小最佳。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> UUID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>目標平台UUID或全域裝置ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> 陣列 </td> 
   <td colname="col3"> 我們看到此裝置的<span class="keyword"> Audience Manager</span>地區ID。 例如，如果裝置在巴黎（歐洲）有某些活動，地區ID會是<code> 6</code>。 請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地區 ID、位置與主機名稱</a>。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>陣列 </p> </td> 
   <td colname="col3"> <p>區段物件的陣列。 對於即時訊息，陣列包含使用者所屬的所有區段。 對於批次消息，陣列只包含自上次批次以來的段更改。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmnent.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>區段的識別碼。 在大多數情況下，這是Audience Manager產生的區段ID（整數）。 在某些情況下，如果目標平台允許，客戶可以在Audience Manager使用者介面（開放文字欄位）中定義區段識別碼，然後會反映在此屬性中。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>定義群體中使用者的狀態。 接受下列值： </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>:作用中（預設） </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>:非活動中、選擇退出或未分段。 </li> 
    </ul> <p>當使用者符合下列條件時，會取消劃分使用者： </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">根據區段規則從區段移除。 </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">根據區段的<a href="../../../features/traits/segment-ttl-explained.md">上線時間間隔</a>，從區段移除。 </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">如果最近120天未看到非活動狀態，則移至此狀態。 </li>
     <li>因隱私權變更要求而移除(即<span class="keyword"> GDPR</span>)</li>
    </ul> <p>與<span class="keyword"> Audience Manager</span> ID同步的所有合作夥伴ID，在取消區隔使用者時，都會收到<code> "Status":"0"</code>標幟。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>使用者區段資格最近驗證的時間。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 安全性

您可以使用私密金鑰來簽署HTTP要求，或透過[!DNL Audience Manager][OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md)[通訊協定來驗證](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md)，以確保即時傳出資料傳輸程式的安全。

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
