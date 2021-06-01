---
description: 重設API方法來管理群組，包括建立、更新、列出、刪除群組。
seo-description: 重設API方法來管理群組，包括建立、更新、列出、刪除群組。
seo-title: 群組管理 API 方法
solution: Audience Manager
title: 群組管理 API 方法
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 13%

---

# 群組管理 API 方法 {#group-management-api-methods}

請停用[!DNL API]方法來管理群組，包括建立、更新、列出、刪除群組。

<!-- c_rest_api_user_man_group.xml -->

## 建立群組 {#create-group}

建立新用戶組的`POST`方法。

<!-- r_rest_api_group_create.xml -->

### 請求

`POST /api/v1/groups/`

### 範例要求內文

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

## 更新組{#update-group}

更新用戶組的`PUT`方法。

<!--
r_rest_api_group_update.xml
-->

### 請求

`PUT /api/v1/groups/`*`<groupId>`*

### 範例要求內文

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

## 清單組{#list-groups}

列出用戶組的`GET`方法。

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

`DELETE`方法，用於刪除用戶組並從該組中刪除所有成員。

<!-- r_rest_api_group_delete.xml -->

### 請求

`DELETE /api/v1/groups/`*`<groupId>`*

如果成功，則傳回`204 No Content`。 如果發生衝突，則返回`409 Conflict`。

## 大量刪除組{#delete-groups-bulk}

`DELETE`方法，可批量刪除多個組並從該組中刪除所有成員。

<!-- r_rest_api_group_delete_bulk.xml -->

### 請求

`DELETE /api/v1/groups/bulk-delete`

如果成功，則傳回`204 No Content`。 如果發生衝突，則返回`409 Conflict`。

## 列出組{#list-permissions-group}的所有權限

列出組上權限對象的`GET`方法。

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

如果組無法訪問，則返回`400 Bad Request`。

## 設定組{#set-permissions-group}的權限

更新群組權限的`PUT`方法。 此方法會以新權限覆寫舊權限。

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

範例回應代表更新的權限物件清單。

如果成功，則傳回`200 OK`。 如果任何給定權限無效，則返回`400`。 如果登錄用戶無法訪問該對象，也可以返回`403`。
