---
description: 選擇性方法，可讓您將特徵指派給使用者定義的型別或類別（通常根據函式或您自己的內部報告程式）。
seo-description: Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.
seo-title: Trait Type Methods
solution: Audience Manager
title: 特徵型別方法
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
exl-id: d450f9ce-2abb-4a8b-b8db-2962b84fb341
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 3%

---

# 特徵型別方法 {#trait-type-methods}

選擇性方法，可讓您將特徵指派給使用者定義的型別或類別（通常根據函式或您自己的內部報告程式）。

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>特徵型別方法不會將特徵指派給[通用分類法](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods)使用的類別。 請將其視為與通用分類法不同的標籤。

對於視覺參考，[!UICONTROL Trait Types]是位於&#x200B;**[!UICONTROL Traits > Create new trait > Basic Information]**&#x200B;下的[!DNL UI]中的下拉式控制項。

## 建立新特徵型別 {#create-trait-type}

可讓您建立新特徵型別的`POST`方法。

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

## 傳回特徵型別的屬性 {#return-props}

傳回指定特徵型別詳細資料的`GET`方法。

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

## 傳回所有特徵型別的屬性 {#return-props-all}

傳回陣列中所有特徵型別詳細資料的`GET`方法。

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
