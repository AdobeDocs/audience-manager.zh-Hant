---
description: 網域管理方法可讓您建立和管理要傳送資料的網域（僅適用於Cookie目的地）。
seo-description: Domain management methods that let you create and manage the domains to which you want to send data (for cookie destinations only).
seo-title: Domain Management API Methods
solution: Audience Manager
title: 網域管理API方法
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 2%

---

# 網域管理API方法 {#domain-management-api-methods}

網域管理方法可讓您建立和管理要傳送資料的網域（僅適用於Cookie目的地）。

<!-- c_partner_site.xml -->

## 建立新網域 {#create-new-domain}

`POST`方法可讓您為（僅限Cookie目的地）建立新網域。

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

成功的回應傳回`201 created`和合作夥伴網站，包括其唯一識別碼。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 刪除網域 {#delete-domain}

可讓您移除網域的`DELETE`方法（僅適用於Cookie目的地）。

<!-- r_delete_partner_site.xml -->

### 請求

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 回應

成功的回應傳回`204 no content`。 如果找不到夥伴網站，則傳回`404 not found`。

## 傳回網域的屬性 {#return-props-domain}

傳回指定網域相關詳細資料的`GET`方法（僅適用於Cookie目的地）。

<!-- r_get_partner_site.xml -->

### 請求

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 回應

成功的回應會傳回`200 OK`和資料，如下列範例所示。 如果找不到網站ID或夥伴，則傳回`404 Not found`。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 傳回所有網域的屬性 {#return-props-all-domains}

傳回您所有網域相關資訊的`GET`方法（僅適用於Cookie目的地）。

<!-- r_get_partner_sites.xml -->

### 請求

`GET https://api.demdex.com/v1/partner-sites/`

### 選擇性查詢引數

您可以使用這些選擇性引數搭配[!DNL API]方法，傳回物件的&#x200B;*所有*&#x200B;屬性。 將該查詢傳入[!DNL API]時，在要求字串中設定這些選項。 請參閱[選用引數](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)。

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
   <td colname="col2"> 依頁碼傳回結果。 編號從0開始。 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> 設定要求傳回的回應結果數目（預設為10）。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> 根據指定的JSON屬性排序並傳回結果。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 以遞減順序排序並傳回結果。 預設值為升序。 </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">根據您要用作搜尋引數的指定字串傳回結果。 例如，假設您想要尋找在該專案的任何值欄位中有「Test」字詞的所有模型的結果。 您的範例請求可能如下所示： <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>。 </p> <p>您可以搜尋"get all"方法傳回的任何值。 </p> </td>
  </tr> 
 </tbody> 
</table>

### 回應

成功的回應傳回`200 OK`和陣列中的資料，如下列範例所示。 如果找不到網站ID或夥伴，則傳回`404 Not found`。

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
