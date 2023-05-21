---
description: 出站即時資料傳輸進程將用戶資料返回為通過POST方法傳入的一系列JSON對象。
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

出站即時資料傳輸過程將用戶資料作為一系列 [!DNL JSON] 格式化消息到目標平台。

<!-- c_outbound_json.xml -->

## 建議

要使用此方法，目標平台必須滿足以下要求：

* 它必須提供終結點 [!DNL URL] 可以擴展以接收來自Audience Manager的大量消息；
* 它必須接受 [!DNL JSON] 格式`Content-type: application/json`);
* 它必須接受安全 `HTTPS` 資料傳輸。 [!DNL Audience Manager] 不會通過不安全方式發送消息 `HTTP` 協定。

## 頻率

這種資料傳輸方法能夠在用戶滿足資料段要求時，即時地發送資料。 只有在用戶線上且對Audience Manager邊緣網路可主動看到時，才會傳送即時消息。 此外，此方法還可以每24小時發送一批離線或掛接資料。

## 批轉移

即時傳輸和批處理傳輸都發送到相同的端點並使用相同的消息格式。 啟用批傳輸後，目標平台在傳送批消息時將看到消息卷中的尖峰。 通過即時消息發送的許多段資格將在批處理消息中重複。 批轉移將僅包括自上次批交付後更改的段資格（或取消資格）。

## 速率限制

未對已傳送消息的吞吐量設定速率限制。 設定速率限制可能會導致資料丟失。

## 所需響應

預設情況下，收件人伺服器必須返回 `200 OK` 用於指示成功接收的代碼。 其他代碼將被解釋為失敗。 此響應應在3000毫秒內。 為了應對失敗， [!DNL Audience Manager] 將僅進行一次重試。

## 參數

下表定義了 [!DNL JSON] 發送到目標的資料檔案。

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
   <td colname="col2"> <p>日期時間 </p> </td> 
   <td colname="col3"> <p>執行請求的時間。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>User.DataPartner_UUID屬性中指示消息中包含的設備ID類型的ID。 </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID(GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOSID(IDFA): <code> 20915</code> </li>
     <li>Web/Cookie ID:根據目標平台的不同</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>表示目標平台中的目標帳戶。 此ID源自目標平台。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>Audience Manager「目標」對象的ID。 此ID源於Audience Manager。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>中的用戶總數 <code> POST</code> 請求。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>陣列 </p> </td> 
   <td colname="col3"> <p>用戶對象的陣列。 預設情況下，每條消息將包含1到10個用戶，以保持消息大小最佳。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>的 <span class="keyword"> Audience Manager</span> UUID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>目標平台UUID或全局設備ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> 陣列 </td> 
   <td colname="col3"> 的 <span class="keyword"> Audience Manager</span> 我們看到此設備的區域ID。 例如，如果設備在巴黎（歐洲）有活動，則區域ID將為 <code> 6</code>。 請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地區 ID、位置與主機名稱</a>。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>陣列 </p> </td> 
   <td colname="col3"> <p>段對象的陣列。 對於即時消息，陣列包含用戶所屬的所有段。 對於批消息，陣列只包含自上次批以來的段更改。</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>段的標識符。 在大多數情況下，這是由Audience Manager（整數）生成的段ID。 在某些情況下，如果目標平台允許，客戶可以在Audience Manager用戶介面（開放文本欄位）中定義段標識符，然後在此屬性中反映。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>定義段中用戶的狀態。 接受以下值： </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>:活動（預設） </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>:非活動、已選擇退出或未分段。 </li> 
    </ul> <p>當用戶是： </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">根據段規則從段中刪除。 </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">從段中刪除(基於段 <a href="../../../features/traits/segment-ttl-explained.md"> 生存時間間隔</a>。 </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">如果在過去120天中未看到它們，則將其移至非活動狀態。 </li>
     <li>由於隱私更改請求(即 <span class="keyword"> 格德普</span>)</li>
    </ul> <p>同步到的所有合作夥伴ID <span class="keyword"> Audience Manager</span> ID將接收 <code> "Status":"0"</code> 標籤。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>日期時間 </p> </td> 
   <td colname="col3"> <p>最近驗證用戶段資格的時間。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 安全性

您可以通過 [簽名HTTP請求](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) 使用私鑰或 [!DNL Audience Manager] 通過驗證 [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) 協定。

## 請求

即時請求的外觀類似於以下內容：

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
