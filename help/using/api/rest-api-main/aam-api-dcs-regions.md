---
description: 用於以寫程式方式列出Audience ManagerDCS區域的方法。
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: DCS 地區 API 方法
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 12%

---

# DCS 地區 API 方法 {#dcs-region-api-methods}

允許以寫程式方式列出Audience Manager的方法 [!DNL DCS] 區域。

<!-- c_rest_api_regions.xml -->

有關區域及其相應整數的清單，請參見 [DCS區域ID、位置和主機名](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

## 列出特定DCS區域 {#list-specific-dcs-region}

A `GET` 列出特定的方法 [!DNL DCS] 的子菜單。

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

返回 `200 OK` 成功。

有關區域及其相應整數的清單，請參見 [DCS區域ID、位置和主機名](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。

## 列出DCS區域 {#list-dcs-regions}

A `GET` 清單的方法 [!DNL DCS] 區域。

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

返回 `200 OK` 成功。

有關區域及其相應整數的清單，請參見 [DCS區域ID、位置和主機名](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。
