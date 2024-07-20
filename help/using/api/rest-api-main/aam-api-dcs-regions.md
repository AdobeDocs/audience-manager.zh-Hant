---
description: 可讓您以程式設計方式列出Audience ManagerDCS區域的方法。
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: DCS地區API方法
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 3%

---

# DCS地區API方法 {#dcs-region-api-methods}

可讓您以程式設計方式列出Audience Manager[!DNL DCS]區域的方法。

<!-- c_rest_api_regions.xml -->

如需區域及其對應整數的清單，請參閱[DCS區域ID、位置與主機名稱](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

## 列出特定DCS區域 {#list-specific-dcs-region}

列出特定[!DNL DCS]區域的`GET`方法。

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

列出[!DNL DCS]區域的`GET`方法。

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
