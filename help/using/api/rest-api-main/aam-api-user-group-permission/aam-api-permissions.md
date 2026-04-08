---
description: Rest API方法可管理物件和群組的許可權。
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: 許可權管理API方法
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
TQID: https://experienceleague.adobe.com/E9JWh1JKhHOSd7MzeOR8csVXChyh4Q0RiCj3Y5yb2vM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 96
ht-degree: 2%

---

# 許可權管理API方法 {#permissions-management-api-methods}

剩下[!DNL API]個方法可管理物件和群組的許可權。

<!-- c_rest_api_perm_man.xml -->

## 列出可用的物件型別 {#list-object-types}

`GET`方法，用來列出可設定角色型存取控制項的可用物件型別。

<!-- r_rest_api_perm_list.xml -->

### 請求

`GET /api/v1/permissionable-object-types/`

### 回應

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## 列出物件型別的可用許可權 {#list-permissions-object-type}

列出物件型別可用許可權的`GET`方法。

<!-- r_rest_api_perm_list_perms.xml -->

### 請求

`GET /api/v1/permissionable-object-types/SEGMENT/`

### 回應

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
}
```

>[!NOTE]
>
>物件型別TAGS和DERIVED SIGNALS沒有正常的使用許可權。 這些物件型別的控制項僅由「全部」或「無萬用字元許可權」變更。
