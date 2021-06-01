---
description: 重設API方法以管理物件和群組的權限。
seo-description: 重設API方法以管理物件和群組的權限。
seo-title: 權限管理 API 方法
solution: Audience Manager
title: 權限管理 API 方法
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 15%

---

# 權限管理 API 方法 {#permissions-management-api-methods}

請停用[!DNL API]方法以管理物件和群組的權限。

<!-- c_rest_api_perm_man.xml -->

## 列出可用對象類型{#list-object-types}

`GET`方法，列出可設定基於角色的訪問控制的可用對象類型。

<!-- r_rest_api_perm_list.xml -->

### 請求

`GET /api/v1/permissionable-object-types/`

### 回應

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## 列出對象類型{#list-permissions-object-type}的可用權限

列出對象類型可用權限的`GET`方法。

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
>物件類型TAGS和衍生訊號沒有可使用的一般權限。 對這些對象類型的控制項僅通過「全部」或「無萬用字元權限」更改。
