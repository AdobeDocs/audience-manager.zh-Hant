---
description: 可選方法，可讓您將特性指派給使用者定義的類型或類別，通常是根據函數或您自己的內部報告程序。
seo-description: 可選方法，可讓您將特性指派給使用者定義的類型或類別，通常是根據函數或您自己的內部報告程序。
seo-title: 特徵類型方法
solution: Audience Manager
title: 特徵類型方法
uuid: 082931d5-457b-4622-817b-86303f38c26a
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Trait Type Methods {#trait-type-methods}

可選方法，可讓您將特性指派給使用者定義的類型或類別，通常是根據函數或您自己的內部報告程序。

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Trait type methods do not assign traits to categories used by the [common taxonomy](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). 將這些標籤視為與一般分類法不同的標籤。

For visual reference, [!UICONTROL Trait Types] is a dropdown control located in the [!DNL UI] under **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Create a New Trait Type {#create-trait-type}

A `POST` method that lets you create a new trait type.

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

## Return Properties for a Trait Type {#return-props}

A `GET` method that returns details about the specified trait type.

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

## Return Properties for all Trait Types {#return-props-all}

A `GET` method that returns details about all your trait types in an array.

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
