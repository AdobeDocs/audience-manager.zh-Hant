---
description: 返回指定destinationId的目標的GET方法。
seo-description: A GET method that returns the destination for the specified destinationId.
seo-title: Return A Destination by Destination ID
solution: Audience Manager
title: 依目的地 ID 傳回目的地
uuid: abce7426-55a5-4045-93a7-0487652a7189
feature: API
exl-id: c0850e71-7830-4635-b773-e9a28ab5bd68
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 7%

---

# 依目的地 ID 傳回目的地 {#return-a-destination-by-destination-id}

A `GET` 返回指定目標的方法 `destinationId`。

<!-- r_get_all_destinations_order_id.xml -->

## 請求

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>填充 `mappings` 欄位傳遞 `includeMappings=true` 的子菜單。

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

## 返回所有目標 {#return-all-destinations}

A `GET` 返回指定夥伴的所有目標的方法。

<!-- r_get_all_destinations.xml -->

### 請求

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *（可選）* 傳入 `containsSegment=<sid>` 返回映射到指定段的所有目標的陣列。 例如，您的查詢可能如下所示： `GET .../destinations/?containsSegment=4321`。
>
>* 不返回完整目標對象。 如果需要完全填充的對象，按資料順序獲取目標。


### 可選查詢參數

可以將這些可選參數與返回的API方法一起使用 *全部* 對象的屬性。 將查詢傳遞到 [!DNL API]。 請參閱 [可選參數](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)。

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
   <td colname="col2"> 設定請求返回的響應結果數（預設值為10）。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">根據指定的 <span class="keyword"> JSON</span> 屬性。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 按降序排序並返回結果。 升序為預設值。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">根據要用作搜索參數的指定字串返回結果。 例如，假設您要查找所有模型的結果，這些模型在該項目的任何值欄位中都使用「Test」一詞。 您的示例請求可能如下所示： <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>實施流量分類。 </p> <p>可以搜索「get all」方法返回的任何值。 </p> </td>
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

## 返回具有映射ID的目標映射 {#return-dest-mapping-id}

A `GET` 基於返回單個目標映射的方法 `mappingId`。

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

## 返回目標映射 {#return-dest-mappings}

A `GET` 返回目標映射的方法。

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>返回的映射特定於目標類型和配置。

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

## 返回所有可用的目標平台 {#return-dest-platforms}

A `GET` 返回目標的所有可用設備平台的方法。

<!-- r_get_dest_platforms.xml -->

### 請求

`GET /destinations/configurations/available-platforms/`

### 回應

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## 返回S2S和批量S2S目標作業歷史記錄 {#return-job-history}

A `GET` 方法返回出站 [!UICONTROL Server-to-Server] ( [!UICONTROL S2S])和批量 [!UICONTROL S2S] 目標作業歷史記錄資訊。

<!-- r_get_job_history.xml -->

### 請求

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

必需的查詢參數： `startDate` = *&lt;`epochtime`>* 和 `endDate` = *&lt;`epochtime`>*。

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
