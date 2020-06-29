---
description: 可讓您檢視Audience Manager常見分類法的方法。 此選擇性分類方案將特徵組織為業界標準類別。
seo-description: 可讓您檢視Audience Manager常見分類法的方法。 此選擇性分類方案將特徵組織為業界標準類別。
seo-title: 分類 API 方法
solution: Audience Manager
title: 分類 API 方法
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 7%

---


# 分類 API 方法 {#taxonomic-api-methods}

可讓您檢視Audience Manager常見分類法的方法。 此選擇性分類方案將特徵組織為業界標準類別。

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>您無法使用這些方法建立新的分類類別或分類特徵。 若要分類特徵，請使用特徵建 `categoryId` 立或更新方法指定適當。

## 返回特定分類 {#return-specific-taxonomy}

一種 `GET` 返回有關指定分類類別的詳細資訊的方法。

<!-- r_rest_api_taxonomy.xml -->

### 請求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### 回應

成功的回應 `200 OK` 會傳回指定ID的類別。 如果ID不存 `404 No Content` 在，則傳回不成功的請求。

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

一 `GET` 種返回陣列中頂級類別清單的方法。

<!-- r_rest_api_taxonomies.xml -->

### 請求

`GET https://api.demdex.com/v1/taxonomies/0/`

### 回應

因簡短性而截斷。

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

一種 `GET` 在陣列中返回指定父類別子類別的方法。

<!-- r_rest_api_taxonomy_sub.xml -->

### 請求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### 回應

成功的回應 `200 OK` 會傳回指定ID的類別。 如果ID不存 `404 No Content` 在，則傳回不成功的請求。 因簡短性而截斷。

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
