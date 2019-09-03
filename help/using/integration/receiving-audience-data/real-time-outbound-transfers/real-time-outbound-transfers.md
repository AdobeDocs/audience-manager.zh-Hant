---
description: 對外即時資料傳輸程序會傳回使用者資料，作為使用POST方法傳入的一系列JSON物件。
seo-description: 對外即時資料傳輸程序會傳回使用者資料，作為使用POST方法傳入的一系列JSON物件。
seo-title: 即時對外資料傳輸
solution: Audience Manager
title: 即時對外資料傳輸
uuid: 1895e818-7ab8-459-a920-4b0 a4 c8 b83 d
translation-type: tm+mt
source-git-commit: 425315a0a6aa739a90e34deb270ac21df9b88d31

---


# 即時對外資料傳輸 {#real-time-outbound-data-transfers}

對外即時資料傳輸程序會將使用者資料傳回以方法傳入的一系列 [!DNL JSON] 物件 `POST` 。

<!-- c_outbound_json.xml -->

## 建議

若要使用此方法，建議您的資料合作夥伴：

* 接受 [!DNL JSON] 格式的資料。
* 提供傳回資料 `POST` 的呼叫URL。
* 接受安全 `HTTPS` 的資料傳輸。[!DNL Audience Manager] 不會以不安全 `HTTP` 的通訊協定傳送此檔案。

## 頻率

此資料傳輸方法可在使用者符合區段資格時即時傳送資料。此外，此方法可每隔24小時傳送離線或已上線的資料批次。

## 必要回應

根據預設，收件者伺服器必須傳回 `200 OK` 程式碼，指出成功接收。其他代碼將被解讀為失敗。此回應預計在3000毫秒內。為了回應失敗， [!DNL Audience Manager] 只會嘗試重試。

## 參數

下表定義傳回 [!DNL JSON] 資料檔案中的元素。

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
   <td colname="col3"> <p>執行請求時的時間。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ DPID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>指出檔案是否包含Android或iOS ID的ID。使用下列ID值： </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID(GAID)： <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID(IDFA)： <code> 20915</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ ID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>您要傳送資料的系統使用的用戶端ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ Target_ ID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>目的地合作夥伴指派給您的ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ count</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p><code> POST</code> 請求中的使用者總數。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>使用者</i></code> </td> 
   <td colname="col2"> <p>陣列 </p> </td> 
   <td colname="col3"> <p>使用者物件的陣列。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ UUID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> UUID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DataAssection_ UUID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>資料合作夥伴UUID。如果您的資料合作夥伴沒有UUID，請保留空白。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_地區</i></code> </td> 
   <td colname="col2"> 陣列 </td> 
   <td colname="col3"> <span class="keyword"> 我們看過此裝置的Audience Manager</span> 地區ID。例如，如果裝置在巴黎(歐洲)有一些活動，地區ID會是 <code> 6</code>。請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地區 ID、位置與主機名稱</a>。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>區段</i></code> </td> 
   <td colname="col2"> <p>陣列 </p> </td> 
   <td colname="col3"> <p>區段物件的陣列。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>區段_ ID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>區段ID目的地對應。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>狀態</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>定義區段中使用者的狀態。接受下列項目： </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code></code>1：活動(預設) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code></code>0：非活動中、選擇退出或未分段。 </li> 
    </ul> <p>使用者在進行區段時不會分段： </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">根據區段規則從區段中移除。 </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">根據區段 <a href="../../../features/traits/segment-ttl-explained.md"> 的即時間隔，從區段移除</a>。 </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">如果最近120天尚未查看到非活動狀態，則將其移至非活動狀態。 </li> 
    </ul> <p>所有與 <span class="keyword"> Audience Manager</span> ID同步的合作夥伴ID都會收到「 <code> 狀態」：「0」</code> 標幟。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>最新區段資格的時間。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 安全性

您可以使用私密金鑰 [或透過](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md)[!DNL Audience Manager][OAuth2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) 通訊協定驗證HTTP要求，以確保即時傳出資料傳輸程序。

## 程式碼範例

即時資料回應看起來類似下列：

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
