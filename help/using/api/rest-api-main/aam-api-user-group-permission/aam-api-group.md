---
description: 剩餘的API方法來管理組，包括建立、更新、清單、刪除組。
seo-description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-title: Group Management API Methods
solution: Audience Manager
title: 群組管理 API 方法
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 12%

---

# 群組管理 API 方法 {#group-management-api-methods}

休息 [!DNL API] 管理組的方法，包括建立、更新、清單、刪除組。

<!-- c_rest_api_user_man_group.xml -->

## 建立群組 {#create-group}

A `POST` 的子菜單。

<!-- r_rest_api_group_create.xml -->

### 請求

`POST /api/v1/groups/`

### 示例請求正文

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### 回應

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## 更新組 {#update-group}

A `PUT` 更新用戶組的方法。

<!--
r_rest_api_group_update.xml
-->

### 請求

`PUT /api/v1/groups/`*`<groupId>`*

### 示例請求正文

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### 回應

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## 清單組 {#list-groups}

A `GET` 列出用戶組的方法。

<!--
r_rest_api_group_list.xml
-->

### 請求

`GET /api/v1/groups/`

### 回應

```
[
  { 
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }, ...
]
```

## 刪除群組 {#delete-groups}

A `DELETE` 刪除用戶組並從該組中刪除所有成員的方法。

<!-- r_rest_api_group_delete.xml -->

### 請求

`DELETE /api/v1/groups/`*`<groupId>`*

返回 `204 No Content` 成功。 在衝突返回時 `409 Conflict`。

## 批量刪除組 {#delete-groups-bulk}

A `DELETE` 方法，以批量刪除多個組並從該組中刪除所有成員。

<!-- r_rest_api_group_delete_bulk.xml -->

### 請求

`DELETE /api/v1/groups/bulk-delete`

返回 `204 No Content` 成功。 在衝突返回時 `409 Conflict`。

## 列出組的所有權限 {#list-permissions-group}

A `GET` 列出組上的權限對象的方法。

<!-- r_rest_api_perm_list_group.xml -->

### 請求

`GET /api/v1/groups/{groupId}/permissions`

### 回應

```
[{
 "objectId" : 34,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },

{
 "objectId" : "234",
 "objectType": "TRAIT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },
 {
 "objectId" : 277,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "MAP_TO_MODELS"]
 }
]
```

返回 `400 Bad Request` 的子菜單。

## 設定組的權限 {#set-permissions-group}

A `PUT` 更新組權限的方法。 此方法用新權限覆蓋舊權限。

<!-- r_rest_api_perm_set.xml -->

### 請求

`PUT /api/v1/groups/{groupId}/permissions/`

### 回應

```
[ 
  { "objectType" : "SEGMENT",
    "objectId" : 563,
    "permissions" : [ "READ", "WRITE"]
  },
  { "objectType" : "SEGMENT",
    "objectId" : 2363,
    "permissions" : [ "CREATE", "WRITE"]
  },
  { "objectType" : "TRAIT",
    "objectId" : 83498,
    "permissions" : [ "READ", "MAP_TO_SEGMENTS"]
  },
  { "objectType" : "DESTINATION",
    "objectId" : 304,
    "permissions" : [ "READ", "WRITE", "CREATE"]
  }
]
```

示例響應表示已更新的權限對象清單。

返回 `200 OK` 成功。 返回 `400` 如果任何給定權限無效。 也可以返回 `403` 如果已登錄的用戶無法訪問該對象。
