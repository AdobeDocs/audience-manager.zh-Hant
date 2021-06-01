---
description: 一種GET方法，可傳回指定destinationId的目的地。
seo-description: 一種GET方法，可傳回指定destinationId的目的地。
seo-title: 依目的地 ID 傳回目的地
solution: Audience Manager
title: 依目的地 ID 傳回目的地
uuid: abce7426-55a5-4045-93a7-0487652a7189
feature: API
exl-id: c0850e71-7830-4635-b773-e9a28ab5bd68
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 9%

---

# 依目的地 ID 傳回目的地 {#return-a-destination-by-destination-id}

`GET`方法，用於返回指定`destinationId`的目標。

<!-- r_get_all_destinations_order_id.xml -->

## 請求

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>若要填入URL中`includeMappings=true`中的`mappings`欄位傳遞。

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

## 返回所有目標{#return-all-destinations}

`GET`方法可傳回指定合作夥伴的所有目的地。

<!-- r_get_all_destinations.xml -->

### 請求

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *（選用）* 傳入 `containsSegment=<sid>` 以傳回對應至指定區段之所有目的地的陣列。例如，您的查詢看起來可能類似以下：`GET .../destinations/?containsSegment=4321`。
   >
   >
* 不會傳回完整目的地物件。 如果需要完全填入的物件，請依資料順序取得目的地。


### 選用的查詢參數

您可以將這些選用參數與傳回物件&#x200B;*all*&#x200B;屬性的API方法搭配使用。 將查詢傳遞至[!DNL API]時，請在要求字串中設定這些選項。 請參閱[選用參數](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)。

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
   <td colname="col2"> 按頁碼返回結果。 編號從0開始。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> 設定請求傳回的回應結果數（預設為10）。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">根據指定的<span class="keyword"> JSON</span>屬性對結果進行排序和返回。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 按降序排序和返回結果。 預設為遞增。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">根據您要用作搜索參數的指定字串返回結果。 例如，假設您想在該項目的任何值欄位中，找到所有具有「Test」字詞之模型的結果。 您的範例要求可能如下所示： <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>實施流量分類。 </p> <p>您可以搜尋「get all」方法傳回的任何值。 </p> </td>
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

## 返回映射ID {#return-dest-mapping-id}的目標映射

根據`mappingId`傳回個別目的地對應的`GET`方法。

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

## 返回目標映射{#return-dest-mappings}

`GET`方法，可返回目標的映射。

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>傳回的對應是目標類型和設定的特定對象。

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

## 返回所有可用的目標平台{#return-dest-platforms}

一種`GET`方法，可傳回目的地的所有可用裝置平台。

<!-- r_get_dest_platforms.xml -->

### 請求

`GET /destinations/configurations/available-platforms/`

### 回應

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## 返回S2S和批量S2S目標作業歷史記錄{#return-job-history}

傳回傳出[!UICONTROL Server-to-Server]([!UICONTROL S2S])和大量[!UICONTROL S2S]目標作業歷史記錄資訊的`GET`方法。

<!-- r_get_job_history.xml -->

### 請求

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

必要的查詢參數：`startDate` = *`epochtime`>*&#x200B;和`endDate` = *`epochtime`>*。

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
