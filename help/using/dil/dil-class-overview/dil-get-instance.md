---
description: 檢索特定於合作夥伴的DIL實例。
keywords: 受眾管理器api;aam api；受眾管理器apis;aam apis
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 15%

---

# getDil{#getdil}

檢索特定於合作夥伴的DIL實例。

**函式簽名：** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 參數

| 名稱 | 類型 | 說明 |
|---|---|---|
| `partner` | 字串 | 要搜索的合作夥伴名稱。 |
| `containerNSID` | 整數 | 預設值是 `0`。 要搜索的容器的NSID。 選填。 |

## 回應

成功的合作夥伴和容器NSID匹配返回特定於合作夥伴的 [!UICONTROL DIL] 實例。 如果沒有匹配項，API將返回（不引發）消息錯誤， `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## 程式碼範例

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
