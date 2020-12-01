---
description: 可讓您以程式設計方式列出Audience Manager DCS地區的方法。
seo-description: 可讓您以程式設計方式列出Audience Manager DCS地區的方法。
seo-title: DCS 地區 API 方法
solution: Audience Manager
title: DCS 地區 API 方法
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 14%

---


# DCS 地區 API 方法 {#dcs-region-api-methods}

可讓您以程式設計方式列出Audience Manager [!DNL DCS]地區的方法。

<!-- c_rest_api_regions.xml -->

有關區域及其對應整數的清單，請參閱[DCS區域ID、位置和主機名](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

## 列出特定DCS區域{#list-specific-dcs-region}

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

如果成功，則返回`200 OK`。

有關區域及其對應整數的清單，請參閱[DCS區域ID、位置和主機名](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

## 列出DCS地區{#list-dcs-regions}

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

如果成功，則返回`200 OK`。

有關區域及其對應整數的清單，請參閱[DCS區域ID、位置和主機名](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。
