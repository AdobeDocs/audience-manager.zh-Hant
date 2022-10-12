---
description: 傳出的即時資料傳輸程式會以一系列JSON物件的形式傳回使用者資料，並以POST方法傳入。
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: 即時傳出資料傳輸
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
exl-id: 12aee831-1a44-4cd6-aeba-7738a584dfe7
source-git-commit: 0245dd11de31c3139c5df5dc78100f0d3935aa2e
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 5%

---

# 即時傳出資料傳輸 {#real-time-outbound-data-transfers}

傳出的即時資料傳輸程式會以一系列方式提供使用者資料 [!DNL JSON] 格式化訊息至目的地平台。

<!-- c_outbound_json.xml -->

## 建議

若要使用此方法，目的地平台必須符合下列需求：

* 它必須提供端點 [!DNL URL] 可以擴展以接收來自Audience Manager的大量報文；
* 它必須接受 [!DNL JSON] 格式(`Content-type: application/json`);
* 它必須接受安全 `HTTPS` 資料傳輸。 [!DNL Audience Manager] 不會透過不安全傳送訊息 `HTTP` 協定。

## 頻率

當使用者符合區段的資格時，此資料傳輸方法可近乎即時傳送資料。 即時訊息只會在使用者上線且Audience Manager邊緣網路可主動看見時傳送。 或者，此方法也可以每24小時傳送批次離線或已上線的資料。

## 批轉移

即時和批次傳輸都會傳送至相同的端點，並使用相同的訊息格式。 啟用批次傳輸後，目的地平台在傳送批次訊息時，訊息量會出現尖峰。 透過即時訊息傳送的許多區段資格會在批次訊息中重複。 批轉移將僅包括自上次交付批後更改的段資格（或取消資格）。

## 比率限制

傳送訊息的吞吐量沒有設定速率限制。 設定速率限制可能會導致資料遺失。

## 必要的回應

依預設，收件者伺服器必須傳回 `200 OK` 表示成功接收的代碼。 其他程式碼則會解譯為失敗。 此回應應在3000毫秒內完成。 因為失敗， [!DNL Audience Manager] 將僅嘗試一次重試。

## 參數

下表定義 [!DNL JSON] 傳送至目的地的資料檔案。

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
   <td colname="col3"> <p>執行要求的時間。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>此ID表示訊息User.DataPartner_UUID屬性中包含的裝置ID類型。 </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID(GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID(IDFA): <code> 20915</code> </li>
     <li>網頁/Cookie ID:依目的地平台而異</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>代表目標平台中的目標帳戶。 此ID源自於目的地平台。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>Audience Manager「目的地」物件的ID。 此ID源自Audience Manager。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>中的使用者總數 <code> POST</code> 請求。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>陣列 </p> </td> 
   <td colname="col3"> <p>用戶對象的陣列。 依預設，每則訊息將包含1到10位使用者，以保持訊息大小最佳。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>此 <span class="keyword"> Audience Manager</span> UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>目的地平台UUID或全域裝置ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> 陣列 </td> 
   <td colname="col3"> 此 <span class="keyword"> Audience Manager</span> 我們看過這個裝置的地區ID。 例如，如果裝置在巴黎（歐洲）有某些活動，則地區ID會是 <code> 6</code>. 請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地區 ID、位置與主機名稱</a>。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>陣列 </p> </td> 
   <td colname="col3"> <p>區段物件的陣列。 對於即時訊息，陣列包含使用者所屬的所有區段。 對於批次訊息，陣列僅包含自上次批次以來的區段變更。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>區段的識別碼。 在大多數情況下，這是Audience Manager產生的區段ID（整數）。 在某些情況下，如果目標平台允許，客戶可以在Audience Manager使用者介面（開啟文字欄位）中定義區段識別碼，這會反映在此屬性中。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>定義區段中使用者的狀態。 接受下列值： </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>:活動（預設） </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>:非使用中、選擇退出或取消細分。 </li> 
    </ul> <p>使用者會取消分段： </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">根據區段規則從區段中移除。 </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">根據區段的 <a href="../../../features/traits/segment-ttl-explained.md"> 存留時間間隔</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">如果過去120天未顯示，則移至非使用中狀態。 </li>
     <li>因隱私權變更請求而移除(即 <span class="keyword"> GDPR</span>)</li>
    </ul> <p>同步至 <span class="keyword"> Audience Manager</span> ID會收到 <code> "Status":"0"</code> 取消分段使用者時的旗標。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>最近驗證使用者區段資格的時間。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 安全性

您可以借由 [簽署HTTP要求](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) 使用私密金鑰或 [!DNL Audience Manager] 通過驗證 [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) 協定。

## 請求

即時請求看起來可能類似下列：

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
