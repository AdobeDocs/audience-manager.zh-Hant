---
description: 從廣告伺服器擷取特定值。
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVar
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
TQID: https://experienceleague.adobe.com/O8xeJARK4qVGj8SOXmO8OHLqfOcSPZZWvWoGad0Wji8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
subfeature_v2:
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 130
ht-degree: 7%

---

# dexGetQSVar{#dexgetqsvars}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發[!DNL Data Integration Library (DIL)]和[!DNL DIL]擴充功能。
>
>現有客戶可以繼續使用其[!DNL DIL]實作。 不過，Adobe不會在此時間點之後開發[!DNL DIL]。 建議客戶針對[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant)的長期資料收集策略進行評估。
>
>如果客戶希望在2023年7月之後實作新的資料收集整合，應改用[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant)。

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
| `containerNSID` | 整數 | 您正在搜尋的容器[!DNL NSID]。 預設值為`0`。 |

**回應**

傳回[!UICONTROL DIL]執行個體的變數值。

**程式碼範例**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
