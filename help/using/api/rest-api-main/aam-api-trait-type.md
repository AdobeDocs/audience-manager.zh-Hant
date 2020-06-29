---
description: 可選方法，可讓您指派特徵給使用者定義的類型或類別，通常根據函式或您自己的內部報告程式。
seo-description: 可選方法，可讓您指派特徵給使用者定義的類型或類別，通常根據函式或您自己的內部報告程式。
seo-title: 特徵類型方法
solution: Audience Manager
title: 特徵類型方法
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 9%

---


# 特徵類型方法 {#trait-type-methods}

可選方法，可讓您指派特徵給使用者定義的類型或類別，通常根據函式或您自己的內部報告程式。

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>特徵類型方法不會將特徵指派給常用分類法使 [用的類別](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods)。 將這些視為與常用分類法分離的標籤。

對於視覺參考， [!UICONTROL Trait Types] 是位於下方的下拉式控制 [!DNL UI] 項 **[!UICONTROL Traits > Create new trait > Basic Information]**。

## 建立新特徵類型 {#create-trait-type}

可讓您 `POST` 建立新特徵類型的方法。

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

傳回 `GET` 指定特徵類型的詳細資料的方法。

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

## 所有特徵類型的返回屬性 {#return-props-all}

一種 `GET` 方法，可傳回陣列中所有特徵類型的詳細資料。

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
