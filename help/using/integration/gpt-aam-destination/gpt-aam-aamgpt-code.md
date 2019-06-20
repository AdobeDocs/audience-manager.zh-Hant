---
description: Aamgpt是一個JavaScript函數，可讀取Audience Manager Cookie資料，並將該資訊傳送至Google Publisher標記。
seo-description: Aamgpt是一個JavaScript函數，可讀取Audience Manager Cookie資料，並將該資訊傳送至Google Publisher標記。
seo-title: Google Publisher標記的Audience Manager代碼
solution: Audience Manager
title: Google Publisher標記的Audience Manager代碼
uuid: 24ff5d16-b360-46cc-a4 c6-6db34 d7 fda75
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Audience Manager Code for Google Publisher Tags {#audience-manager-code-for-google-publisher-tags}

`AamGpt` is a [!DNL JavaScript] function that read Audience Manager cookie data and send that information to [!DNL Google Publisher Tags].

>[!NOTE]
>
>This function is not required if you have your own code to read Audience Manager cookie data from the [!UICONTROL UUID] and destination cookies.

## 程式碼範例

`AamGpt` 將程式碼放在頁面最上方，最好在 `<head>` 程式碼區塊內。`AamGpt` 程式碼如下：

```js
var AamGpt = {  
 strictEncode: function(str){ 
  return encodeURIComponent(str).replace(/[!'()]/g, escape).replace(/\*/g, "%2A"); 
 }, 
 getCookie: function(c_name) 
 { 
  var i,x,y,c=document.cookie.split(";"); 
  for (i=0;i<c.length;i++) 
  { 
   x=c[i].substr(0,c[i].indexOf("=")); 
   y=c[i].substr(c[i].indexOf("=")+1); 
   x=x.replace(/^\s+|\s+$/g,""); 
   if (x==c_name) 
   { 
    return unescape(y); 
   } 
  } 
 }, 
 getKey: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[0] != "undefined" && cList[0].match(/\w+/)) 
   { 
    return cList[0]; 
   } 
  }  
 }, 
 getValues: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D\w+/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[1] != "undefined" && cList[1].match(/\w+/)) 
   { 
    var vList=cList[1].split("%2C"); 
    if(typeof vList[0] != "undefined") 
    { 
     return vList; 
    } else { 
     return null; 
    }    
   } else { 
    return null; 
   } 
  } else { 
   return null; 
  } 
 } 
};
```
