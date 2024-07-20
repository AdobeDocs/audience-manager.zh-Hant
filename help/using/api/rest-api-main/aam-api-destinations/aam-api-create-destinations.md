---
description: 使用這些RESTful API方法建立目的地。
seo-description: Create destinations with these RESTful API methods.
seo-title: Create Destinations
solution: Audience Manager
title: 建立目的地
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
feature: API
exl-id: bae0f304-0ff3-4c5f-b432-19aef61d9d10
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 6%

---

# 建立目的地 {#create-destinations}

使用這些[!UICONTROL RESTful API]方法建立目的地。

<!-- c_create_destinations.xml -->

## 支援的目的地型別：僅限URL和Cookie

可用的`POST`方法只能讓您建立[!UICONTROL URL]和[!UICONTROL cookie destinations]。 目前無法使用這[!DNL REST API]個方法建立[!UICONTROL server-to-server destinations]。 不過，相關的目的地`GET`方法可讓您擷取使用者介面中建立的[!UICONTROL server-to-server destinations]相關資訊。

## 建立非序列URL目的地 {#create-nonserial-dest}

`POST`方法可讓您建立接受由單一機碼值組（例如，`gender=male`或`gender=female`）組成的區段的目的地。

<!-- r_create_nonserial_destination.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

此請求會建立單一目的地。 除非另有指示，否則所有要求值都是必要的。

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### 回應

成功的要求傳回`201 created`和目的地。

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

## 建立序列化URL目的地 {#create-serial-url-dest}

`POST`方法可讓您建立接受與單一索引鍵（例如`color=blue, red, green`）相關聯的多個值的目的地。

<!-- r_create_serial_url_destination.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

為傳遞到目的地的機碼值組指定安全[!DNL URL]和分隔字元。 除非另有指示，否則所有要求值都是必要的。

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

成功更新會傳回回應代碼`201 created`和目的地。

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

## 建立Cookie目的地：單一金鑰、非序列化 {#create-cookie-dest-single}

`POST`方法可讓您建立接受由單一索引鍵值配對（例如，`gender=male`或`gender=female`）組成的區段的[!UICONTROL cookie destination]。

<!-- r_cookie_destination_singlekey_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

除非另有指示，否則所有要求值都是必要的。

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

成功更新會傳回回應代碼`201 created`和目的地。

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

## 建立Cookie目的地：單一金鑰，序列化 {#create-cookie-dest-single-serial}

`POST`方法可讓您建立接受與單一索引鍵（例如`color=blue, red, green`）相關聯的多個值的目的地。

<!-- r_cookie_destination_singlekey_serial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

除非另有指示，否則所有要求值都是必要的。

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

成功更新會傳回回應代碼`201 created`和目的地。

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

## 建立Cookie目的地：多索引鍵，非序列化 {#create-cookie-dest-multi}

`POST`方法可讓您建立目的地，以接受包含多個具有不同值的索引鍵（例如`gender=male; gender=female; color=blue; color=red`）的區段。

<!-- r_create_cookie_multikey_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

除非另有指示，否則所有要求值都是必要的。

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

成功更新會傳回回應代碼`201 created`和目的地。

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

## 建立Cookie目的地：多索引鍵，序列化 {#create-cookie-dest-multi-serial}

`POST`方法可讓您建立接受包含多個索引鍵和值（例如`gender=male, female; color=blue, red, green`）的區段的目的地。

<!-- r_cookie_destination_multikey_serial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

除非另有指示，否則所有要求值都是必要的。

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

成功更新會傳回回應代碼`201 created`和目的地。

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

>[!MORELIKETHIS]
>
>* [目的地](../../../features/destinations/destinations.md)
>* [目的地序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [索引鍵值配對說明](../../../reference/key-value-pairs-explained.md)
