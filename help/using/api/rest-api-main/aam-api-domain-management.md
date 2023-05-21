---
description: 域管理方法，用於建立和管理要向其發送資料的域（僅適用於Cookie目標）。
seo-description: Domain management methods that let you create and manage the domains to which you want to send data (for cookie destinations only).
seo-title: Domain Management API Methods
solution: Audience Manager
title: 網域管理 API 方法
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 5%

---

# 網域管理 API 方法 {#domain-management-api-methods}

域管理方法，用於建立和管理要向其發送資料的域（僅適用於Cookie目標）。

<!-- c_partner_site.xml -->

## 建立新域 {#create-new-domain}

A `POST` 用於為（僅cookie目標）建立新域的方法。

<!-- r_post_new_partner_site.xml -->

### 請求

`POST` `https://api.demdex.com/v1/partner-sites/`

### 範例要求

```
{
   "url":"example1.com"
}
```

### 回應

成功的響應返回 `201 created` 以及合作夥伴站點，包括其唯一ID。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 刪除域 {#delete-domain}

A `DELETE` 用於刪除域（僅用於cookie目標）的方法。

<!-- r_delete_partner_site.xml -->

### 請求

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 回應

成功的響應返回 `204 no content`。 返回 `404 not found` 找不到合作夥伴站點。

## 返回域的屬性 {#return-props-domain}

A `GET` 返回有關指定域的詳細資訊的方法（僅適用於cookie目標）。

<!-- r_get_partner_site.xml -->

### 請求

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 回應

成功的響應返回 `200 OK` 和以下示例中所示的資料。 返回 `404 Not found` 找不到站點ID或合作夥伴。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 返回所有域的屬性 {#return-props-all-domains}

A `GET` 返回有關所有域的資訊（僅適用於cookie目標）的方法。

<!-- r_get_partner_sites.xml -->

### 請求

`GET https://api.demdex.com/v1/partner-sites/`

### 可選查詢參數

可將這些可選參數與 [!DNL API] 返回的方法 *全部* 對象的屬性。 將查詢傳遞到 [!DNL API]。 請參閱 [可選參數](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)。

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td> 
   <td colname="col2"> 按頁碼返回結果。 編號從0開始。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> 設定請求返回的響應結果數（預設值為10）。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> 根據指定的JSON屬性對結果排序並返回結果。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 按降序排序並返回結果。 升序為預設值。 </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">根據要用作搜索參數的指定字串返回結果。 例如，假設您要查找所有模型的結果，這些模型在該項目的任何值欄位中都使用「Test」一詞。 您的示例請求可能如下所示： <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>實施流量分類。 </p> <p>可以搜索「get all」方法返回的任何值。 </p> </td>
  </tr> 
 </tbody> 
</table>

### 回應

成功的響應返回 `200 OK` 和陣列中的資料，如下例所示。 返回 `404 Not found` 找不到站點ID或合作夥伴。

```
[
    {
        "pid": 1111,
        "siteId": 111,
        "url": "example1.com"
    },
    {
        "pid": 2222,
        "siteId": 222,
        "url": "example2.com"
    },
    {
        "pid": 3333,
        "siteId": 333,
        "url": "example3.com"
    }
]
```
