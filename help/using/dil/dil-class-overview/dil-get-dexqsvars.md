---
description: 從廣告伺服器擷取特定值。
seo-description: 從廣告伺服器擷取特定值。
seo-title: DexgetQSVars
solution: Audience Manager
title: DexgetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343db047e
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# dexGetQSVars{#dexgetqsvars}

從廣告伺服器擷取特定值。

**函數簽名：**`dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `variableName` | 字串 | 要取得值的變數名稱。 |
| `partner` | 字串 | 要搜尋的合作夥伴名稱。 |
| `containerNSID` | 整數 | The [!DNL NSID] of the container you're searching for. Defaults is `0`. |

**回應**

Returns the variable value for a [!UICONTROL DIL] instance.

**程式碼範例**

<pre class="java"><code>var value= DIL. exdetQQsVars('<i>variableName</i>'，'<i>parterName</i>'，<i>containerNSID</i>)；</code>
</pre>
