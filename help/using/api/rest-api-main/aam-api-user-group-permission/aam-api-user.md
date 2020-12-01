---
description: 保留API方法來管理使用者，包括建立、更新、列出、刪除和傳回使用者物件。
seo-description: 保留API方法來管理使用者，包括建立、更新、列出、刪除和傳回使用者物件。
seo-title: 使用者管理 API 方法
solution: Audience Manager
title: 使用者管理 API 方法
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 7%

---


# 使用者管理 API 方法 {#user-management-api-methods}

保留[!DNL API]方法來管理用戶，包括建立、更新、列出、刪除和返回用戶對象。

<!-- c_rest_api_user_man_user.xml -->

## 建立用戶{#create-user}

用於建立新用戶的`POST`方法。

<!-- r_rest_api_user_create.xml -->

### 請求

`POST /api/v1/users/`

### 請求正文示例

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

如果`isAdmin`設為true，則會以合作夥伴管理員的身分建立使用者。 此屬性也可讓您知道使用者是否為合作夥伴管理員。

如果已使用用戶名，則返回`409 Conflict`。

## 更新用戶{#update-user}

用於更新用戶的`PUT`方法。

<!-- r_rest_api_user_update.xml -->

### 請求

`PUT /api/v1/users/`*`<userId>`*

### 請求正文示例

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

如果已使用用戶名，則返回`409 Conflict`。

## 更新登入使用者{#update-logged-in-user}

`PUT`方法，用於更新當前登錄的用戶。

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>雖然大部分[!DNL API]方法只能由合作夥伴管理員呼叫，但此方法可由非管理員使用者呼叫。

### 請求

`PUT /self/update`

### 請求正文示例

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

如果已使用用戶名，則返回`409 Conflict`。

## 更新登入使用者密碼{#update-logged-in-user-pw}

`PUT`方法，用於更新當前登錄的用戶。

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>雖然大部分[!DNL API]方法只能由合作夥伴管理員呼叫，但此方法可由非管理員使用者呼叫。

### 請求

`POST /users/self/update-password`

### 請求正文示例

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

如果成功，則返回`200 OK`。 如果任一密碼出錯，則返回`400 Bad Request`。

## 重設登錄用戶密碼{#reset-logged-in-user-pw}

`PUT`方法，可重設目前登入的使用者。 [!UICONTROL Audience Management] 向用戶發送系統生成的口令。

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>雖然大部分[!DNL API]方法只能由合作夥伴管理員呼叫，但此方法可由非管理員使用者呼叫。

### 請求

`POST /self/reset-password`

如果成功，則返回`200 OK`。

## 返回用戶ID {#return-user-object-for-id}的用戶對象

`Get`方法，用於返回用戶ID的用戶對象。

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

## 返回登錄用戶{#return-user-object-for-logged-in-user}的用戶對象

`Get`方法，可返回當前登錄用戶的用戶對象。

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>雖然大部分[!DNL API]方法只能由合作夥伴管理員呼叫，但此方法可由非管理員使用者呼叫。

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

## 列出用戶{#list-users}

列出用戶的`GET`方法。

<!-- r_rest_api_user_list.xml -->

### 請求

`GET /api/v1/users/`

您可以在查詢參數中指定多個群組ID:

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

## 刪除用戶{#delete-users}

刪除用戶的`DELETE`方法。

<!-- r_rest_api_user_delete.xml -->

### 請求

`DELETE /api/v1/users/`*`<user_id>`*

如果成功，則返回`204 No Content`。 如果發生衝突，則返回`409 Conflict`。

## 大量刪除用戶{#delete-users-bulk}

一種批量刪除多個用戶的`POST`方法。

<!-- r_rest_api_user_delete_bulk.xml -->

### 請求

`POST /api/v1/users/bulk-delete`

### 請求正文示例

```
{[<user_id_1>, <user_id_2>, ...]}
```
