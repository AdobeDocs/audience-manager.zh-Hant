---
description: 擷取合作夥伴特定的DIL例項。
keywords: audience manager api；aam api；audience manager api；aam api
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%

---

# getDil{#getdil}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 副檔名。
><br><br>
>現有客戶可繼續使用其 [!DNL DIL] 實作。 不過，Adobe將不會開發 [!DNL DIL] 超越此點。 建議客戶評估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 長期資料收集策略的影響。
><br><br>
>2023年7月後想要實作新資料收集整合的客戶應使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而非。

擷取合作夥伴特定的DIL例項。

**函式簽章：** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 參數

| 名稱 | 類型 | 說明 |
|---|---|---|
| `partner` | 字串 | 要搜尋的合作夥伴名稱。 |
| `containerNSID` | 整數 | 預設值為 `0`. 您要搜尋之容器的NSID。 選填。 |

## 回應

成功的合作夥伴和容器NSID相符專案會傳回特定於合作夥伴的專案 [!UICONTROL DIL] 執行個體。 如果沒有相符專案，API會傳回（不會擲回）錯誤訊息， 」 `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## 程式碼範例

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
