---
description: AamGpt是JavaScript函式，可讀取Audience ManagerCookie資料並將該資訊傳送至Google Publisher標籤。
seo-description: AamGpt是JavaScript函式，可讀取Audience ManagerCookie資料並將該資訊傳送至Google Publisher標籤。
seo-title: 適用於 Google 發佈商廣告代碼的 Audience Manager 代碼
solution: Audience Manager
title: 適用於 Google 發佈商廣告代碼的 Audience Manager 代碼
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
feature: Third-party Integration
exl-id: 04e74399-7b6a-400e-a1e6-94fe296e7209
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 19%

---

# 適用於 Google 發佈商廣告代碼的 Audience Manager 代碼 {#audience-manager-code-for-google-publisher-tags}

`AamGpt` 是讀取 [!DNL JavaScript] Audience ManagerCookie資料並將該資訊傳送至的函式 [!DNL Google Publisher Tags]。

>[!NOTE]
>
>如果您有自己的程式碼從[!UICONTROL UUID]和目標Cookie讀取Audience ManagerCookie資料，則不需要此函式。

## 程式碼範例

將`AamGpt`程式碼放在頁面頂端，最好是放在`<head>`程式碼區塊內。 `AamGpt`程式碼提供如下：

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
