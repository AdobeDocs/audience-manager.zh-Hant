---
description: DART Enterprise（和其他目的地類型）用於捕獲Audience Manager不重複用戶ID(UUID)值所需的代碼。
seo-description: DART Enterprise（和其他目的地類型）用於捕獲Audience Manager不重複用戶ID(UUID)值所需的代碼。
seo-title: get_aamCookie 程式碼
solution: Audience Manager
title: get_aamCookie 程式碼
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: 目的地基本知識
exl-id: 66e61a4b-908e-4950-8953-37a9920b67b5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 9%

---

# `get_aamCookie` 程式碼 {#get-aamcookie-code}

[!DNL DART Enterprise]（和其他目標類型）用於捕獲Audience Manager唯一用戶ID([!DNL UUID])值的代碼。

在頁面頂端定義此函式，最好在`<head>`程式碼區塊內。

<!-- r_aam_de_cookie.xml -->

```js
<script type="text/javascript">
function get_aamCookie (c_name)
{
var i,x,y,ARRcookies=document.cookie.split(";");
for (i=0;i<ARRcookies.length;i++)
   {
   x=ARRcookies[i].substr(0,ARRcookies[i].indexOf("="));
   y=ARRcookies[i].substr(ARRcookies[i].indexOf("=")+1);
   x=x.replace(/^\s+|\s+$/g,"");
   if (x==c_name)
      { 
      return unescape(y);
      }
   }
}
</script>
```
