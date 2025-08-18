---
description: 使用這些RESTful API方法將區段對應至目的地。
seo-description: Map segments to destinations with these RESTful API methods.
seo-title: Map Segments to a Destination
solution: Audience Manager
title: 將區段對應至目的地
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
feature: API
exl-id: 906df6c5-f878-48e6-a804-eb5b4407f304
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 6%

---

# 將區段對應至目的地 {#map-segments-to-a-destination}

使用這些[!DNL RESTful API]方法將區段對應至目的地。

<!-- c_api_map_seg_dest.xml -->

## 支援的目的地型別：僅限URL和Cookie

可用的`POST`方法可讓您僅將區段對應至[!UICONTROL URL]和[!UICONTROL cookie destinations]。 目前，您無法使用這些[!UICONTROL server-to-server destinations]方法將區段對應至[!DNL REST API]。 請改用使用者介面。 不過，相關的目的地`GET`方法可讓您擷取使用者介面中建立的[!UICONTROL server-to-server destinations]相關資訊。

## 將區段對應至非序列化URL目的地 {#map-segment-non-serial}

可讓您將區段對應至非序列`POST`目的地的[!UICONTROL URL]方法。

<!-- r_map_noserial_url.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

除非另有指示，否則所有要求值都是必要的。

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

## 將區段對應至序列化URL目的地 {#map-segment-serial}

可讓您將區段對應到序列化`POST`目的地的[!UICONTROL URL]方法。

<!-- r_map_serialized_url.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### 範例要求

在要求中，`traitAlias`對應於機碼值組中的機碼。 除非另有指示，否則所有要求值都是必要的。

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

## 將區段對應至Cookie目的地：單一金鑰、非序列化 {#map-segment-cookie-noserial}

`POST`方法可讓您將區段對應至單一索引鍵、非序列化[!UICONTROL cookie]目的地。

<!-- r_map_cookie_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

在要求中，`valueAlias`對應於機碼值組中的值。 除非另有指示，否則所有要求值都是必要的。

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

## 將區段對應至Cookie目的地：多索引鍵，非序列化 {#map-segment-cookie-multi-noserial}

`POST`方法可讓您將區段對應到多索引鍵、非序列化[!UICONTROL cookie]目的地。

<!-- r_map_cookie_multikey_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

在要求中，`traitAlias`和`valueAlias`分別設定機碼和機碼值組中的值。 除非另有指示，否則所有要求值都是必要的。

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

## 將區段對應至Cookie目的地：多索引鍵，序列化 {#map-segment-cookie-multi-serial}

`POST`方法，可讓您將區段對應至序列化的多索引鍵[!UICONTROL cookie destination]。

<!-- r_map_cookie_multikey_serialized.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

在要求中，`traitAlias`和`valueAlias`設定機碼和機碼值組中的值。 除非另有指示，否則所有要求值都是必要的。

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

可讓您將區段對應到現有`POST`目的地的[!UICONTROL server-to-server]方法。 但是請注意，您無法使用這些目前可用的[!UICONTROL server-to-server]方法建立[!DNL API]目的地。

<!-- r_map_segment_s2s.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

在要求中，`traitAlias`對應於機碼值組中的機碼。 除非另有指示，否則所有要求值都是必要的。

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

## 大量建立目的地對應 {#bulk-create}

`POST`方法，可讓您傳入[!UICONTROL cookie]或[!UICONTROL URL]目的地對應的陣列。

<!-- r_bulk_create.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### 範例要求

除非另有指示，否則所有要求值都是必要的。

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

成功的回應會傳回已建立對應的陣列。

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

## 將多個區段新增至目的地 {#add-segments-dest}

可讓您將多個區段對應至目的地的`POST`方法。

<!-- r_add_segments_to_destination.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### 範例要求

在陣列中建立多個目的地對應。 除非另有指示，否則所有要求值都是必要的。

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

傳回已建立對應的陣列。

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

## 依目的地ID更新目的地 {#update-dest-data-order}

`PUT`方法，可讓您依`destinationId`更新現有的目的地。

<!-- r_update_destination_data_order_id.xml -->

### 請求

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### 範例要求

除非另有指示，否則所有要求值都是必要的。

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

## 透過對應ID更新對映至目的地 {#update-mapping-dest-id}

`PUT`方法，可讓您依據指定的`mappingId`更新到目的地的對應。

<!-- r_update_destination_trait_data_order_id.xml -->

### 請求

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### 範例要求

除非另有指示，否則所有要求值都是必要的。

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

>[!MORELIKETHIS]
>
>* [目的地](../../../features/destinations/destinations.md)
>* [目的地序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [索引鍵值配對說明](../../../reference/key-value-pairs-explained.md)
