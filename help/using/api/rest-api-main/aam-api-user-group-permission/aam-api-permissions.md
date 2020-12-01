---
description: 保留API方法來管理物件和群組的權限。
seo-description: 保留API方法來管理物件和群組的權限。
seo-title: 權限管理 API 方法
solution: Audience Manager
title: 權限管理 API 方法
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 14%

---


# 權限管理 API 方法 {#permissions-management-api-methods}

保留[!DNL API]方法來管理對象和組的權限。

<!-- c_rest_api_perm_man.xml -->

## 列出可用對象類型{#list-object-types}

`GET`方法，列出可在其上設定基於角色的訪問控制的可用對象類型。

<!-- r_rest_api_perm_list.xml -->

### 請求

`GET /api/v1/permissionable-object-types/`

### 回應

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## 列出對象類型{#list-permissions-object-type}的可用權限

`GET`方法，列出對象類型的可用權限。

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
>對象類型TAGS和DERIVED SIGNALS沒有常規使用權限。 這些物件類型的控制項僅透過「全部」或「無萬用字元權限」進行變更。