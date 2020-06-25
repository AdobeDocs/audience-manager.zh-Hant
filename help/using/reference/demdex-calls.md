---
description: Audience Manager和Adobe Experience Platform Identity Service會呼叫demdex.net網域並從中接收資料。 Adobe似乎正在與不同尋常的第三方網域合作，但事實並非如此。 本節說明demdex.net呼叫中的元素。
seo-description: Audience Manager和Adobe Experience Platform Identity Service會呼叫demdex.net網域並從中接收資料。 Adobe似乎正在與不同尋常的第三方網域合作，但事實並非如此。 本節說明demdex.net呼叫中的元素。
seo-title: 瞭解向 Demdex 網域進行的呼叫
solution: Audience Manager
title: 瞭解向 Demdex 網域進行的呼叫
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 14%

---


# Understanding Calls to the [!DNL Demdex] Domain {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] 以及 [!DNL Adobe Experience Platform Identity Service] 對網域進行呼叫和接收數 `demdex.net` 據。 這似乎與一 [!DNL Adobe] 個不同尋常的第三方領域有關，但情況並非如此。 本節說明呼叫中的 `demdex.net` 元素。

| 呼叫元素 | 說明 |
|---|---|
| `demdex.net` | This is a legacy domain controlled by [!DNL Adobe]. 它反映( [!DNL Audience Manager][!DNL Demdex])的原始收購前名稱。 [!DNL Adobe] 於 2011 年收購 [!DNL Demdex]，並將該公司重新命名為 [!DNL Audience Manager]。很難更改此域，因為它與已安裝的用戶群 [!DNL Audience Manager]、用戶 [!DNL Adobe Experience Cloud ID Service]群以及用戶群密切相連。 您可能會看到附加在舊 `demdex.net` 呼叫的其他字首( `dcs.demdex.net`如 `fast.demdex.net`，等等)。 不論首碼為何，呼叫一律 `something.demdex.net` 是對某個未知或可疑 [!DNL Adobe] 第三方網域的呼叫，而非呼叫。 |
| `dpm` | [!DNL DPM] 是的縮寫 [!DNL Data Provider Match]。 It tells internal, [!DNL Adobe] systems that a call from [!DNL Audience Manager] or the [!DNL Adobe Experience Cloud ID Service] is passing in customer data for synchronization or requesting an ID. 這是您從或 `demdex.net` 中看到的最常見 [!DNL Audience Manager] 的呼叫 [!DNL Adobe Experience Cloud ID Service]。 <br><br>[!DNL DPM] 呼叫基礎： <ul><li>[!DNL Audience Manager]: 來 [!DNL DPM] 自的呼 [!DNL Audience Manager] 叫會將資料傳送至 [!DNL Data Collection Servers] 和 [!DNL Profile Cache Servers]。 請參閱[資料收集元件](../reference/system-components/components-data-collection.md)。</li><li>[!DNL Adobe Experience Cloud ID Service]: 來自 [!DNL DPM] 的呼叫 [!DNL Adobe Experience Cloud ID Service] 是訪客ID的請求。 請參 [閱Cookie和Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/intro/cookies.html)[，以及Adobe Experience Platform Identity Service如何要求和設定ID](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html)。</li></ul><br>注意： [!DNL Adobe Experience Cloud ID Service] 客戶可以變更 [!DNL DPM] 網域名稱中的首碼。 請參 [閱audienceManager Server和audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html)。 |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.translate.html)
>* [Audience Manager Cookie](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-am.translate.html)

