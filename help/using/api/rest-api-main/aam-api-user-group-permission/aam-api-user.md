---
description: 剩餘的API方法用於管理用戶，包括建立、更新、列出、刪除和返回用戶對象。
seo-description: Rest API methods to manage users, including creating, updating, listing, deleting, and returning user objects.
seo-title: User Management API Methods
solution: Audience Manager
title: 使用者管理 API 方法
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 6%

---

# 使用者管理 API 方法 {#user-management-api-methods}

休息 [!DNL API] 管理用戶的方法，包括建立、更新、列出、刪除和返回用戶對象。

<!-- c_rest_api_user_man_user.xml -->

## 建立用戶 {#create-user}

A `POST` 的子菜單。

<!-- r_rest_api_user_create.xml -->

### 請求

`POST /api/v1/users/`

### 示例請求正文

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : true | false 
}
```

### 回應

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : <"true"|"false"> 
 
}
```

如果 `isAdmin` 設定為true時，用戶將建立為夥伴管理員。 此屬性還允許您知道用戶是否是合作夥伴管理員。

返回 `409 Conflict` 的子菜單。

## 更新用戶 {#update-user}

A `PUT` 更新用戶的方法。

<!-- r_rest_api_user_update.xml -->

### 請求

`PUT /api/v1/users/`*`<userId>`*

### 示例請求正文

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
}
```

### 回應

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

返回 `409 Conflict` 的子菜單。

## 更新登錄用戶 {#update-logged-in-user}

A `PUT` 更新當前登錄用戶的方法。

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>而大多數 [!DNL API] 方法只能由夥伴管理員調用，此方法可由非管理員用戶調用。

### 請求

`PUT /self/update`

### 示例請求正文

```
{  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

### 回應

```
{ 
  "userId": <integer>,,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string> 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

返回 `409 Conflict` 的子菜單。

## 更新登錄用戶密碼 {#update-logged-in-user-pw}

A `PUT` 更新當前登錄用戶的方法。

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>而大多數 [!DNL API] 方法只能由夥伴管理員調用，此方法可由非管理員用戶調用。

### 請求

`POST /users/self/update-password`

### 示例請求正文

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

返回 `200 OK` 成功。 返回 `400 Bad Request` 的下界。

## 重置登錄用戶密碼 {#reset-logged-in-user-pw}

A `PUT` 重置當前登錄用戶的方法。 [!UICONTROL Audience Management] 向用戶發送系統生成的密碼。

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>而大多數 [!DNL API] 方法只能由夥伴管理員調用，此方法可由非管理員用戶調用。

### 請求

`POST /self/reset-password`

返回 `200 OK` 成功。

## 返回用戶ID的用戶對象 {#return-user-object-for-id}

A `Get` 方法返回用戶ID的用戶對象。

<!-- r_rest_api_user_get_user_obj.xml -->

### 請求

`GET /api/v1/users/`*`<userId>`*

### 回應

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## 返回已登錄用戶的用戶對象 {#return-user-object-for-logged-in-user}

A `Get` 方法，以返回當前登錄用戶的用戶對象。

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>而大多數 [!DNL API] 方法只能由夥伴管理員調用，此方法可由非管理員用戶調用。

### 請求

`GET /api/v1/users/self`

### 回應

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## 列出用戶 {#list-users}

A `GET` 列出用戶的方法。

<!-- r_rest_api_user_list.xml -->

### 請求

`GET /api/v1/users/`

可以在查詢參數中指定多個組ID:

`GET /api/v1/users/?groupId=343&groupdId=12`

此查詢返回指定組中所有用戶的清單。

### 回應

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

## 刪除用戶 {#delete-users}

A `DELETE` 刪除用戶的方法。

<!-- r_rest_api_user_delete.xml -->

### 請求

`DELETE /api/v1/users/`*`<user_id>`*

返回 `204 No Content` 成功。 在衝突返回時 `409 Conflict`。

## 批量刪除用戶 {#delete-users-bulk}

A `POST` 方法批量刪除多個用戶。

<!-- r_rest_api_user_delete_bulk.xml -->

### 請求

`POST /api/v1/users/bulk-delete`

### 示例請求正文

```
{[<user_id_1>, <user_id_2>, ...]}
```
