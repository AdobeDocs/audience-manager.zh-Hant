---
description: 擷取合作夥伴專屬的DIL實例。
keywords: 觀眾管理員API；aam api；觀眾經理API；aam apis
seo-description: 擷取合作夥伴專屬的DIL實例。
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9ff-14c0-4c74-b6 b9-d6 b38513 d487
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# getDil{#getdil}

擷取合作夥伴專屬的DIL實例。

**函數簽名：**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 參數

| 名稱 | 類型 | 說明 |
|---|---|---|
| `partner` | 字串 | 要搜尋的合作夥伴名稱。 |
| `containerNSID` | 整數 | Defaults is `0`. 您正在搜尋之容器的NSID。選填。 |

## 回應

A successful partner and container NSID match returns a partner-specific [!UICONTROL DIL] instance. If there is no match, the API returns (does not throw) an error with the message, &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## 程式碼範例

<pre class="java"><code>DIL. getDil('<i>partner</i>'， <i>containInnsID</i>)；
DIL. getDil('<i>partner</i>')；</code>
</pre>
