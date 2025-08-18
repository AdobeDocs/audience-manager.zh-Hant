---
description: 概述DIL及其運作方式。
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: 瞭解Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 1%

---

# 瞭解[!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>自2023年7月起，Adobe已停止開發[!DNL Data Integration Library (DIL)]和[!DNL DIL]擴充功能。
>
>現有客戶可以繼續使用其[!DNL DIL]實作。 不過，Adobe不會在此時間點之後開發[!DNL DIL]。 建議客戶針對[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant)的長期資料收集策略進行評估。
>
>如果客戶希望在2023年7月之後實作新的資料收集整合，應改用[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hant)。

[!DNL Audience Manager DIL]程式碼程式庫中可用的概述、快速入門和程式碼方法。

>[!IMPORTANT]
>
>從8.0版（於2018年8月發行）開始，[!UICONTROL DIL]對[Adobe Experience Platform Identity服務](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant) 3.3版或更新版本有硬性相依性。 它仰賴[!DNL ID Service]引發ID同步和URL目的地。 如果[!DNL ID Service]遺失、過時或未設定，則會發生錯誤。
>
>我們建議您使用[!DNL Adobe Experience Platform Tags]來實作及管理您的[!DNL DIL]與[!DNL Adobe Experience Platform Identity Service]資料庫。

不過，您也可以從我們的GitHub頁面下載最新的Experience Cloud和[!DNL DIL]版本。 請參閱下列下載連結：

* 下載[Adobe Experience Platform Identity服務](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下載[DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL的目的 {#purpose-dil}

[!UICONTROL DIL]是API程式庫。 您可以將它視為[!DNL Adobe Audience Manager]的協助程式程式碼內文。 不一定要使用[!DNL Audience Manager]，但[!UICONTROL DIL]提供的方法和函式表示您不需要開發自己的程式碼即可將資料傳送至[!DNL Audience Manager]。 此外，[!UICONTROL DIL]與[Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant)提供的API不同。 此服務的設計用途是管理不同[!DNL Experience Cloud]解決方案中的訪客身分識別。 相較之下，[!UICONTROL DIL]的設計目的是：

* 進行事件呼叫並將資料傳送至[資料收集伺服器](../reference/system-components/components-data-collection.md)。
* 傳送資料至[目的地](../features/destinations/destinations.md)。

## 取得和實作DIL程式碼 {#get-implement-dil-code}

[!UICONTROL DIL]程式碼可在&#x200B;**[這裡](https://github.com/Adobe-Marketing-Cloud/dil/releases)**&#x200B;下載。 請注意，從8.0版（於2018年8月發行）開始，[!UICONTROL DIL]對[Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant) 3.3版或更新版本有硬性相依性。 它仰賴[!DNL ID Service]引發ID同步和[!DNL URL destinations]。 如果[!DNL ID Service]遺失、過時或未設定，則會發生錯誤。

建議您改用[!UICONTROL DIL]Adobe Experience Platform標籤[!DNL Audience Manager]，而不要使用[並手動設定](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hant)。 [!DNL Adobe Experience Platform Tags]是建議的實作工具，因為它可簡化程式碼部署、放置和版本管理。 深入瞭解[中的](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=zh-Hant)Audience Manager擴充功能[!DNL Adobe Experience Platform Tags]。

## 呼叫範例 {#sample-code}

[!UICONTROL DIL]在事件呼叫中將資料傳送至[!DNL Audience Manager]。 事件呼叫是來自頁面的XML HTTP要求。 它使用`POST`方法在要求內文中傳送資料。

| 事件呼叫元素 | 說明 |
|--- |--- |
| URL | DIL事件呼叫使用以下語法： `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 內文 | 如下列範例所示，DIL會以索引鍵值配對的形式傳遞資料。 特殊首碼字元將機碼值組識別為Audience Manager或合作夥伴變數。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

另請參閱：
* [關鍵變數的前置詞要求](../features/traits/trait-variable-prefixes.md)
* [DCS API呼叫的支援屬性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 相關連結

* [DIL使用案例和程式碼範例](/help/using/dil/dil-use-cases.md)
* [類別層級DIL方法](/help/using/dil/dil-class-overview/dil-start.md)
* [例項層級DIL方法](/help/using/dil/dil-instance-methods.md)
* [DIL模組](/help/using/dil/dil-modules.md)
* [DIL工具](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
