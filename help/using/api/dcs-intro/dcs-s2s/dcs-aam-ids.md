---
description: 本節說明如何剖析DCS回應，以擷取對DCS進行即時呼叫所需的訪客和地區ID。
seo-description: 本節說明如何剖析DCS回應，以擷取對DCS進行即時呼叫所需的訪客和地區ID。
seo-title: 從DCS回應取得使用者ID和地區
solution: Audience Manager
title: 從DCS回應取得使用者ID和地區
uuid: 0803604-1b26-4d40-8e94-7d0884048683
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions From a DCS Response {#get-user-ids-and-regions-from-a-dcs-response}

This section describes how to parse a [!UICONTROL DCS] response to retrieve the visitor and region IDs required to make real-time calls to the [!UICONTROL DCS].

## User and Region IDs {#user-region-ids}

[!UICONTROL DCS] 回應包含關於網站訪客的資料。You need the visitor and region ID before you can make server-to-server calls to the [!UICONTROL DCS].

* 使用者ID是識別和關聯特定訪客資料的必要項目。
* The region ID is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. 請參閱 [DCS 地區 ID、位置與主機名稱](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

這些參數如下所述。*斜體的程式碼* 代表變數預留位置。

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 資料類型 </th> 
   <th colname="col3" class="entry"> 範例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>「uuid」： <i>使用者ID</i></code></span> </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p> <code> 「uuid」：「123456789」</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>「cs_ region」：<i>地區ID</i></code> </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p> <code> 「cs_ region」：9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例回應 {#sample-response}

This simple response shows the `UUID` and region `ID`. 請注意，這僅是範例資料。您的記錄檔可能會比較長且更複雜。

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 後續步驟 {#next-steps}

Once you have the user ID and regional server name, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
