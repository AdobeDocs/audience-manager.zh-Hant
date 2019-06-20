---
description: 使用這些REEST API方法將區段對應至目的地。
seo-description: 使用這些REEST API方法將區段對應至目的地。
seo-title: 將區段對應至目的地
solution: Audience Manager
title: 將區段對應至目的地
uuid: 35358ase-3082-4e86-a6 eb-d77281 af6 d7 e
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Map Segments to a Destination {#map-segments-to-a-destination}

Map segments to destinations with these [!DNL RESTful API] methods.

<!-- c_api_map_seg_dest.xml -->

## 支援的目的地類型：僅限URL和Cookie

The available `POST` methods let you map segments to [!UICONTROL URL] and [!UICONTROL cookie destinations] only. Currently, you cannot map segments to [!UICONTROL server-to-server destinations] with these [!DNL REST API] methods. 請改用使用者介面。However, the related destination `GET` methods let you retrieve information about [!UICONTROL server-to-server destinations] created in the user interface.

>[!MORE_贊_ this]
>
>* [目的地](../../../features/destinations/destinations.md#destination-api-methods)
>* [目的地序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [索引鍵值對說明](../../../reference/key-value-pairs-explained.md)


## Map a Segment to a Non-Serialized URL Destination {#map-segment-non-serial}

`POST` 可讓您將區段對應至非序列 [!UICONTROL URL] 目的地的方法。

<!-- r_map_noserial_url.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

除非另有指示，否則需要所有要求值。

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

## Map a Segment to a Serialized URL Destination {#map-segment-serial}

`POST` 可讓您將區段對應至序列化 [!UICONTROL URL] 目的地的方法。

<!-- r_map_serialized_url.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### 範例要求

In the request, the `traitAlias` corresponds to the key in a key-value pair. 除非另有指示，否則需要所有要求值。

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

## Map a Segment to a Cookie Destination: Single-Key, Non-Serialized {#map-segment-cookie-noserial}

`POST` 可讓您將區段對應至單一索引鍵、非序列化 [!UICONTROL cookie] 目的地的方法。

<!-- r_map_cookie_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

In the request, the `valueAlias` corresponds to the value in a key-value pair. 除非另有指示，否則需要所有要求值。

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

## Map a Segment to a Cookie Destination: Multi-Key, Non-Serialized {#map-segment-cookie-multi-noserial}

`POST` 可讓您將區段對應至多個關鍵、非序列化 [!UICONTROL cookie] 目的地的方法。

<!-- r_map_cookie_multikey_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

In the request, the `traitAlias` and `valueAlias` set the key and the value respectively in a key-value pair. 除非另有指示，否則需要所有要求值。

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

## Map a Segment to a Cookie Destination: Multi-Key, Serialized {#map-segment-cookie-multi-serial}

`POST` 可讓您將區段對應至多索引鍵、序列化 [!UICONTROL cookie destination]的方法。

<!-- r_map_cookie_multikey_serialized.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

In the request, the `traitAlias` and `valueAlias` set the key and the value in a key-value pair. 除非另有指示，否則需要所有要求值。

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

## Map a Segment to a Server-to-Server Destination {#map-segment-s2s}

`POST` 可讓您將區段對應至現有 [!UICONTROL server-to-server] 目的地的方法。Note, however, that you cannot create [!UICONTROL server-to-server] destinations with these currently available [!DNL API] methods.

<!-- r_map_segment_s2s.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

In the request, the `traitAlias` corresponds to the key in a key-value pair. 除非另有指示，否則需要所有要求值。

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

## Bulk Create Destination Mappings {#bulk-create}

`POST` 可讓您傳入或 [!UICONTROL cookie][!UICONTROL URL] 目的地對應的方法。

<!-- r_bulk_create.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### 範例要求

除非另有指示，否則需要所有要求值。

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

成功的回應會傳回已建立映射的陣列。

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

## Add Multiple Segments to a Destination {#add-segments-dest}

A `POST` method that lets you map multiple segments to a destination.

<!-- r_add_segments_to_destination.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### 範例要求

在陣列中建立多個目的地對應。除非另有指示，否則需要所有要求值。

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

傳回已建立映射的陣列。

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

## Update a Destination by Destination ID {#update-dest-data-order}

A `PUT` method that lets you update an existing destination by `destinationId`.

<!-- r_update_destination_data_order_id.xml -->

### 請求

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### 範例要求

除非另有指示，否則需要所有要求值。

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

## Update a Mapping to a Destination by Mapping ID {#update-mapping-dest-id}

A `PUT` method that lets you update a mapping to a destination by the specified `mappingId`.

<!-- r_update_destination_trait_data_order_id.xml -->

### 請求

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### 範例要求

除非另有指示，否則需要所有要求值。

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
