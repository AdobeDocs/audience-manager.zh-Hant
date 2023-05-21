---
description: DIL及其工作原理概述。
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil,dil
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

# 瞭解 [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

概述、入門和代碼方法 [!DNL Audience Manager DIL] 代碼庫。

>[!IMPORTANT]
>
>從8.0版開始（2018年8月發佈）, [!UICONTROL DIL] 很依賴 [Adobe Experience Platform身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html), 3.3版或更高版本。 它依賴於 [!DNL ID Service] 以激發ID同步和URL目標。 如果 [!DNL ID Service] 缺少、舊或未配置。
>
>我們建議您使用 [!DNL Adobe Experience Platform Tags] 實施和管理 [!DNL DIL] 和 [!DNL Adobe Experience Platform Identity Service] 庫。

但是，您也可以下載最新的Experience Cloud [!DNL DIL] 從GitHub頁面發佈。 請參閱以下下載連結：

* 下載 [Adobe Experience Platform身份服務](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 下載 [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL {#purpose-dil}

[!UICONTROL DIL] 是API庫。 你可以認為它是 [!DNL Adobe Audience Manager]。 不需要使用 [!DNL Audience Manager]但是方法和功能 [!UICONTROL DIL] 提供意味著您不必開發自己的代碼來將資料發送到 [!DNL Audience Manager]。 還有， [!UICONTROL DIL] 不同於 [Adobe Experience Platform身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)。 該服務旨在管理不同訪問者身份 [!DNL Experience Cloud] 解決方案。 相反， [!UICONTROL DIL] 設計為：

* 進行事件調用並將資料發送到 [資料收集伺服器](../reference/system-components/components-data-collection.md)。
* 將資料發送到 [目的地](../features/destinations/destinations.md)。

## 獲取和實施DIL代碼 {#get-implement-dil-code}

[!UICONTROL DIL] 可下載代碼 **[這裡](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。 請注意，從8.0版（2018年8月發佈）開始， [!UICONTROL DIL] 很依賴 [Adobe Experience Platform身份服務](https://experienceleague.adobe.com/docs/id-service/using/home.html), 3.3版或更高版本。 它依賴於 [!DNL ID Service] 觸發ID同步 [!DNL URL destinations]。 如果 [!DNL ID Service] 缺少、舊或未配置。

而不是 [!UICONTROL DIL] 設定 [!DNL Audience Manager] 手動，建議您使用 [Adobe Experience Platform標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) 的雙曲餘切值。 [!DNL Adobe Experience Platform Tags] 是推薦的實施工具，因為它簡化了代碼部署、放置和版本管理。 閱讀有關 [Audience Manager擴展](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) 在 [!DNL Adobe Experience Platform Tags]。

## 示例調用 {#sample-code}

[!UICONTROL DIL] 發送資料 [!DNL Audience Manager] 在事件呼叫中。 事件調用是來自您頁面的XML HTTP請求。 它使用 `POST` 在請求正文中發送資料的方法。

| 事件調用元素 | 說明 |
|--- |--- |
| URL | DIL事件調用使用以下語法： `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 內文 | 如下面的示例所示，DIL將資料作為鍵值對傳遞。 特殊前置詞字元將鍵值對標識為Audience Manager或夥伴變數。<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
