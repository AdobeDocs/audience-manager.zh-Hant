---
description: 一種GET方法，可傳回指定destinationId的目的地。
seo-description: 一種GET方法，可傳回指定destinationId的目的地。
seo-title: 依目標ID傳回目標
solution: Audience Manager
title: 依目標ID傳回目標
uuid: abce7426-55a5-4045-93a7-0487652a7189
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# 依目標ID傳回目標 {#return-a-destination-by-destination-id}

返回 `GET` 指定目標的方法 `destinationId`。

<!-- r_get_all_destinations_order_id.xml -->

## 請求

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>若要填入 `mappings` URL中的欄 `includeMappings=true` 位傳遞。

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

返回 `GET` 指定夥伴的所有目標的方法。

<!-- r_get_all_destinations.xml -->

### 請求

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *（可選）* ，請傳入 `containsSegment=<sid>` 以傳回映射至指定區段之所有目的地的陣列。 例如，您的查詢看起來可能類似下列： `GET .../destinations/?containsSegment=4321`。
   >
   >
* 不返回完整目標對象。 如果需要完全填入的物件，請依資料順序取得目的地。


### 可選查詢參數

您可以將這些可選參數與API方法搭配使用， *以傳回* 物件的所有屬性。 將查詢傳入請求字串中時，請在請求字串中設定這些選項 [!DNL API]。 請參 [閱可選參數](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)。

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
   <td colname="col2"> 依頁碼傳回結果。 編號從0開始。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> 設定請求傳回的回應結果數目（預設為10）。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">根據指定的 <span class="keyword"> JSON屬性排序並傳回結果</span> 。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> 降序</code> </td>
   <td colname="col2"> 以遞減順序排序和傳回結果。 預設為遞增。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> 搜尋</code> </td>
   <td colname="col2">根據您要用作搜尋參數的指定字串傳回結果。 例如，假設您想要在該項目的任何值欄位中，尋找具有「測試」字詞的所有模型的結果。 您的範例要求可能如下所示： <p><code> 取得https://api.demdex.com/v1/models/?search=Test</code>。 </p> <p>您可以搜尋「get all」方法傳回的任何值。 </p> </td>
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

## 傳回具有映射ID的目標映射 {#return-dest-mapping-id}

一種 `GET` 基於返回單個目標映射的方法 `mappingId`。

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

返回 `GET` 目標映射的方法。

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>傳回的對應是目標類型和配置特定的。

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

一種 `GET` 返回目標所有可用設備平台的方法。

<!-- r_get_dest_platforms.xml -->

### 請求

`GET /destinations/configurations/available-platforms/`

### 回應

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## 傳回S2S和大量S2S目標作業歷史記錄 {#return-job-history}

一種 `GET` 返回出站( [!UICONTROL Server-to-Server] )和大量目標作業 [!UICONTROL S2S][!UICONTROL S2S] 歷史資訊的方法。

<!-- r_get_job_history.xml -->

### 請求

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

所需查詢參數： `startDate` = *&lt;`epochtime`&gt;和* = `endDate` &lt; *`epochtime`*&gt;

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
