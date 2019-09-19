---
description: 擷取合作夥伴專屬的DIL例項。
keywords: audience manager api;aam api;audience manager apis;aam api
seo-description: 擷取合作夥伴專屬的DIL例項。
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# getDil{#getdil}

擷取合作夥伴專屬的DIL例項。

**** 函式簽名： `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 參數

| 名稱 | 類型 | 說明 |
|---|---|---|
| `partner` | 字串 | 要搜索的合作夥伴名稱。 |
| `containerNSID` | 整數 | 預設值 `0`為。 您要搜尋的容器的NSID。 選填。 |

## 回應

成功的合作夥伴和容器NSID符合會傳回合作夥伴特定的 [!UICONTROL DIL] 例項。 如果沒有相符項目，API會傳回（不擲出）訊息「 `The DIL instance with partner <name> and containerNSID <ID> was not found.`」

## 程式碼範例

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>);
DIL.getDil('<i>partner</i>');</code></pre>
