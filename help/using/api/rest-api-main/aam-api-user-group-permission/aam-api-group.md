---
description: Rest API方法可管理群組，包括建立、更新、列出和刪除群組。
seo-description: Rest API方法可管理群組，包括建立、更新、列出和刪除群組。
seo-title: 群組管理API方法
solution: Audience Manager
title: 群組管理API方法
uuid: fe042eb5-ea12-42Fe-be98-d721 f987 a914
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Group Management API Methods {#group-management-api-methods}

Rest [!DNL API] methods to manage groups, including creating, updating, listing, deleting groups.

<!-- c_rest_api_user_man_group.xml -->

## 建立群組 {#create-group}

A `POST` method to create a new user group.

<!-- r_rest_api_group_create.xml -->

### 請求

`POST /api/v1/groups/`

### 請求主體範例

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

## Update a Group {#update-group}

A `PUT` method to update a user group.

<!--
r_rest_api_group_update.xml
-->

### 請求

`PUT /api/v1/groups/`*`<groupId>`*

### 請求主體範例

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

## List Groups {#list-groups}

A `GET` method to list user groups.

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

A `DELETE` method to delete a user group and remove all members from that group.

<!-- r_rest_api_group_delete.xml -->

### 請求

`DELETE /api/v1/groups/`*`<groupId>`*

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## Delete Groups in Bulk {#delete-groups-bulk}

`DELETE` 一種方法，可大量刪除多個群組，並移除該群組中的所有成員。

<!-- r_rest_api_group_delete_bulk.xml -->

### 請求

`DELETE /api/v1/groups/bulk-delete`

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## List All Permissions for a Group {#list-permissions-group}

A `GET` method to list the permission objects on a group.

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

Returns `400 Bad Request` if the group is inaccessible.

## Set Permissions for a Group {#set-permissions-group}

A `PUT` method to update group permissions. 此方法會以新權限覆寫舊權限。

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

樣本回應代表權限物件的更新清單。

Returns `200 OK` if successful. Returns `400` if any given permission is invalid. Can also return `403` if the object is not accessible by the logged-in user.