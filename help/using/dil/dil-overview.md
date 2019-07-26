---
description: 概述DIL及其運作方式。
seo-description: 概述DIL及其運作方式。
seo-title: 瞭解資料整合庫(DIL)
solution: Audience Manager
title: 瞭解資料整合庫(DIL)
uuid: 77b12f35-81e4-4639-ada6-bc982 f27 b36 e
translation-type: tm+mt
source-git-commit: 8f2cbf8a31335762f03cad278114d9ab7c520763

---


# Understanding the Data Integration Library (DIL){#understanding-the-data-integration-library-dil}

Audience Manager DIL程式碼庫中可用的概述、快速入門和程式碼方法。

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. 它依賴ID服務觸發ID同步和URL目的地。如果ID服務遺失、舊或未設定，就會發生錯誤。
>
>建議您使用Adobe Launch實施及管理您的DIL和Experience Cloud ID服務程式庫。

不過，您也可以從我們的GitHub頁面下載最新的Experience Cloud和DIL版本。請參閱下列下載連結：

* Download the [Experience Cloud ID Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Download [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Purpose of DIL {#purpose-dil}

[!UICONTROL DIL] 是API庫。You can think it as a body of helper code for [!DNL Adobe Audience Manager]. It is not required to use [!DNL Audience Manager], but the methods and functions [!UICONTROL DIL] provides means you don't have to develop your own code to send data to [!DNL Audience Manager]. Also, [!UICONTROL DIL] is different than the API provided by the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/). That service is designed to manage visitor identity across different [!DNL Experience Cloud] solutions. By contrast, [!UICONTROL DIL] is designed to:

* Make event calls and send data to the [Data Collection Server](../reference/system-components/components-data-collection.md).
* Send data to [destinations](../features/destinations/destinations.md).

## Getting and Implementing DIL Code {#get-implement-dil-code}

[!UICONTROL DIL] 程式碼可供下載 **[](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. 它依賴ID服務觸發ID同步和URL目的地。如果ID服務遺失、舊或未設定，就會發生錯誤。

Rather than work with [!UICONTROL DIL] and set up [!DNL Audience Manager] manually, we recommend that you use [Adobe Launch](https://docs.adobelaunch.com/) instead. [!DNL Adobe Launch] 是建議的實施工具，因為它簡化了程式碼部署、位置和版本管理。Read more about the [Audience Manager extension](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in Adobe Launch.

Adobe Launch is the successor to [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Sample Call {#sample-code}

[!UICONTROL DIL] 傳送資料至 [!DNL Audience Manager] 事件呼叫中。事件呼叫是來自您頁面的XML HTTP請求。It uses a `POST` method to send data in the body of the request.

| 事件呼叫元素 | 說明 |
|--- |--- |
| URL | DIL event calls use the following syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 內文 | 如下方範例所示，DIL會將資料傳遞為索引鍵值配對。Special prefix characters identify the key-value pairs as Audience Manager or partner variables.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

另請參閱:
* [關鍵變數的首碼需求](../features/traits/trait-variable-prefixes.md)
* [DCS API呼叫的支援屬性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 相關連結

* [DIL使用案例和程式碼範例](/help/using/dil/dil-use-cases.md)
* [類別層級DIL方法](/help/using/dil/dil-class-overview/dil-start.md)
* [例項層級DIL方法](/help/using/dil/dil-instance-methods.md)
* [DIL模組](/help/using/dil/dil-modules.md)
* [DIL工具](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)