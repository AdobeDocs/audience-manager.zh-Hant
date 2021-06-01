---
description: 擷取合作夥伴專屬的DIL例項。
keywords: audience manager api;aam api;audience manager api;aam api
seo-description: 擷取合作夥伴專屬的DIL例項。
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL實作
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%

---

# getDil{#getdil}

擷取合作夥伴專屬的DIL例項。

**函式簽名：** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 參數

| 名稱 | 類型 | 說明 |
|---|---|---|
| `partner` | 字串 | 要搜索的合作夥伴名稱。 |
| `containerNSID` | 整數 | 預設值為`0`。 您要搜尋的容器的NSID。 選填。 |

## 回應

成功的合作夥伴和容器NSID比對會傳回合作夥伴專屬的[!UICONTROL DIL]例項。 如果沒有相符項目，API會傳回（未擲回）訊息「 `The DIL instance with partner <name> and containerNSID <ID> was not found.`」的錯誤

## 程式碼範例

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
