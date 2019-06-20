---
description: 讓您以程式設計方式列出Audience Manager DCS地區的方法。
seo-description: 讓您以程式設計方式列出Audience Manager DCS地區的方法。
seo-title: DCS地區API方法
solution: Audience Manager
title: DCS地區API方法
uuid: 00b70927-b3 b7-46bb-8be1-37c6100 ef80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DCS Region API Methods {#dcs-region-api-methods}

Methods that let you programmatically list Audience Manager [!UICONTROL DCS] regions.

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## List a Specific DCS Region {#list-specific-dcs-region}

`GET` 列出特定 [!UICONTROL DCS] 地區的方法。

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

Returns `200 OK` if successful.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## List DCS Regions {#list-dcs-regions}

`GET` 列出 [!UICONTROL DCS] 地區的方法。

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

Returns `200 OK` if successful.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
