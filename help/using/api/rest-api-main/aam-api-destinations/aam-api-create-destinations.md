---
description: 使用這些REST風格的API方法建立目標。
seo-description: 使用這些REST風格的API方法建立目標。
seo-title: 建立目的地
solution: Audience Manager
title: 建立目的地
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 9%

---


# 建立目的地 {#create-destinations}

使用這些[!UICONTROL RESTful API]方法建立目標。

<!-- c_create_destinations.xml -->

## 支援的目標類型：僅限URL和Cookie

可用的`POST`方法僅允許您建立[!UICONTROL URL]和[!UICONTROL cookie destinations]。 目前，您無法使用這些[!DNL REST API]方法建立[!UICONTROL server-to-server destinations]。 但是，相關的目標`GET`方法可讓您擷取有關在使用者介面中建立的[!UICONTROL server-to-server destinations]資訊。

## 建立非串列URL目標{#create-nonserial-dest}

一種`POST`方法，可讓您建立接受由單鍵值配對（例如`gender=male`或`gender=female`）組成之區段的目的地。

<!-- r_create_nonserial_destination.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

此請求會建立單一目標。 除非另有指示，否則所有請求值都為必要值。

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### 回應

成功的請求返回`201 created`和目標。

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

## 建立序列化URL目標{#create-serial-url-dest}

一種`POST`方法，可讓您建立接受與單一索引鍵相關聯之多個值的目的地（例如`color=blue, red, green`）。

<!-- r_create_serial_url_destination.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

為傳遞至目的地的鍵值對指定安全[!DNL URL]和分隔字元。 除非另有指示，否則所有請求值都為必要值。

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

成功的更新會傳回回回應代碼`201 created`和目標。

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

## 建立Cookie目標：單鍵，無序{#create-cookie-dest-single}

`POST`方法，可讓您建立[!UICONTROL cookie destination]，接受由單鍵值對（例如`gender=male`或`gender=female`）組成的區段。

<!-- r_cookie_destination_singlekey_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

除非另有指示，否則所有請求值都為必要值。

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

成功的更新會傳回回回應代碼`201 created`和目標。

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

## 建立Cookie目標：單鍵，序列化{#create-cookie-dest-single-serial}

一種`POST`方法，可讓您建立接受與單一索引鍵相關聯之多個值的目的地（例如`color=blue, red, green`）。

<!-- r_cookie_destination_singlekey_serial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

除非另有指示，否則所有請求值都為必要值。

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

成功的更新會傳回回回應代碼`201 created`和目標。

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

## 建立Cookie目標：多鍵，無序{#create-cookie-dest-multi}

一種`POST`方法，可讓您建立接受包含具有不同值（例如`gender=male; gender=female; color=blue; color=red`）之多個索引鍵之區段的目標。

<!-- r_create_cookie_multikey_noserial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

除非另有指示，否則所有請求值都為必要值。

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

成功的更新會傳回回回應代碼`201 created`和目標。

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

## 建立Cookie目標：多鍵，序列化{#create-cookie-dest-multi-serial}

一種`POST`方法，可讓您建立接受包含多個鍵和值的區段的目的地（例如`gender=male, female; color=blue, red, green`）。

<!-- r_cookie_destination_multikey_serial.xml -->

### 請求

`POST https://api.demdex.com/v1/destinations/`

### 範例要求

除非另有指示，否則所有請求值都為必要值。

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

成功的更新會傳回回回應代碼`201 created`和目標。

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
>* [目標序列化](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [索引鍵值配對說明](../../../reference/key-value-pairs-explained.md)

