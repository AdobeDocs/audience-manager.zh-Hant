---
description: DIL及其運作方式的概觀。
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: 'dil、dil、dil、dil、dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil '
solution: Audience Manager
title: 瞭解 Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 11%

---

# 了解 [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

概述、快速入門，以及 [!DNL Audience Manager DIL] 程式碼程式庫。

>[!IMPORTANT]
>
>從8.0版開始（2018年8月發行）, [!UICONTROL DIL] 對 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), 3.3版或更新版本。 它依賴 [!DNL ID Service] 以引發ID同步和URL目的地。 若 [!DNL ID Service] 缺少、舊或未配置。
>
>建議您使用 [!DNL Adobe Experience Platform Tags] 實作和管理 [!DNL DIL] 和 [!DNL Adobe Experience Platform Identity Service] 程式庫。

不過，您也可以下載最新Experience Cloud和 [!DNL DIL] 發佈於GitHub頁面。 請參閱下列下載連結：

* 下載 [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下載 [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL {#purpose-dil}

[!UICONTROL DIL] 是API程式庫。 您可以將其視為 [!DNL Adobe Audience Manager]. 不需要使用 [!DNL Audience Manager]，但方法和函式 [!UICONTROL DIL] 提供表示您不需要開發自己的程式碼即可將資料傳送至 [!DNL Audience Manager]. 此外， [!UICONTROL DIL] 與 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). 該服務旨在管理不同訪客身分 [!DNL Experience Cloud] 解決方案。 相反， [!UICONTROL DIL] 設計用於：

* 進行事件呼叫，並將資料傳送至 [資料收集伺服器](../reference/system-components/components-data-collection.md).
* 將資料傳送至 [目的地](../features/destinations/destinations.md).

## 取得與實作DIL程式碼 {#get-implement-dil-code}

[!UICONTROL DIL] 代碼可供下載 **[此處](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. 請注意，從8.0版開始（2018年8月發行）, [!UICONTROL DIL] 對 [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), 3.3版或更新版本。 它依賴 [!DNL ID Service] 觸發ID同步和 [!DNL URL destinations]. 若 [!DNL ID Service] 缺少、舊或未配置。

而不是搭配 [!UICONTROL DIL] 和設定 [!DNL Audience Manager] 手動，建議您使用 [Adobe Experience Platform標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) 。 [!DNL Adobe Experience Platform Tags] 是建議的實作工具，因為可簡化程式碼部署、放置和版本管理。 深入了解 [Audience Manager擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) in [!DNL Adobe Experience Platform Tags].

## 呼叫範例 {#sample-code}

[!UICONTROL DIL] 將資料傳送至 [!DNL Audience Manager] 在事件呼叫中。 事件呼叫是來自您頁面的XML HTTP要求。 它使用 `POST` 方法，在要求內文中傳送資料。

| 事件呼叫元素 | 說明 |
|--- |--- |
| URL | DIL事件呼叫使用下列語法： `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 內文 | 如下列範例所示，DIL會以機碼值組的形式傳遞資料。 特殊首碼字元會將機碼值組識別為Audience Manager或合作夥伴變數。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
