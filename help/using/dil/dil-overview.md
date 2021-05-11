---
description: 概觀DIL及其運作方式。
seo-description: 概觀DIL及其運作方式。
seo-title: 瞭解 Data Integration Library (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil '
solution: Audience Manager
title: 瞭解 Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL實作
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 17%

---

# 瞭解[!DNL Data Integration Library](DIL){#understanding-the-data-integration-library-dil}

[!DNL Audience Manager DIL]程式碼庫中提供的概述、快速入門和程式碼方法。

>[!IMPORTANT]
>
>從8.0版（2018年8月發行）開始，[!UICONTROL DIL]對[Adobe Experience Platform身分服務](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html)、3.3版或更新版本有嚴格的依賴。 它依賴[!DNL ID Service]來觸發ID同步和URL目標。 如果[!DNL ID Service]遺失、舊或未設定，則會發生錯誤。
>
>建議您使用[!DNL Adobe Experience Platform Launch]來實作和管理[!DNL DIL]和[!DNL Adobe Experience Platform Identity Service]程式庫。

不過，您也可以從我們的GitHub頁面下載最新的Experience Cloud和[!DNL DIL]版本。 請參閱以下的下載連結：

* 下載[Adobe Experience PlatformIdentity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下載[DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL目的{#purpose-dil}

[!UICONTROL DIL] 是API程式庫。您可將其視為[!DNL Adobe Audience Manager]的輔助程式碼。 您不需要使用[!DNL Audience Manager]，但[!UICONTROL DIL]的方法和函式表示您不需要開發自己的程式碼，就能將資料傳送至[!DNL Audience Manager]。 此外，[!UICONTROL DIL]與[Adobe Experience Platform身分服務](https://docs.adobe.com/content/help/en/id-service/using/home.html)所提供的API不同。 該服務旨在管理不同[!DNL Experience Cloud]解決方案的訪客身分。 相比之下，[!UICONTROL DIL]的設計目的是：

* 進行事件呼叫並將資料傳送至[資料收集伺服器](../reference/system-components/components-data-collection.md)。
* 傳送資料至[目標](../features/destinations/destinations.md)。

## 獲取和實施DIL代碼{#get-implement-dil-code}

[!UICONTROL DIL] 程式碼可從這裡 **[下載](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。請注意，從8.0版（2018年8月發行）開始，[!UICONTROL DIL]對[Adobe Experience Platform身分服務](https://docs.adobe.com/content/help/en/id-service/using/home.html)、3.3版或更新版本有嚴格的依存。 它依賴[!DNL ID Service]來觸發ID同步和[!DNL URL destinations]。 如果[!DNL ID Service]遺失、舊或未設定，則會發生錯誤。

我們建議您不要使用[!UICONTROL DIL]並手動設定[!DNL Audience Manager]，而應改用[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html)。 [!DNL Adobe Experience Platform Launch] 是建議的實作工具，因為它可簡化程式碼部署、位置和版本管理。閱讀有關[!DNL Adobe Experience Platform Launch]中[Audience Manager擴展](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html)的更多資訊。

## 範例呼叫{#sample-code}

[!UICONTROL DIL] 在事件呼 [!DNL Audience Manager] 叫中傳送資料。事件呼叫是來自您頁面的XML HTTP請求。 它使用`POST`方法傳送請求內文中的資料。

| 事件呼叫元素 | 說明 |
|--- |--- |
| URL | DIL事件呼叫使用以下語法：`https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 內文 | 如以下範例所示，DIL會將資料傳遞為索引鍵值對。 特殊前置詞字元將鍵值對標識為Audience Manager或夥伴變數。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

另請參閱：
* [關鍵變數的前置詞要求](../features/traits/trait-variable-prefixes.md)
* [DCS API 呼叫的支援屬性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)。

## 相關連結

* [DIL 使用案例和程式碼範例](/help/using/dil/dil-use-cases.md)
* [類別層級 DIL 方法](/help/using/dil/dil-class-overview/dil-start.md)
* [例項層級 DIL 方法](/help/using/dil/dil-instance-methods.md)
* [DIL 模組](/help/using/dil/dil-modules.md)
* [DIL 工具](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
