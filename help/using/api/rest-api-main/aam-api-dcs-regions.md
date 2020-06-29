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

可讓您以程式設計方式列出Audience Manager地區 [!DNL DCS] 的方法。

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## 列出特定DCS地區 {#list-specific-dcs-region}

列 `GET` 出特定區域的方 [!DNL DCS] 法。

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

成功 `200 OK` 時傳回。

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## 列出DCS地區 {#list-dcs-regions}

一種 `GET` 列出區域的 [!DNL DCS] 方法。

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

成功 `200 OK` 時傳回。

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
