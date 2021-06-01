---
description: DIL及其運作方式的概觀。
seo-description: DIL及其運作方式的概觀。
seo-title: 瞭解 Data Integration Library (DIL)
keywords: 'dil、dil、dil、dil、dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil、 dil '
solution: Audience Manager
title: 瞭解 Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL實作
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 17%

---

# 了解[!DNL Data Integration Library](DIL){#understanding-the-data-integration-library-dil}

[!DNL Audience Manager DIL]程式碼程式庫中提供的概述、快速入門和程式碼方法。

>[!IMPORTANT]
>
>從8.0版（2018年8月發行）開始，[!UICONTROL DIL]硬性相依於[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html)、3.3版或更新版本。 仰賴[!DNL ID Service]來引發ID同步和URL目的地。 如果[!DNL ID Service]缺少、舊或未配置，則會出錯。
>
>建議您使用[!DNL Adobe Experience Platform Launch]來實作及管理[!DNL DIL]和[!DNL Adobe Experience Platform Identity Service]程式庫。

不過，您也可以從GitHub頁面下載最新Experience Cloud和[!DNL DIL]版本。 請參閱下列下載連結：

* 下載[Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下載[DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL目的{#purpose-dil}

[!UICONTROL DIL] 是API程式庫。您可以將其視為[!DNL Adobe Audience Manager]的協助程式碼內文。 您不需要使用[!DNL Audience Manager]，但[!UICONTROL DIL]提供的方法和函式表示您不需要開發自己的程式碼，即可將資料傳送至[!DNL Audience Manager]。 此外，[!UICONTROL DIL]與[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)所提供的API不同。 該服務旨在管理不同[!DNL Experience Cloud]解決方案間的訪客身分識別。 相較之下， [!UICONTROL DIL]的設計目的為：

* 進行事件呼叫並傳送資料至[資料收集伺服器](../reference/system-components/components-data-collection.md)。
* 將資料傳送至[destinations](../features/destinations/destinations.md)。

## 取得並實作DIL程式碼{#get-implement-dil-code}

[!UICONTROL DIL] 程式碼可從這裡 **[下載](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。請注意，從8.0版（2018年8月發行）開始，[!UICONTROL DIL]嚴格依賴[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)、3.3版或更新版本。 仰賴[!DNL ID Service]來引發ID同步和[!DNL URL destinations]。 如果[!DNL ID Service]缺少、舊或未配置，則會出錯。

我們建議您改用[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html)，而不要手動使用[!UICONTROL DIL]並設定[!DNL Audience Manager]。 [!DNL Adobe Experience Platform Launch] 是建議的實作工具，因為可簡化程式碼部署、放置和版本管理。深入閱讀[!DNL Adobe Experience Platform Launch]中[Audience Manager擴展](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html)的相關資訊。

## 呼叫範例{#sample-code}

[!UICONTROL DIL] 在事件呼叫 [!DNL Audience Manager] 中將資料傳送至。事件呼叫是來自您頁面的XML HTTP要求。 它會使用`POST`方法，在要求內文中傳送資料。

| 事件呼叫元素 | 說明 |
|--- |--- |
| URL | DIL事件呼叫使用下列語法：`https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 內文 | 如下列範例所示，DIL會以機碼值組的形式傳遞資料。 特殊首碼字元將機碼值組識別為Audience Manager或合作夥伴變數。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
