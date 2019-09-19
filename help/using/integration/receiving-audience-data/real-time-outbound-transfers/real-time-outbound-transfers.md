---
description: 對外即時資料傳輸程式會傳回使用者資料，以POST方法傳入的一連串JSON物件形式傳回。
seo-description: 對外即時資料傳輸程式會傳回使用者資料，以POST方法傳入的一連串JSON物件形式傳回。
seo-title: 即時出站資料傳輸
solution: Audience Manager
title: 即時出站資料傳輸
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: 425315a0a6aa739a90e34deb270ac21df9b88d31

---


# 即時出站資料傳輸 {#real-time-outbound-data-transfers}

出站即時資料傳輸過程以通過方法傳入的一系列對 [!DNL JSON] 像的形式返回用戶 `POST` 資料。

<!-- c_outbound_json.xml -->

## 建議

若要使用此方法，建議您的資料合作夥伴：

* 接受格式 [!DNL JSON] 的資料。
* 提供可供呼叫用來傳回資料 `POST` 的URL。
* 接受安全的 `HTTPS` 資料傳輸。 [!DNL Audience Manager] 將不會以不安全的通訊協定傳送此 `HTTP` 檔案。

## 頻率

當使用者符合區段的資格時，這種資料傳輸方法可近乎即時傳送資料。 此外，此方法可每24小時傳送一批離線或已登入的資料。

## 必要回應

依預設，收件者伺服器必須傳回程式碼， `200 OK` 以指出成功收件。 其他代碼將被解釋為失敗。 此回應預期在3000毫秒內完成。 響應失敗，將只 [!DNL Audience Manager] 進行1次重試。

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
   <td colname="col3"> <p>指示檔案是包含Android或iOS ID的ID。 使用下列ID值： </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID(GAID):二零九一 <code> 四年</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID(IDFA):二零九 <code> 一五年</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>您要傳送資料至的系統所使用的用戶端ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>目標合作夥伴指派給您的ID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>POST請求中的使用 <code> 者總數</code> 。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>使用者</i></code> </td> 
   <td colname="col2"> <p>陣列 </p> </td> 
   <td colname="col3"> <p>一組用戶對象。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>Audience Manager <span class="keyword"></span> UUID。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>資料合作夥伴UUID。 如果您的資料合作夥伴沒有UUID，請留空。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Regions</i></code> </td> 
   <td colname="col2"> 陣列 </td> 
   <td colname="col3"> 我 <span class="keyword"> 們看過此裝置的Audience Manager</span> 地區ID。 例如，如果裝置在巴黎（歐洲）有某些活動，地區ID會是 <code> 6</code>。 請參閱 <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 地區 ID、位置與主機名稱</a>。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>區段</i></code> </td> 
   <td colname="col2"> <p>陣列 </p> </td> 
   <td colname="col3"> <p>區段物件的陣列。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>區段ID</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>區段ID目標對應。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>狀態</i></code> </td> 
   <td colname="col2"> <p>整數 </p> </td> 
   <td colname="col3"> <p>定義群體中使用者的狀態。 接受下列條件： </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>:作用中（預設） </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>:非活動中、選擇退出或未分段。 </li> 
    </ul> <p>當使用者符合下列條件時，會取消劃分使用者： </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">根據區段規則從區段移除。 </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">根據區段的上線時間間隔， <a href="../../../features/traits/segment-ttl-explained.md"> 從區段中移除</a>。 </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">如果最近120天未看到非活動狀態，則移至非活動狀態。 </li> 
    </ul> <p>當使用者解除區隔時，所有同步至 <span class="keyword"> Audience Manager</span> ID的合作夥伴ID都會收到 <code></code> 「狀態」:「0」旗標。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>最近區段資格的時間。</p> </td> 
  </tr> 
 </tbody> 
</table>

## 安全性

您可以使用私密金鑰簽署 [HTTP請求](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) ，或透過 [!DNL Audience Manager][](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) OAuth 2.0通訊協定進行驗證，以確保即時傳出資料傳輸程式的安全。

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
