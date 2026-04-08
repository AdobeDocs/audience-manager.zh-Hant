---
description: 可讓您檢視Audience Manager一般分類法的方法。 此選擇性分類配置會將特徵組織成業界標準類別。
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: 分類API方法
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
TQID: https://experienceleague.adobe.com/LIHEWvF3t-VNHJEviomvCF-dxE2Jy-BFxBynonvwP3w
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
topic_v2: id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 1%

---

# 分類API方法 {#taxonomic-api-methods}

可讓您檢視Audience Manager一般分類法的方法。 此選擇性分類配置會將特徵組織成業界標準類別。

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>您無法使用這些方法建立新的分類類別或分類特徵。 若要分類特徵，請使用特徵建立或更新方法來指定適當的`categoryId`。

## 傳回特定分類法 {#return-specific-taxonomy}

傳回指定分類類別相關詳細資料的`GET`方法。

<!-- r_rest_api_taxonomy.xml -->

### 請求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### 回應

成功的回應會傳回`200 OK`和指定識別碼的類別。 如果識別碼不存在，失敗的要求會傳回`404 No Content`。

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

## 傳回所有分類類別 {#return-all-taxonomy-categories}

傳回陣列中最上層類別清單的`GET`方法。

<!-- r_rest_api_taxonomies.xml -->

### 請求

`GET https://api.demdex.com/v1/taxonomies/0/`

### 回應

為簡短起見，已截斷。

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

## 傳回分類子類別 {#return-taxonomy-sub-categories}

傳回陣列中指定父類別之子類別的`GET`方法。

<!-- r_rest_api_taxonomy_sub.xml -->

### 請求

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### 回應

成功的回應會傳回`200 OK`和指定識別碼的類別。 如果識別碼不存在，失敗的要求會傳回`404 No Content`。 為簡短起見，已截斷。

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
