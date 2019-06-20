---
description: DART Enterprise(和其他目的地類型)所需的程式碼，以擷取Audience Manager唯一使用者ID(UUID)值。
seo-description: DART Enterprise(和其他目的地類型)所需的程式碼，以擷取Audience Manager唯一使用者ID(UUID)值。
seo-title: get_ aamCookie Code
solution: Audience Manager
title: get_ aamCookie Code
uuid: 89c30Fe3-dobe6-4d18-b161-104167d75 bcd
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` 程式碼 {#get-aamcookie-code}

Code required by [!DNL DART Enterprise] (and other destination types) to capture the Audience Manager unique user ID ([!DNL UUID]) value.

Define this function at the top of the page, ideally within the `<head>` code block.

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
