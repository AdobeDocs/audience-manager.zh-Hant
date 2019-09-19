---
description: DART Enterprise（及其他目標類型）擷取Audience Manager唯一使用者ID(UUID)值所需的程式碼。
seo-description: DART Enterprise（及其他目標類型）擷取Audience Manager唯一使用者ID(UUID)值所需的程式碼。
seo-title: get_aamCookie代碼
solution: Audience Manager
title: get_aamCookie代碼
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` 程式碼 {#get-aamcookie-code}

擷取Audience manager獨 [!DNL DART Enterprise] 特使用者ID()值所需的程式碼(及其他目標類[!DNL UUID]型)。

在頁面頂端定義此函式，最好是在程式碼區 `<head>` 塊內。

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
