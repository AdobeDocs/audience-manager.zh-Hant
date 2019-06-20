---
description: 管理使用者的REST方法，包括建立、更新、列出、刪除和回傳使用者物件。
seo-description: 管理使用者的REST方法，包括建立、更新、列出、刪除和回傳使用者物件。
seo-title: 使用者管理API方法
solution: Audience Manager
title: 使用者管理API方法
uuid: 6e1f2c35-bb9 d-4166-b7 d4 d4-d9 c5518 a61 ad
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# User Management API Methods {#user-management-api-methods}

Rest [!DNL API] methods to manage users, including creating, updating, listing, deleting, and returning user objects.

<!-- c_rest_api_user_man_user.xml -->

## Create a User {#create-user}

A `POST` method to create a new user.

<!-- r_rest_api_user_create.xml -->

### 請求

`POST /api/v1/users/`

### 請求主體範例

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

If `isAdmin` is set to true, the user is created as a partner admin. 此屬性也可讓您知道使用者是否為合作夥伴管理員。

Returns `409 Conflict` if the username is already taken.

## Update a User {#update-user}

A `PUT` method to update a user.

<!-- r_rest_api_user_update.xml -->

### 請求

`PUT /api/v1/users/`*`<userId>`*

### 請求主體範例

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

Returns `409 Conflict` if the username is already taken.

## Update Logged-In User {#update-logged-in-user}

A `PUT` method to update the currently logged-in user.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### 請求

`PUT /self/update`

### 請求主體範例

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

Returns `409 Conflict` if the username is already taken.

## Update Logged-In User Password {#update-logged-in-user-pw}

A `PUT` method to update the currently logged-in user.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### 請求

`POST /users/self/update-password`

### 請求主體範例

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Returns `200 OK` if successful. Returns `400 Bad Request` if something is wrong with either password.

## Reset Logged-In User Password {#reset-logged-in-user-pw}

A `PUT` method to reset the currently logged-in user. [!UICONTROL Audience Management] 傳送使用者系統產生的密碼。

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### 請求

`POST /self/reset-password`

Returns `200 OK` if successful.

## Return User Object for a User ID {#return-user-object-for-id}

A `Get` method to return the user object for a User ID.

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

## Return User Object for Logged-In User {#return-user-object-for-logged-in-user}

A `Get` method to return the user object for the currently logged-in user.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

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

## List Users {#list-users}

A `GET` method to list users.

<!-- r_rest_api_user_list.xml -->

### 請求

`GET /api/v1/users/`

您可以在查詢參數中指定多個群組ID：

`GET /api/v1/users/?groupId=343&groupdId=12`

此查詢會傳回指定群組中所有使用者的清單。

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

## Delete a User {#delete-users}

A `DELETE` method to delete a user.

<!-- r_rest_api_user_delete.xml -->

### 請求

`DELETE /api/v1/users/`*`<user_id>`*

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## Delete Users in Bulk {#delete-users-bulk}

A `POST` method to delete multiple users in bulk.

<!-- r_rest_api_user_delete_bulk.xml -->

### 請求

`POST /api/v1/users/bulk-delete`

### 請求主體範例

```
{[<user_id_1>, <user_id_2>, ...]}
```
