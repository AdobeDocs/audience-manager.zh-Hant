---
description: REST API方法，用於管理對象和組的權限。
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: 權限管理 API 方法
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 12%

---

# 權限管理 API 方法 {#permissions-management-api-methods}

休息 [!DNL API] 管理對象和組權限的方法。

<!-- c_rest_api_perm_man.xml -->

## 列出可用對象類型 {#list-object-types}

A `GET` 方法，列出可設定基於角色的訪問控制的可用對象類型。

<!-- r_rest_api_perm_list.xml -->

### 請求

`GET /api/v1/permissionable-object-types/`

### 回應

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## 列出對象類型的可用權限 {#list-permissions-object-type}

A `GET` 方法，列出對象類型的可用權限。

<!-- r_rest_api_perm_list_perms.xml -->

### 請求

`GET /api/v1/permissionable-object-types/SEGMENT/`

### 回應

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
}
```

>[!NOTE]
>
>對象類型TAGS和DERIVED SIGNALS沒有使用的常規權限。 這些對象類型的控制項僅由「全部」或「無」通配符權限更改。
