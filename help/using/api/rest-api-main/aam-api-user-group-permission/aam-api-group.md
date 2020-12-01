---
description: 剩餘API方法來管理群組，包括建立、更新、列出、刪除群組。
seo-description: 剩餘API方法來管理群組，包括建立、更新、列出、刪除群組。
seo-title: 群組管理 API 方法
solution: Audience Manager
title: 群組管理 API 方法
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 13%

---


# 群組管理 API 方法 {#group-management-api-methods}

保留[!DNL API]方法來管理群組，包括建立、更新、列出、刪除群組。

<!-- c_rest_api_user_man_group.xml -->

## 建立群組 {#create-group}

用於建立新用戶組的`POST`方法。

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

## 更新群組{#update-group}

用於更新用戶組的`PUT`方法。

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

## 清單群組{#list-groups}

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

`DELETE`方法，可刪除使用者群組並移除該群組的所有成員。

<!-- r_rest_api_group_delete.xml -->

### 請求

`DELETE /api/v1/groups/`*`<groupId>`*

如果成功，則返回`204 No Content`。 如果發生衝突，則返回`409 Conflict`。

## 大量刪除組{#delete-groups-bulk}

`DELETE`方法，可大量刪除多個組，並從該組中刪除所有成員。

<!-- r_rest_api_group_delete_bulk.xml -->

### 請求

`DELETE /api/v1/groups/bulk-delete`

如果成功，則返回`204 No Content`。 如果發生衝突，則返回`409 Conflict`。

## 列出組{#list-permissions-group}的所有權限

`GET`方法，列出群組上的權限物件。

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

## 設定群組的權限{#set-permissions-group}

`PUT`方法，可更新群組權限。 此方法會以新權限覆寫舊權限。

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

如果成功，則返回`200 OK`。 如果任何給定權限無效，則返回`400`。 如果登入的使用者無法存取物件，也可傳回`403`。