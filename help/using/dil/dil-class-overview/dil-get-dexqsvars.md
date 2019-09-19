---
description: 從廣告伺服器擷取特定值。
seo-description: 從廣告伺服器擷取特定值。
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# dexGetQSVars{#dexgetqsvars}

從廣告伺服器擷取特定值。

**** 函式簽名： `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `variableName` | 字串 | 您要取得值的變數名稱。 |
| `partner` | 字串 | 要搜索的合作夥伴名稱。 |
| `containerNSID` | 整數 | 您 [!DNL NSID] 正在搜尋的容器。 預設值 `0`為。 |

**回應**

傳回例項的變數 [!UICONTROL DIL] 值。

**程式碼範例**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
