---
description: 可選方法，允許您將特徵分配給用戶定義的類型或類別，通常根據函式或您自己的內部報告流程進行。
seo-description: Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.
seo-title: Trait Type Methods
solution: Audience Manager
title: 特徵類型方法
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
exl-id: d450f9ce-2abb-4a8b-b8db-2962b84fb341
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 9%

---

# 特徵類型方法 {#trait-type-methods}

可選方法，允許您將特徵分配給用戶定義的類型或類別，通常根據函式或您自己的內部報告流程進行。

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>特徵類型方法不會將特徵指定給 [通用分類](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods)。 將這些標籤視為與常用分類分離的標籤。

為了便於查看， [!UICONTROL Trait Types] 是位於 [!DNL UI] 在 **[!UICONTROL Traits > Create new trait > Basic Information]**。

## 建立新特性類型 {#create-trait-type}

A `POST` 用於建立新特徵類型的方法。

<!-- r_rest_api_create_trait_type.xml -->

### 請求

`POST https://api.demdex.com/v1/customer-trait-types`

### 範例要求

```
{
"name":"Custom trait type"
}
```

### 回應

```
{
    "pixelType": 34,
    "pid": 1099,
    "name": "Custom type",
    "description": null,
    "crUID": 694,
    "upUID": 694,
    "createTime": 1358297352000,
    "updateTime": 1358297352000
}
```

## 特徵類型的返回屬性 {#return-props}

A `GET` 返回有關指定特徵類型的詳細資訊的方法。

<!-- r_rest_api_get_trait_type.xml -->

### 請求

`GET https://api.demdex.com/v1/customer-trait-types/`*`<customerTraitTypeId>`*

### 回應

```
{
    "pixelType": 4,
    "pid": 0,
    "name": "Delivery Event",
    "description": "Delivery Event",
    "crUID": 158,
    "upUID": 158,
    "createTime": 1299115496000,
    "updateTime": 1299115496000
}
```

## 返回所有特徵類型的屬性 {#return-props-all}

A `GET` 方法，它返回有關陣列中所有特徵類型的詳細資訊。

<!-- r_rest_api_get_trait_types.xml -->

### 請求

`GET https://api.demdex.com/v1/customer-trait-types/`

### 回應

```
[
    {
        "pixelType": 200,
        "pid": 1099,
        "name": "Customer Specific Trait Type",
        "description": "Test",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1349990458000,
        "updateTime": 1349990458000
    },
    {
        "pixelType": 1,
        "pid": 0,
        "name": "User Trait",
        "description": "User Trait",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115492000,
        "updateTime": 1299115492000
    },
    {
        "pixelType": 2,
        "pid": 0,
        "name": "Site Visitor",
        "description": "Site Visitor",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115493000,
        "updateTime": 1299115493000
    }
]
```
