---
description: 網域管理方法，可讓您建立和管理您要傳送資料的網域(僅限Cookie目的地)。
seo-description: 網域管理方法，可讓您建立和管理您要傳送資料的網域(僅限Cookie目的地)。
seo-title: 網域管理API方法
solution: Audience Manager
title: 網域管理API方法
uuid: f2f08bc5-ea42-4171-9a43-0b20976 f0 cb0
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Domain Management API Methods {#domain-management-api-methods}

網域管理方法，可讓您建立和管理您要傳送資料的網域(僅限Cookie目的地)。

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

A `POST` method that lets you create a new domain for (cookie destinations only).

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

A successful response returns `201 created` and the partner site, including its unique ID.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Delete a Domain {#delete-domain}

A `DELETE` method that lets you remove a domain (for cookie destinations only).

<!-- r_delete_partner_site.xml -->

### 請求

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 回應

A successful response returns `204 no content`. Returns `404 not found` if the partner site cannot be found.

## Return Properties for a Domain {#return-props-domain}

A `GET` method that returns details about the specified domain (for cookie destinations only).

<!-- r_get_partner_site.xml -->

### 請求

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 回應

A successful response returns `200 OK` and data as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Return Properties for all Domains {#return-props-all-domains}

A `GET` method that returns information about all your domains (for cookie destinations only).

<!-- r_get_partner_sites.xml -->

### 請求

`GET https://api.demdex.com/v1/partner-sites/`

### 選擇性查詢參數

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See [Optional Parameters](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> 依頁碼傳回結果。編號開始於0。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> 設定請求傳回的回應結果數(預設為10)。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> SortBy</code> </td> 
   <td colname="col2"> 根據指定的JSON屬性排序並傳回結果。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> 遞減遞減</code> </td>
   <td colname="col2"> 排序並傳回結果遞減順序。遞增是預設值。 </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">根據您要用作搜尋參數的指定字串傳回結果。例如，假設您想尋找所有該項目值欄位中字詞「Test」的所有模型的結果。您的範例請求可能類似於： <p><code> 「GET''https://api.demdex.com/v1/models/?search=Test</code>'。 </p> <p>您可以搜尋「get all」方法傳回的任何值。 </p> </td>
  </tr> 
 </tbody> 
</table>

### 回應

A successful response returns `200 OK` and data in an array as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

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
