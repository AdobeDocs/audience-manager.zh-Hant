---
description: 可讓您檢視Audience Manager常用分類法的方法。此選用分類配置將特徵組織成業界標準類別。
seo-description: 可讓您檢視Audience Manager常用分類法的方法。此選用分類配置將特徵組織成業界標準類別。
seo-title: 分類API方法
solution: Audience Manager
title: 分類API方法
uuid: ee29ba5-e9 ba-4498-a6 ee-7343227dd7 ba
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Taxonomic API Methods {#taxonomic-api-methods}

可讓您檢視Audience Manager常用分類法的方法。此選用分類配置將特徵組織成業界標準類別。

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>您無法使用這些方法建立新的分類類別或分類特徵。To classify a trait, specify the appropriate `categoryId` with a trait create or update method.

## Return a Specific Taxonomy {#return-specific-taxonomy}

A `GET` method that returns details about the specified taxonomic category.

<!-- r_rest_api_taxonomy.xml -->

### 請求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### 回應

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist.

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

## Return all Taxonomic Categories {#return-all-taxonomy-categories}

A `GET` method that returns a list of the top-level categories in an array.

<!-- r_rest_api_taxonomies.xml -->

### 請求

`GET https://api.demdex.com/v1/taxonomies/0/`

### 回應

截斷捷徑。

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

## Return Taxonomic Sub-Categories {#return-taxonomy-sub-categories}

A `GET` method that returns sub-categories for the specified parent category in an array.

<!-- r_rest_api_taxonomy_sub.xml -->

### 請求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### 回應

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist. 截斷捷徑。

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
