---
description: 網域管理方法，可讓您建立並管理您要傳送資料的網域（僅限Cookie目的地）。
seo-description: 網域管理方法，可讓您建立並管理您要傳送資料的網域（僅限Cookie目的地）。
seo-title: 網域管理 API 方法
solution: Audience Manager
title: 網域管理 API 方法
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 6%

---


# 網域管理 API 方法 {#domain-management-api-methods}

網域管理方法，可讓您建立並管理您要傳送資料的網域（僅限Cookie目的地）。

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

可讓您 `POST` 建立新網域的方法（僅限Cookie目的地）。

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

成功的回應會傳 `201 created` 回合作夥伴網站，包括其唯一ID。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 刪除域 {#delete-domain}

可讓 `DELETE` 您移除網域的方法（僅限Cookie目的地）。

<!-- r_delete_partner_site.xml -->

### 請求

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### 回應

成功的回應會傳回 `204 no content`。 如果 `404 not found` 找不到合作夥伴站點，則返回。

## 域的返回屬性 {#return-props-domain}

傳回 `GET` 指定網域的詳細資料的方法（僅適用於Cookie目的地）。

<!-- r_get_partner_site.xml -->

### 請求

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### 回應

成功的回應會傳 `200 OK` 回資料，如下列範例所示。 如果 `404 Not found` 找不到網站ID或合作夥伴，則傳回。

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## 所有網域的傳回屬性 {#return-props-all-domains}

傳回 `GET` 您所有網域的相關資訊的方法（僅適用於Cookie目的地）。

<!-- r_get_partner_sites.xml -->

### 請求

`GET https://api.demdex.com/v1/partner-sites/`

### 可選查詢參數

您可將這些可選參數與傳 [!DNL API] 回物件所 *有屬性* 的方法搭配使用。 將查詢傳入請求字串中時，請在請求字串中設定這些選項 [!DNL API]。 請參 [閱可選參數](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)。

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
   <td colname="col2"> 設定請求傳回的回應結果數目（預設為10）。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> 根據指定的JSON屬性排序並傳回結果。 </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 以遞減順序排序和傳回結果。 預設為遞增。 </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">根據您要用作搜尋參數的指定字串傳回結果。 例如，假設您想要在該項目的任何值欄位中，尋找具有「測試」字詞的所有模型的結果。 您的範例要求可能如下所示： <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>實施流量分類。 </p> <p>您可以搜尋「get all」方法傳回的任何值。 </p> </td>
  </tr> 
 </tbody> 
</table>

### 回應

成功的響應 `200 OK` 返回陣列中的資料，如下例所示。 如果 `404 Not found` 找不到網站ID或合作夥伴，則傳回。

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
