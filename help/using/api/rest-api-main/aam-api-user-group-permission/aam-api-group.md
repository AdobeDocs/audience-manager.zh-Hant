---
description: 剩餘API方法來管理群組，包括建立、更新、列出、刪除群組。
seo-description: 剩餘API方法來管理群組，包括建立、更新、列出、刪除群組。
seo-title: 群組管理API方法
solution: Audience Manager
title: 群組管理API方法
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# 群組管理API方法 {#group-management-api-methods}

剩餘 [!DNL API] 方法來管理群組，包括建立、更新、列出、刪除群組。

<!-- c_rest_api_user_man_group.xml -->

## 建立群組 {#create-group}

建立 `POST` 新使用者群組的方法。

<!-- r_rest_api_group_create.xml -->

### 請求

`POST /api/v1/groups/`

### 請求正文示例

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

## 更新群組 {#update-group}

一種 `PUT` 更新用戶組的方法。

<!--
r_rest_api_group_update.xml
-->

### 請求

`PUT /api/v1/groups/`*`<groupId>`*

### 請求正文示例

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

## 清單群組 {#list-groups}

列出 `GET` 使用者群組的方法。

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

刪除 `DELETE` 使用者群組並移除該群組中所有成員的方法。

<!-- r_rest_api_group_delete.xml -->

### 請求

`DELETE /api/v1/groups/`*`<groupId>`*

成功 `204 No Content` 時傳回。 如果發生衝突，則返回 `409 Conflict`。

## 大量刪除群組 {#delete-groups-bulk}

一種 `DELETE` 批量刪除多個組並從該組中刪除所有成員的方法。

<!-- r_rest_api_group_delete_bulk.xml -->

### 請求

`DELETE /api/v1/groups/bulk-delete`

成功 `204 No Content` 時傳回。 如果發生衝突，則返回 `409 Conflict`。

## 列出群組的所有權限 {#list-permissions-group}

列 `GET` 出群組上權限物件的方法。

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

如果 `400 Bad Request` 組無法訪問，則返回。

## Set Permissions for a Group {#set-permissions-group}

更新 `PUT` 群組權限的方法。 此方法會以新權限覆寫舊權限。

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

範例回應代表權限物件的更新清單。

成功 `200 OK` 時傳回。 如果 `400` 任何給定權限無效，則返回。 如果登入 `403` 的使用者無法存取物件，也可以傳回。