---
description: 概述DIL及其運作方式。
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: 瞭解 Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 10%

---

# 瞭解 [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 副檔名。
><br><br>
>現有客戶可繼續使用其 [!DNL DIL] 實作。 不過，Adobe將不會開發 [!DNL DIL] 超越此點。 建議客戶評估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 長期資料收集策略的影響。
><br><br>
>2023年7月後想要實作新資料收集整合的客戶應使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而非。

概述、快速入門和提供的程式碼方法 [!DNL Audience Manager DIL] 程式碼程式庫。

>[!IMPORTANT]
>
>從8.0版（2018年8月發行）開始， [!UICONTROL DIL] 對有硬性相依性 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)，版本3.3或更新版本。 此服務仰賴 [!DNL ID Service] 引發ID同步和URL目的地。 如果發生以下情況，則會發生錯誤 [!DNL ID Service] 遺失、過時或未設定。
>
>我們建議您使用 [!DNL Adobe Experience Platform Tags] 實作與管理 [!DNL DIL] 和 [!DNL Adobe Experience Platform Identity Service] 程式庫。

不過，您也可以下載最新的Experience Cloud和 [!DNL DIL] GitHub頁面的發行版本。 請參閱下列下載連結：

* 下載 [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下載 [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL目的 {#purpose-dil}

[!UICONTROL DIL] 是API程式庫。 您可以將它視為以下專案的協助程式程式碼內文： [!DNL Adobe Audience Manager]. 不需要使用 [!DNL Audience Manager]，但方法和函式 [!UICONTROL DIL] 提供表示您不需要開發自己的程式碼即可將資料傳送至 [!DNL Audience Manager]. 此外， [!UICONTROL DIL] 與提供的API不同 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). 該服務旨在管理不同訪客的身分識別 [!DNL Experience Cloud] 解決方案。 對比之下， [!UICONTROL DIL] 專門設計用於：

* 進行事件呼叫並將資料傳送至 [資料收集伺服器](../reference/system-components/components-data-collection.md).
* 傳送資料至 [目的地](../features/destinations/destinations.md).

## 取得和實作DIL程式碼 {#get-implement-dil-code}

[!UICONTROL DIL] 程式碼可供下載 **[此處](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. 請注意，從8.0版（於2018年8月發行）開始， [!UICONTROL DIL] 對有硬性相依性 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)，版本3.3或更新版本。 此服務仰賴 [!DNL ID Service] 引發ID同步和 [!DNL URL destinations]. 如果發生以下情況，則會發生錯誤 [!DNL ID Service] 遺失、過時或未設定。

而不是搭配使用 [!UICONTROL DIL] 和設定 [!DNL Audience Manager] 手動，我們建議您使用 [Adobe Experience Platform標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) 而非。 [!DNL Adobe Experience Platform Tags] 是建議的實作工具，因為它可簡化程式碼部署、放置和版本管理。 深入瞭解 [Audience Manager延伸模組](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) 在 [!DNL Adobe Experience Platform Tags].

## 呼叫範例 {#sample-code}

[!UICONTROL DIL] 傳送資料至 [!DNL Audience Manager] 在事件呼叫中。 事件呼叫是來自頁面的XML HTTP要求。 它使用 `POST` 在要求內文中傳送資料的方法。

| 事件呼叫元素 | 說明 |
|--- |--- |
| URL | DIL事件呼叫使用以下語法： `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 內文 | 如下列範例所示，DIL會以索引鍵值配對的形式傳遞資料。 特殊首碼字元會將機碼值組識別為Audience Manager或合作夥伴變數。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

另請參閱：
* [關鍵變數的前置詞要求](../features/traits/trait-variable-prefixes.md)
* [DCS API 呼叫的支援屬性。](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 相關連結

* [DIL 使用案例和程式碼範例](/help/using/dil/dil-use-cases.md)
* [類別層級 DIL 方法](/help/using/dil/dil-class-overview/dil-start.md)
* [例項層級 DIL 方法](/help/using/dil/dil-instance-methods.md)
* [DIL 模組](/help/using/dil/dil-modules.md)
* [DIL 工具](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
