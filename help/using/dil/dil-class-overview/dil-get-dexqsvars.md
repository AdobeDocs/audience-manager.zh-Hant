---
description: 從廣告伺服器擷取特定值。
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 8%

---

# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 副檔名。
><br><br>
>現有客戶可繼續使用其 [!DNL DIL] 實作。 不過，Adobe將不會開發 [!DNL DIL] 超越此點。 建議客戶評估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 長期資料收集策略的影響。
><br><br>
>2023年7月後想要實作新資料收集整合的客戶應使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而非。

從廣告伺服器擷取特定值。

**函式簽章：** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**參數**

| 名稱 | 類型 | 說明 |
|---|---|---|
| `variableName` | 字串 | 您要為其取得值的變數名稱。 |
| `partner` | 字串 | 要搜尋的合作夥伴名稱。 |
| `containerNSID` | 整數 | 此 [!DNL NSID] 您正在搜尋的容器。 預設值為 `0`. |

**回應**

傳回 [!UICONTROL DIL] 執行個體。

**程式碼範例**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
