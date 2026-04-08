---
description: 可讓您以程式設計方式列出Audience Manager DCS區域的方法。
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: DCS地區API方法
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
TQID: https://experienceleague.adobe.com/ipsOlq24Y00SHvGKgUFJHnRQ11DZIuDNY76D5LCAgso
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 110
ht-degree: 3%

---

# DCS地區API方法 {#dcs-region-api-methods}

可讓您以程式設計方式列出Audience Manager [!DNL DCS]區域的方法。

<!-- c_rest_api_regions.xml -->

如需區域及其對應整數的清單，請參閱[DCS區域ID、位置與主機名稱](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

## 列出特定DCS區域 {#list-specific-dcs-region}

列出特定`GET`區域的[!DNL DCS]方法。

<!-- r_rest_api_regions_list_specific.xml -->

### 請求

`GET /v1/dcs-regions/`*`<id>`*

### 範例回應

```
{ 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code>",
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  }
```

如果成功，則傳回`200 OK`。

如需區域及其對應整數的清單，請參閱[DCS區域ID、位置與主機名稱](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

## 列出DCS地區 {#list-dcs-regions}

列出`GET`區域的[!DNL DCS]方法。

<!-- r_rest_api_regions_list.xml -->

### 請求

`GET /v1/dcs-regions/`

### 範例回應

```
[
  { 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code> # APSE, USE, etc,
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  },
  ...
]
```

如果成功，則傳回`200 OK`。

如需區域及其對應整數的清單，請參閱[DCS區域ID、位置與主機名稱](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。
