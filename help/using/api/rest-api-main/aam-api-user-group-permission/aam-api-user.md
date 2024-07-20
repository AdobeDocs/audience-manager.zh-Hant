---
description: 使用Rest API方法來管理使用者，包括建立、更新、列出、刪除和傳回使用者物件。
seo-description: Rest API methods to manage users, including creating, updating, listing, deleting, and returning user objects.
seo-title: User Management API Methods
solution: Audience Manager
title: 使用者管理API方法
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 1%

---

# 使用者管理API方法 {#user-management-api-methods}

剩下[!DNL API]個方法可管理使用者，包括建立、更新、列出、刪除和傳回使用者物件。

<!-- c_rest_api_user_man_user.xml -->

## 建立使用者 {#create-user}

建立新使用者的`POST`方法。

<!-- r_rest_api_user_create.xml -->

### 請求

`POST /api/v1/users/`

### 範例要求內文

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

如果`isAdmin`設定為true，則會將使用者建立為合作夥伴管理員。 此屬性也可讓您知道使用者是否為合作夥伴管理員。

如果使用者名稱已被使用，則傳回`409 Conflict`。

## 更新使用者 {#update-user}

更新使用者的`PUT`方法。

<!-- r_rest_api_user_update.xml -->

### 請求

`PUT /api/v1/users/`*`<userId>`*

### 範例要求內文

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

如果使用者名稱已被使用，則傳回`409 Conflict`。

## 更新登入使用者 {#update-logged-in-user}

更新目前登入使用者的`PUT`方法。

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>雖然大多數[!DNL API]方法只能由合作夥伴管理員呼叫，但非管理員使用者可以呼叫此方法。

### 請求

`PUT /self/update`

### 範例要求內文

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

如果使用者名稱已被使用，則傳回`409 Conflict`。

## 更新登入使用者密碼 {#update-logged-in-user-pw}

更新目前登入使用者的`PUT`方法。

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>雖然大多數[!DNL API]方法只能由合作夥伴管理員呼叫，但非管理員使用者可以呼叫此方法。

### 請求

`POST /users/self/update-password`

### 範例要求內文

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

如果成功，則傳回`200 OK`。 若任一密碼發生錯誤，則傳回`400 Bad Request`。

## 重設登入使用者密碼 {#reset-logged-in-user-pw}

用來重設目前登入使用者的`PUT`方法。 [!UICONTROL Audience Management]傳送系統產生的密碼給使用者。

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>雖然大多數[!DNL API]方法只能由合作夥伴管理員呼叫，但非管理員使用者可以呼叫此方法。

### 請求

`POST /self/reset-password`

如果成功，則傳回`200 OK`。

## 傳回使用者ID的使用者物件 {#return-user-object-for-id}

傳回使用者ID之使用者物件的`Get`方法。

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

## 傳回登入使用者的使用者物件 {#return-user-object-for-logged-in-user}

傳回目前登入使用者之使用者物件的`Get`方法。

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>雖然大多數[!DNL API]方法只能由合作夥伴管理員呼叫，但非管理員使用者可以呼叫此方法。

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

## 列出使用者 {#list-users}

列出使用者的`GET`方法。

<!-- r_rest_api_user_list.xml -->

### 請求

`GET /api/v1/users/`

您可以在查詢引數中指定多個群組ID：

`GET /api/v1/users/?groupId=343&groupdId=12`

此查詢會傳回指定群組中的所有使用者清單。

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

## 刪除使用者 {#delete-users}

刪除使用者的`DELETE`方法。

<!-- r_rest_api_user_delete.xml -->

### 請求

`DELETE /api/v1/users/`*`<user_id>`*

如果成功，則傳回`204 No Content`。 在衝突的情況下傳回`409 Conflict`。

## 大量刪除使用者 {#delete-users-bulk}

用於大量刪除多個使用者的`POST`方法。

<!-- r_rest_api_user_delete_bulk.xml -->

### 請求

`POST /api/v1/users/bulk-delete`

### 範例要求內文

```
{[<user_id_1>, <user_id_2>, ...]}
```
