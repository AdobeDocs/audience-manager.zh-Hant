---
description: 使用這些REST風格的API方法將區段對應至目標。
seo-description: 使用這些REST風格的API方法將區段對應至目標。
seo-title: 將區段對應至目標
solution: Audience Manager
title: 將區段對應至目標
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
translation-type: tm+mt
source-git-commit: 8ab675cac67a0e6353cf5fd14944c7c5cc849e5a

---


# 將區段對應至目標 {#map-segments-to-a-destination}

使用這些方法將區段對應至 [!DNL RESTful API] 目標。

<!-- c_api_map_seg_dest.xml -->

## 支援的目標類型：僅限URL和Cookie

可用的 `POST` 方法可讓您將區段對應至 [!UICONTROL URL] 且僅 [!UICONTROL cookie destinations] 限。 目前，您無法使用這些方法將 [!UICONTROL server-to-server destinations] 區段對 [!DNL REST API] 應至。 請改用使用者介面。 不過，相關的目標方 `GET` 法可讓您擷取在使用者介 [!UICONTROL server-to-server destinations] 面中建立的相關資訊。

>[!MORE_LIKE_THIS]
>
>* [目的地](../../../features/destinations/destinations.md)
>* [目標序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [說明的鍵值對](../../../reference/key-value-pairs-explained.md)


## 將區段對應至無序號的URL目的地 {#map-segment-non-serial}

一種 `POST` 方法，可讓您將區段對應至非序列目的 [!UICONTROL URL] 地。

<!-- r_map_noserial_url.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

除非另有指示，否則所有請求值都為必要值。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-07-04"
}
```

### 回應

```
{
   "mappingId":65334,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4033,
   "elementName":"Sample games",
   "elementDescription":"Sample games pixel",
   "elementStatus":"active",
   "createTime":1338940094000,
   "updateTime":1338940094000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"https://adobe.com",
   "secureUrl":null,
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":null
}
```

## 將區段對應至序號的URL目的地 {#map-segment-serial}

一種 `POST` 方法，可讓您將區段對應至序列化 [!UICONTROL URL] 目的地。

<!-- r_map_serialized_url.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### 範例要求

在請求中， `traitAlias` 對應於鍵值對中的鍵。 除非另有指示，否則所有請求值都為必要值。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### 回應

```
{
   "mappingId":65335,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4034,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940401000,
   "updateTime":1338940401000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"123",
   "secureUrl":"123",
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":"123"
}
```

## 將區段對應至Cookie目標：單鍵、無序號 {#map-segment-cookie-noserial}

一種 `POST` 方法，可讓您將區段對應至單鍵、無序號的 [!UICONTROL cookie] 目的地。

<!-- r_map_cookie_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

在請求中， `valueAlias` 與鍵值對中的值相對應。 除非另有指示，否則所有請求值都為必要值。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "valueAlias":"123"
}
```

### 回應

```
{
   "destinationMappingId":65336,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4035,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940704000,
   "updateTime":1338940704000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":null,
   "valueAlias":"123"
}
```

## 將區段對應至Cookie目標：多鍵、無序號 {#map-segment-cookie-multi-noserial}

一種 `POST` 方法，可讓您將區段對應至多鍵、無序號的 [!UICONTROL cookie] 目的地。

<!-- r_map_cookie_multikey_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

在請求中， `traitAlias` 和 `valueAlias` 分別在鍵值對中設定鍵和值。 除非另有指示，否則所有請求值都為必要值。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### 回應

```
{
   "mappingId":65338,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4037,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941092000,
   "updateTime":1338941092000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## 將區段對應至Cookie目標：多鍵，序列化 {#map-segment-cookie-multi-serial}

可 `POST` 讓您將區段對應至多鍵序號的方法 [!UICONTROL cookie destination]。

<!-- r_map_cookie_multikey_serialized.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

在請求中， `traitAlias` 和 `valueAlias` 在鍵值對中設定鍵和值。 除非另有指示，否則所有請求值都為必要值。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### 回應

```
{
   "destinationMappingId":65340,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4038,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941273000,
   "updateTime":1338941273000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":2,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## 將區段對應至伺服器對伺服器目的地 {#map-segment-s2s}

一種 `POST` 方法，可讓您將區段對應至現有目 [!UICONTROL server-to-server] 的地。 但請注意，您無法使用這些目 [!UICONTROL server-to-server] 前可用的方法來建立目 [!DNL API] 標。

<!-- r_map_segment_s2s.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

在請求中， `traitAlias` 對應於鍵值對中的鍵。 除非另有指示，否則所有請求值都為必要值。

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### 回應

```
{
   "destinationMappingId":65341,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":566,
   "elementName":"Sample",
   "elementDescription":"",
   "elementStatus":"active",
   "createTime":1338942118000,
   "updateTime":1338942118000,
   "crUID":308,
   "upUID":308,
   "sid":84326,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "traitAlias":"123"
}
```

## 批量建立目標映射 {#bulk-create}

一種 `POST` 可讓您傳入陣列或目標映射 [!UICONTROL cookie] 的 [!UICONTROL URL] 方法。

<!-- r_bulk_create.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### 範例要求

除非另有指示，否則所有請求值都為必要值。

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### 回應

成功的響應返回已建立映射的陣列。

```
[
    {
        "mappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "mappingId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "orderId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## 新增多個區段至目標 {#add-segments-dest}

一種 `POST` 方法，可讓您將多個區段對應至目標。

<!-- r_add_segments_to_destination.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### 範例要求

在陣列中建立多個目標映射。 除非另有指示，否則所有請求值都為必要值。

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### 回應

返回已建立映射的陣列。

```
[
    {
        "destinationMappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "traitToDataOrderId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## 依目標ID更新目標 {#update-dest-data-order}

一種 `PUT` 方法，可讓您依據更新現有的目的地 `destinationId`。

<!-- r_update_destination_data_order_id.xml -->

### 請求

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### 範例要求

除非另有指示，否則所有請求值都為必要值。

```
{
   "name":"Updated URL Destination (not serialized)",
   "description":"new description",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### 回應

```
{
    "destinationType": "PUSH",
    "destinationId": 780,
    "dataSourceId": null,
    "pid": 1099,
    "name": "Updated URL Destination (not serialized)",
    "description": "new description",
    "startDate": null,
    "endDate": null,
    "status": 1,
    "createTime": 1348851790000,
    "updateTime": 1353372029000,
    "crUID": 884,
    "upUID": 1065,
    "domainRestrictions":"all_domains",
    "tagType": 0,
    "serializationEnabled": false,
    "urlFormatString": null,
    "secureUrlFormatString": null,
    "delimiter": null,
    "mappings": null
}
```

## 通過映射ID更新映射到目標 {#update-mapping-dest-id}

一種 `PUT` 方法，可讓您依指定更新目標的對應 `mappingId`。

<!-- r_update_destination_trait_data_order_id.xml -->

### 請求

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### 範例要求

除非另有指示，否則所有請求值都為必要值。

```
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
}
```

### 回應

```
{
    "mappingId": 103453,
    "traitType": "SEGMENT",
    "traitValue": 0,
    "destinationId": 780,
    "elementName": "sample",
    "elementDescription": "test",
    "elementStatus": "active",
    "createTime": 1353373005000,
    "updateTime": 1353373005000,
    "crUID": 1065,
    "upUID": 1065,
    "sid": 105123,
    "startDate": "2012-11-19",
    "endDate": null,
    "priority": null,
    "url": "https://www.adobe.com/send?%ALIAS%",
    "secureUrl": null,
    "tagCode": null,
    "secureTagCode": null,
    "traitAlias": null
}
```
