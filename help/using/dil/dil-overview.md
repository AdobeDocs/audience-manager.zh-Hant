---
description: DIL的概觀及其運作方式。
seo-description: DIL的概觀及其運作方式。
seo-title: 瞭解資料整合庫(DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: 瞭解資料整合庫(DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# 瞭解資料整合庫(DIL){#understanding-the-data-integration-library-dil}

Audience Manager DIL程式碼庫中提供的概觀、快速入門和程式碼方法。

>[!IMPORTANT]
>
>從8.0版（2018年8月發行）起， [!UICONTROL DIL] 您對 [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)3.3版或更新版本的依賴十分嚴重。 它依賴ID服務來觸發ID同步和URL目標。 如果ID服務遺失、舊或未設定，就會發生錯誤。
>
>我們建議您使用Adobe Experience Platform Launch來實作和管理DIL和Adobe Experience Platform Identity Service程式庫。

不過，您也可以從我們的GitHub頁面下載最新的Experience Cloud和DIL版本。 請參閱以下的下載連結：

* 下載 [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下載 [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL的用途 {#purpose-dil}

[!UICONTROL DIL] 是API程式庫。 你可以把它當成一套輔助代碼 [!DNL Adobe Audience Manager]。 您不需要使用它 [!DNL Audience Manager]，但提供的方 [!UICONTROL DIL] 法和功能表示您不需要開發自己的程式碼即可傳送資料 [!DNL Audience Manager]。 此外， [!UICONTROL DIL] 它與 [Adobe Experience Platform Identity Service提供的API不同](https://docs.adobe.com/content/help/en/id-service/using/home.html)。 該服務旨在管理不同解決方案的訪客 [!DNL Experience Cloud] 身分。 相比之下， [!UICONTROL DIL] 其設計目的是：

* 進行事件呼叫並傳送資料至資 [料收集伺服器](../reference/system-components/components-data-collection.md)。
* 傳送資料至 [目的地](../features/destinations/destinations.md)。

## 取得及實作DIL程式碼 {#get-implement-dil-code}

[!UICONTROL DIL] 程式碼可從這裡 **[下載](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。 請注意，從8.0版（2018年8月發行）開始，[!UICONTROL DIL]Adobe Experience Platform Identity Service[](https://docs.adobe.com/content/help/en/id-service/using/home.html)（3.3版或更新版本）的需求十分龐大。 它依賴ID服務來觸發ID同步和URL目標。 如果ID服務遺失、舊或未設定，就會發生錯誤。

我們建議您改用 [!UICONTROL DIL] Adobe Experience Platform Launch [!DNL Audience Manager][](https://docs.adobelaunch.com/) ，而不是手動使用和設定。 [!DNL Adobe Experience Platform Launch] 是建議的實作工具，因為它可簡化程式碼部署、位置和版本管理。 閱讀Adobe Experience Platform Launch中 [的Audience Manager擴充功能](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) ，以進一步瞭解。

Adobe Experience Platform Launch是 [Adobe Dynamic Tag Manager](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) ([!DNL DTM])的後繼者。

## 範例呼叫 {#sample-code}

[!UICONTROL DIL] 在事件呼叫 [!DNL Audience Manager] 中傳送資料。 事件呼叫是來自您頁面的XML HTTP請求。 它使用一 `POST` 種方法，在請求的正文中傳送資料。

| 事件呼叫元素 | 說明 |
|--- |--- |
| URL | DIL事件呼叫使用下列語法： `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 內文 | 如以下範例所示，DIL會將資料傳遞為索引鍵值配對。 特殊首碼字元會將金鑰值配對識別為Audience Manager或合作夥伴變數。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

另請參閱:
* [關鍵變數的前置詞要求](../features/traits/trait-variable-prefixes.md)
* [DCS API呼叫的支援屬性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 相關連結

* [DIL使用案例和程式碼範例](/help/using/dil/dil-use-cases.md)
* [類別層級DIL方法](/help/using/dil/dil-class-overview/dil-start.md)
* [例項層級DIL方法](/help/using/dil/dil-instance-methods.md)
* [DIL模組](/help/using/dil/dil-modules.md)
* [DIL工具](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)