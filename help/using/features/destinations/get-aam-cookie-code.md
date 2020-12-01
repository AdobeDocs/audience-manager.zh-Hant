---
description: DART Enterprise（及其他目標類型）擷取Audience Manager唯一使用者ID(UUID)值所需的程式碼。
seo-description: DART Enterprise（及其他目標類型）擷取Audience Manager唯一使用者ID(UUID)值所需的程式碼。
seo-title: get_aamCookie 程式碼
solution: Audience Manager
title: get_aamCookie 程式碼
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 9%

---


# `get_aamCookie` 程式碼 {#get-aamcookie-code}

[!DNL DART Enterprise]（及其他目標類型）擷取Audience Manager唯一使用者ID([!DNL UUID])值所需的程式碼。

在頁面頂端定義此函式，最好是在`<head>`程式碼區塊內。

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
