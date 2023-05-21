---
description: 用於查看Audience Manager公用分類的方法。 此可選分類方案將特徵組織為行業標準類別。
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: 分類 API 方法
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 6%

---

# 分類 API 方法 {#taxonomic-api-methods}

用於查看Audience Manager公用分類的方法。 此可選分類方案將特徵組織為行業標準類別。

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>不能用這些方法建立新分類類別或分類特徵。 要分類特徵，請指定相應 `categoryId` 以特徵建立或更新方法。

## 返回特定分類 {#return-specific-taxonomy}

A `GET` 返回有關指定分類類別的詳細資訊的方法。

<!-- r_rest_api_taxonomy.xml -->

### 請求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### 回應

成功的響應返回 `200 OK` 和指定ID的類別。 未成功的請求返回 `404 No Content` 的子菜單。

```
{
    "crUID": 158,
    "name": "Arts & Entertainment",
    "upUID": 158,
    "description": "Arts & Entertainment",
    "categoryID": 1,
    "parentCategoryID": 0
}
```

## 返回所有分類類別 {#return-all-taxonomy-categories}

A `GET` 方法，它返回陣列中頂級類別的清單。

<!-- r_rest_api_taxonomies.xml -->

### 請求

`GET https://api.demdex.com/v1/taxonomies/0/`

### 回應

為簡單而截斷。

```
[
    {
        "crUID": 158,
        "name": "Arts & Entertainment",
        "upUID": 158,
        "description": "Arts & Entertainment",
        "categoryID": 1,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Automotive",
        "upUID": 158,
        "description": "Automotive",
        "categoryID": 2,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Business",
        "upUID": 158,
        "description": "Business",
        "categoryID": 3,
        "parentCategoryID": 0
    }
]
```

## 返回分類子類別 {#return-taxonomy-sub-categories}

A `GET` 方法，它返回陣列中指定父類別的子類別。

<!-- r_rest_api_taxonomy_sub.xml -->

### 請求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### 回應

成功的響應返回 `200 OK` 和指定ID的類別。 未成功的請求返回 `404 No Content` 的子菜單。 為簡單而截斷。

```
[
    {
        "crUID": 158,
        "name": "Books & Literature",
        "upUID": 158,
        "description": "Books & Literature",
        "categoryID": 25,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Celebrity Fan/Gossip",
        "upUID": 158,
        "description": "Celebrity Fan/Gossip",
        "categoryID": 49,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Fine Art",
        "upUID": 158,
        "description": "Fine Art",
        "categoryID": 72,
        "parentCategoryID": 1
    }
]
```
