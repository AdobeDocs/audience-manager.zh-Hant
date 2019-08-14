---
description: 概述DIL及其運作方式。
seo-description: 概述DIL及其運作方式。
seo-title: 瞭解資料整合庫(DIL)
keywords: 'dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil，dil l， '
solution: Audience Manager
title: 瞭解資料整合庫(DIL)
uuid: 77b12f35-81e4-4639-ada6-bc982 f27 b36 e
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# 瞭解資料整合庫(DIL){#understanding-the-data-integration-library-dil}

Audience Manager DIL程式碼庫中可用的概述、快速入門和程式碼方法。

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. 它依賴ID服務觸發ID同步和URL目的地。如果ID服務遺失、舊或未設定，就會發生錯誤。
>
>建議您使用Adobe Launch實施及管理您的DIL和Experience Cloud ID服務程式庫。

不過，您也可以從我們的GitHub頁面下載最新的Experience Cloud和DIL版本。請參閱下列下載連結：

* 下載 [Experience Cloud ID服務](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下載 [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL的用途 {#purpose-dil}

[!UICONTROL DIL] 是API庫。您可以將它視為程式碼的一部分 [!DNL Adobe Audience Manager]。它不需要使用 [!DNL Audience Manager]，但提供的方法和函數 [!UICONTROL DIL] 可讓您開發自己的程式碼，以傳送資料 [!DNL Audience Manager]。此外， [!UICONTROL DIL] 也與 [Experience Cloud ID服務所提供的API不同](https://marketing.adobe.com/resources/help/en_US/mcvid/)。該服務旨在管理 [!DNL Experience Cloud] 跨不同解決方案的訪客身分。相反地， [!UICONTROL DIL] 您可以：

* 進行事件呼叫並傳送資料至 [資料收集伺服器](../reference/system-components/components-data-collection.md)。
* 將資料傳送至 [目的地](../features/destinations/destinations.md)。

## 取得並實施DIL程式碼 {#get-implement-dil-code}

[!UICONTROL DIL] 程式碼可供下載 **[](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. 它依賴ID服務觸發ID同步和URL目的地。如果ID服務遺失、舊或未設定，就會發生錯誤。

我們建議您改用Adobe [!UICONTROL DIL][!DNL Audience Manager][Launch](https://docs.adobelaunch.com/) ，而非手動使用和設定。[!DNL Adobe Launch] 是建議的實施工具，因為它簡化了程式碼部署、位置和版本管理。進一步瞭解Adobe Launch中 [的Audience Manager擴充功能](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) 。

Adobe Launch是 [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM])的後繼。

## 範例呼叫 {#sample-code}

[!UICONTROL DIL] 傳送資料至 [!DNL Audience Manager] 事件呼叫中。事件呼叫是來自您頁面的XML HTTP請求。它會使用 `POST` 方法來傳送請求內文中的資料。

| 事件呼叫元素 | 說明 |
|--- |--- |
| URL | DIL事件呼叫使用下列語法： `https://adobe.demdex.net/event?_ts =`*`UNIX UTC timestamp`* |
| 內文 | 如下方範例所示，DIL會將資料傳遞為索引鍵值配對。特殊首碼字元會將索引鍵值配對識別為Audience Manager或合作夥伴變數。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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