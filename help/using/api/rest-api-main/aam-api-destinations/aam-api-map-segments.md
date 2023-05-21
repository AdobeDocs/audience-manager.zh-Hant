---
description: 使用這些REST風格的API方法將段映射到目標。
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
ht-degree: 10%

---

# 將區段對應至目的地 {#map-segments-to-a-destination}

將段映射到具有這些 [!DNL RESTful API] 的雙曲餘切值。

<!-- c_api_map_seg_dest.xml -->

## 支援的目標類型：僅URL和Cookie

可用 `POST` 方法允許將段映射到 [!UICONTROL URL] 和 [!UICONTROL cookie destinations] 只是。 當前，無法將段映射到 [!UICONTROL server-to-server destinations] 和 [!DNL REST API] 的雙曲餘切值。 改用用戶介面。 但是，相關目的地 `GET` 方法允許檢索有關 [!UICONTROL server-to-server destinations] 在用戶介面中建立。

## 將段映射到非序列化URL目標 {#map-segment-non-serial}

A `POST` 用於將段映射到非串列 [!UICONTROL URL] 目標。

<!-- r_map_noserial_url.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

除非另有指明，否則所有請求值都是必需的。

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

## 將段映射到序列化URL目標 {#map-segment-serial}

A `POST` 用於將段映射到序列化的方法 [!UICONTROL URL] 目標。

<!-- r_map_serialized_url.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### 範例要求

在請求中， `traitAlias` 對應於鍵值對中的鍵。 除非另有指明，否則所有請求值都是必需的。

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

## 將段映射到Cookie目標：單鍵、非序列化 {#map-segment-cookie-noserial}

A `POST` 用於將段映射到單鍵、非序列化的方法 [!UICONTROL cookie] 目標。

<!-- r_map_cookie_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

在請求中， `valueAlias` 對應於鍵值對中的值。 除非另有指明，否則所有請求值都是必需的。

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

## 將段映射到Cookie目標：多鍵、非序列化 {#map-segment-cookie-multi-noserial}

A `POST` 用於將段映射到多鍵、非序列化的方法 [!UICONTROL cookie] 目標。

<!-- r_map_cookie_multikey_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

在請求中， `traitAlias` 和 `valueAlias` 在key-value對中分別設定鍵和值。 除非另有指明，否則所有請求值都是必需的。

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

## 將段映射到Cookie目標：多鍵，序列化 {#map-segment-cookie-multi-serial}

A `POST` 用於將段映射到多鍵、序列化的 [!UICONTROL cookie destination]。

<!-- r_map_cookie_multikey_serialized.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

在請求中， `traitAlias` 和 `valueAlias` 設定鍵值對中的鍵和值。 除非另有指明，否則所有請求值都是必需的。

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

## 將段映射到伺服器到伺服器目標 {#map-segment-s2s}

A `POST` 用於將段映射到現有段的方法 [!UICONTROL server-to-server] 目標。 但請注意，您無法建立 [!UICONTROL server-to-server] 這些目標當前可用 [!DNL API] 的雙曲餘切值。

<!-- r_map_segment_s2s.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### 範例要求

在請求中， `traitAlias` 對應於鍵值對中的鍵。 除非另有指明，否則所有請求值都是必需的。

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

A `POST` 一種方法，它允許您通過 [!UICONTROL cookie] 或 [!UICONTROL URL] 目標映射。

<!-- r_bulk_create.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### 範例要求

除非另有指明，否則所有請求值都是必需的。

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

成功的響應將返回建立的映射陣列。

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

## 將多個段添加到目標 {#add-segments-dest}

A `POST` 用於將多個段映射到目標的方法。

<!-- r_add_segments_to_destination.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### 範例要求

在陣列中建立多個目標映射。 除非另有指明，否則所有請求值都是必需的。

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

## 按目標ID更新目標 {#update-dest-data-order}

A `PUT` 用於更新現有目標的方法 `destinationId`。

<!-- r_update_destination_data_order_id.xml -->

### 請求

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### 範例要求

除非另有指明，否則所有請求值都是必需的。

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

## 通過映射ID更新到目標的映射 {#update-mapping-dest-id}

A `PUT` 用於通過指定更新到目標的映射的方法 `mappingId`。

<!-- r_update_destination_trait_data_order_id.xml -->

### 請求

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### 範例要求

除非另有指明，否則所有請求值都是必需的。

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
>* [目標序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [索引鍵值配對說明](../../../reference/key-value-pairs-explained.md)

