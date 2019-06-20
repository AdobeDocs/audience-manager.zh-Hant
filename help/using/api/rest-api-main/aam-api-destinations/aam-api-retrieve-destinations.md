---
description: 一種GET方法，可傳回指定之destinationID的目的地。
seo-description: 一種GET方法，可傳回指定之destinationID的目的地。
seo-title: 依目的地ID傳回目的地ID
solution: Audience Manager
title: 依目的地ID傳回目的地ID
uuid: abce7426-55a5-4045-93a7-0487652a7189
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Return A Destination by Destination ID {#return-a-destination-by-destination-id}

`GET` 傳回指定 `destinationId`之目標的方法。

<!-- r_get_all_destinations_order_id.xml -->

## 請求

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>To populate the `mappings` field pass in `includeMappings=true` in the URL.

## 回應

```
{
   "destinationType":"PUSH",
   "destinationId":314,
   "dataSourceId":null,
   "pid":1099,
   "name":"sample destination",
   "description":"Turn",
   "startDate":null,
   "endDate":null,
   "status":"active",
   "destinationType":"PUSH",
   "createTime":1281997484000,
   "updateTime":1300752888000,
   "crUID":224,
   "upUID":308,
   "domainRestrictions":"ALL_DOMAINS",
   "tagType":0,
   "serializationEnabled":false,
   "urlFormatString":null,
   "secureUrlFormatString":null,
   "delimiter":null,
   "mappings":null
}
```

## Return All Destinations {#return-all-destinations}

A `GET` method that returns all destinations for the specified partner.

<!-- r_get_all_destinations.xml -->

### 請求

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(選擇性)* 傳入以 `containsSegment=<sid>` 傳回對應至指定區段之所有目的地的陣列。For example, your query could look similar to this: `GET .../destinations/?containsSegment=4321`.
   >
   >
* 請勿傳回完整目標物件。如果需要完全填入物件，請依資料順序取得目的地。


### 選擇性查詢參數

You can use these optional parameters with API methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See [Optional Parameters](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th>
   <th colname="col2" class="entry"> 說明 </th>
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td>
   <td colname="col2"> 依頁碼傳回結果。編號開始於0。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> 設定請求傳回的回應結果數(預設為10)。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> SortBy</code> </td>
   <td colname="col2">Sorts and returns results according to the specified <span class="keyword"> JSON</span> property. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> 遞減遞減</code> </td>
   <td colname="col2"> 排序並傳回結果遞減順序。遞增是預設值。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">根據您要用作搜尋參數的指定字串傳回結果。例如，假設您想尋找所有該項目值欄位中字詞「Test」的所有模型的結果。您的範例請求可能類似於： <p><code> GET</code>Social。 </p> <p>您可以搜尋「get all」方法傳回的任何值。 </p> </td>
  </tr>
 </tbody>
</table>

### 回應

```
[
   {
      "destinationId":364,
      "pid":1099,
      "name":"Test",
      "description":"",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1291345192000,
      "updateTime":1291347561000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   },
   {
      "destinationId":369,
      "pid":1099,
      "name":"sample destination",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1292631706000,
      "updateTime":1292631706000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   }
]
```

## Return a Destination Mapping With the Mapping ID {#return-dest-mapping-id}

A `GET` method that returns an individual destination mapping based on the `mappingId`.

<!-- r_get_destination_trait_data_order.xml -->

### 請求

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`*`<destinationMappingId>`*

### 回應

```
{
"mappingId": 14593,
"traitType": "SEGMENT",
"traitValue": 0,
"destinationId": 314,
"elementName": "sample",
"elementDescription": "Migration Pixel",
"elementStatus": "active",
"createTime": 1281997484000,
"updateTime": 1300752888000,
"crUID": 224,
"upUID": 308,
"sid": 80920,
"startDate": "2010-11-15",
"endDate": null,
"priority": null,
"url": "https://www.adobe.com/send?%ALIAS%",
"secureUrl": "https://www.adobe.com/send?%ALIAS%",
"tagCode": null,
"secureTagCode": null,
"traitAlias": null
}
```

## Return Destination Mappings {#return-dest-mappings}

A `GET` method that returns the mappings for a destination.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>傳回的對應取決於目的地類型和設定。

### 請求

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings`

>[!NOTE]
>
>支援分頁參數。

### 回應

```
{
   "total":354,
   "page":0,
   "pageSize":2,
   "list":[
      {
         "destinationMappingId":14395,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":224,
         "upUID":308,
         "sid":80920,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
      {
         "destinationMappingId":15934,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":242,
         "upUID":803,
         "sid":90820,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
   ]
{
```

## Return All Available Destination Platforms {#return-dest-platforms}

A `GET` method that returns all available device platforms for destinations.

<!-- r_get_dest_platforms.xml -->

### 請求

`GET /destinations/configurations/available-platforms/`

### 回應

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## Return S2S and Bulk S2S Destination Job History {#return-job-history}

`GET` 傳回對外 [!UICONTROL Server-to-Server] ( [!UICONTROL S2S])和大量 [!UICONTROL S2S] 目的地工作歷史記錄資訊的方法。

<!-- r_get_job_history.xml -->

### 請求

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Required query parameters: `startDate` = *&lt;`epochtime`&gt;* and `endDate` = *&lt;`epochtime`&gt;*.

### 回應

```
[
{
      "pushID":34090,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337292466000,
      "endTime":1337292466000,
      "dataFileName":"ftp_655_269_iter_1337229891903.sync",
      "success":true
   },
   {
      "pushID":34104,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337346397000,
      "endTime":1337346397000,
      "dataFileName":"ftp_655_269_iter_1337285714581.sync",
      "success":true
   },
   {
      "pushID":34124,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337396811000,
      "endTime":1337396812000,
      "dataFileName":"ftp_655_269_iter_1337338243600.sync",
      "success":true
   }
]
```
