---
description: 可讓您建立及管理要將資料傳送至哪些網域的網域管理方法（僅適用於Cookie目的地）。
seo-description: 可讓您建立及管理要將資料傳送至哪些網域的網域管理方法（僅適用於Cookie目的地）。
seo-title: 網域管理 API 方法
solution: Audience Manager
title: 網域管理 API 方法
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 6%

---

# 網域管理 API 方法 {#domain-management-api-methods}

可讓您建立及管理要將資料傳送至哪些網域的網域管理方法（僅適用於Cookie目的地）。

<!-- c_partner_site.xml -->

## 建立新域{#create-new-domain}

`POST`方法可讓您為建立新網域（僅限Cookie目的地）。

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

成功的回應會傳回`201 created`和合作夥伴網站，包括其唯一ID。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 刪除域{#delete-domain}

`DELETE`方法可讓您移除網域（僅適用於Cookie目的地）。

<!-- r_delete_partner_site.xml -->

### 請求

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 回應

成功的響應返回`204 no content`。 如果找不到合作夥伴站點，則返回`404 not found`。

## 域{#return-props-domain}的返回屬性

`GET`方法可傳回指定網域的詳細資訊（僅適用於Cookie目的地）。

<!-- r_get_partner_site.xml -->

### 請求

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 回應

成功的回應會傳回`200 OK`和資料，如下列範例所示。 如果找不到網站ID或合作夥伴，則傳回`404 Not found`。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 返回所有域{#return-props-all-domains}的屬性

`GET`方法可傳回關於所有網域的資訊（僅適用於Cookie目的地）。

<!-- r_get_partner_sites.xml -->

### 請求

`GET https://api.demdex.com/v1/partner-sites/`

### 選用的查詢參數

您可以將這些可選參數與[!DNL API]方法搭配使用，這些方法會傳回物件的&#x200B;*all*&#x200B;屬性。 將查詢傳遞至[!DNL API]時，請在要求字串中設定這些選項。 請參閱[選用參數](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)。

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
   <td colname="col2"> 設定請求傳回的回應結果數（預設為10）。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> 根據指定的JSON屬性對結果進行排序和返回。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 按降序排序和返回結果。 預設為遞增。 </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">根據您要用作搜索參數的指定字串返回結果。 例如，假設您想在該項目的任何值欄位中，找到所有具有「Test」字詞之模型的結果。 您的範例要求可能如下所示： <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>實施流量分類。 </p> <p>您可以搜尋「get all」方法傳回的任何值。 </p> </td>
  </tr> 
 </tbody> 
</table>

### 回應

成功的回應會傳回`200 OK`和陣列中的資料，如下列範例所示。 如果找不到網站ID或合作夥伴，則傳回`404 Not found`。

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
