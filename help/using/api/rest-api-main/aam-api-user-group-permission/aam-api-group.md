---
description: 重設API方法來管理群組，包括建立、更新、列出和刪除群組。
seo-description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-title: Group Management API Methods
solution: Audience Manager
title: 群組管理API方法
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 5%

---

# 群組管理API方法 {#group-management-api-methods}

剩下[!DNL API]種管理群組的方法，包括建立、更新、列出及刪除群組。

<!-- c_rest_api_user_man_group.xml -->

## 建立群組 {#create-group}

建立新使用者群組的`POST`方法。

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

## 更新群組 {#update-group}

更新使用者群組的`PUT`方法。

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

## 清單群組 {#list-groups}

列出使用者群組的`GET`方法。

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

刪除使用者群組並移除該群組之所有成員的`DELETE`方法。

<!-- r_rest_api_group_delete.xml -->

### 請求

`DELETE /api/v1/groups/`*`<groupId>`*

如果成功，則傳回`204 No Content`。 在衝突的情況下傳回`409 Conflict`。

## 大量刪除群組 {#delete-groups-bulk}

一種`DELETE`方法，可大量刪除多個群組並移除該群組中的所有成員。

<!-- r_rest_api_group_delete_bulk.xml -->

### 請求

`DELETE /api/v1/groups/bulk-delete`

如果成功，則傳回`204 No Content`。 在衝突的情況下傳回`409 Conflict`。

## 列出群組的所有許可權 {#list-permissions-group}

列出群組許可權物件的`GET`方法。

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

如果群組無法存取，則傳回`400 Bad Request`。

## 設定群組的許可權 {#set-permissions-group}

更新群組許可權的`PUT`方法。 此方法會以新許可權覆寫舊許可權。

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

範例回應代表許可權物件的更新清單。

如果成功，則傳回`200 OK`。 如果任何指定的許可權無效，則傳回`400`。 如果登入的使用者無法存取物件，也可以傳回`403`。
