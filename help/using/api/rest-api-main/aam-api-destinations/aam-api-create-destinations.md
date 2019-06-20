---
description: 使用這些REEST API方法建立目的地。
seo-description: 使用這些REEST API方法建立目的地。
seo-title: 建立目標
solution: Audience Manager
title: 建立目標
uuid: 12f04151-ad0 e-4cb6-8f3 b-b5 c427 dc2 cef
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Destinations {#create-destinations}

Create destinations with these [!UICONTROL RESTful API] methods.

<!-- c_create_destinations.xml -->

## 支援的目的地類型：僅限URL和Cookie

The available `POST` methods let you create [!UICONTROL URL] and [!UICONTROL cookie destinations] only. Currently, you cannot create [!UICONTROL server-to-server destinations] with these [!DNL REST API] methods. However, the related destination `GET` methods let you retrieve information about [!UICONTROL server-to-server destinations] created in the user interface.

>[!MORE_贊_ this]
>
>* [目的地](../../../features/destinations/destinations.md#destination-api-methods)
>* [目的地序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [索引鍵值對說明](../../../reference/key-value-pairs-explained.md)


## Create a Non-Serial URL Destination {#create-nonserial-dest}

`POST` 一種方法，可讓您建立可接受由單一索引鍵值配對組成之區段的目的地(例如 `gender=male` ，或 `gender=female`)。

<!-- r_create_nonserial_destination.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

此請求會建立單一目的地。除非另有指示，否則需要所有要求值。

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### 回應

A successful request returns `201 created` and the destination.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4033, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (not serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"ACTIVE", 
   "destinationType":"PUSH", 
   "createTime":1338937116000, 
   "updateTime":1338937116000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":false, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "delimiter":null,
   "mappings":null
} 
```

>[!MORE_贊_ this]
>
>* [目的地序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)


## Create a Serialized URL Destination {#create-serial-url-dest}

`POST` 一種方法，可讓您建立可接受多個與單一索引鍵關聯之值的目的地(例如 `color=blue, red, green`，)。

<!-- r_create_serial_url_destination.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

Specify the secure [!DNL URL] and delimiter for the key-value pair passed in to the destination. 除非另有指示，否則需要所有要求值。

```
{ 
   "name":"Sample URL Destination (Serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":true,
   "urlFormatString":"https://www.adobe.com/send?data=%ALIAS%",
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
   "delimiter":","
}
```

### 回應

A successful update returns response code `201 created` and the destination.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4034, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (Serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"active", 
   "destinationType":"PUSH", 
   "createTime":1338937420000, 
   "updateTime":1338937420000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":true, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%", 
   "delimiter":"-", 
   "mappings":null 
}
```

>[!MORE_贊_ this]
>
>* [目的地序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)


## Create a Cookie Destination: Single-Key, Non-Serialized {#create-cookie-dest-single}

A `POST` method that lets you create a [!UICONTROL cookie destination] that accepts segments composed of single key-value pairs (e.g., `gender=male` or `gender=female`).

<!-- r_cookie_destination_singlekey_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

除非另有指示，否則需要所有要求值。

```
{ 
   "name":"Cookie Destination Single Key Not Serialized",
   "destinationType":"ADS",
   "adServerTypeID":1,
   "cookieName":"adobe",
   "cnameDomain":"adobe.com",
   "maxSize":"2048",
   "ttl":"0",
   "domainRestrictions":"inclusion",
   "siteIDs":[
      312
   ],
   "formatType":"single_key",
   "singleKey":"key",
   "keySeparator":"=",
   "valueSeparator":",",
   "serializationEnabled":false
}
```

### 回應

A successful update returns response code `201 created` and the destination.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4035, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Not Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338937984000, 
   "updateTime":1338937984000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"inclusion", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"key", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
      312 
   ], 
   "uparamEnabled":false
} 
```

>[!MORE_贊_ this]
>
>* [目的地序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [索引鍵值對說明](../../../reference/key-value-pairs-explained.md)


## Create a Cookie Destination: Single Key, Serialized {#create-cookie-dest-single-serial}

`POST` 一種方法，可讓您建立可接受多個與單一索引鍵關聯之值的目的地(例如 `color=blue, red, green`，)。

<!-- r_cookie_destination_singlekey_serial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

除非另有指示，否則需要所有要求值。

```
{ 
   "name":"Cookie Destination Single Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
 
   ], 
   "formatType":"single_key", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### 回應

A successful update returns response code `201 created` and the destination.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4036, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938329000, 
   "updateTime":1338938329000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false
}
```

>[!MORE_贊_ this]
>
>* [目的地序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [索引鍵值對說明](../../../reference/key-value-pairs-explained.md)


## Create a Cookie Destination: Multi-Key, Non-Serialized {#create-cookie-dest-multi}

`POST` 一種方法，可讓您建立可接受包含不同值之多個索引鍵(例如 `gender=male; gender=female; color=blue; color=red`，)的目標區段。

<!-- r_create_cookie_multikey_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

除非另有指示，否則需要所有要求值。

```
{ 
   "name":"Ad Server Multi-Key Not Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
  
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":false 
}
```

### 回應

A successful update returns response code `201 created` and the destination.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4037, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Not Serialized", 
   "status":1, 
   "destinationType":"ADS", 
   "createTime":1338938666000, 
   "updateTime":1338938666000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
  
   ], 
   "uparamEnabled":false 
}
```

## Create a Cookie Destination: Multi-Key, Serialized {#create-cookie-dest-multi-serial}

`POST` 一種方法，可讓您建立可接受包含多個索引鍵和值之區段的目的地(例如 `gender=male, female; color=blue, red, green`，)。

<!-- r_cookie_destination_multikey_serial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

除非另有指示，否則需要所有要求值。

```
{ 
   "name":"Cookie Destination Multi-Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains",
   "siteIDs":[ 
 
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### 回應

A successful update returns response code `201 created` and the destination.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4038, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938872000, 
   "updateTime":1338938872000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false 
}
```

>[!MORE_贊_ this]
>
>* [目的地序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [索引鍵值對說明](../../../reference/key-value-pairs-explained.md)

