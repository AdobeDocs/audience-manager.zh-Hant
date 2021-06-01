---
description: Audience Manager和Adobe Experience Platform Identity Service會呼叫demdex.net網域，並從其接收資料。 這看起來似乎是Adobe在與一個不尋常的第三方領域合作，但情況並非如此。 本節說明demdex.net呼叫中的元素。
seo-description: Audience Manager和Adobe Experience Platform Identity Service會呼叫demdex.net網域，並從其接收資料。 這看起來似乎是Adobe在與一個不尋常的第三方領域合作，但情況並非如此。 本節說明demdex.net呼叫中的元素。
seo-title: 瞭解向 Demdex 網域進行的呼叫
solution: Audience Manager
title: 瞭解向 Demdex 網域進行的呼叫
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: 參考
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 15%

---

# 了解對[!DNL Demdex]網域{#understanding-calls-to-the-demdex-domain}的呼叫

[!DNL Audience Manager] 和對 [!DNL Adobe Experience Platform Identity Service] 網域進行呼叫和接收資 `demdex.net` 料。這看起來可能像是[!DNL Adobe]在使用異常的第三方網域，但情況並非如此。 本節介紹`demdex.net`呼叫中的元素。

| 呼叫元素 | 說明 |
|---|---|
| `demdex.net` | 這是由[!DNL Adobe]控制的舊域。 它反映收購前的[!DNL Audience Manager]([!DNL Demdex])原始名稱。 [!DNL Adobe] 於 2011 年收購 [!DNL Demdex]，並將該公司重新命名為 [!DNL Audience Manager]。很難更改此域，因為它與[!DNL Audience Manager]、[!DNL Adobe Experience Cloud ID Service]和我們安裝的用戶群緊密交織。 您可能會看到附加至舊版`demdex.net`呼叫的其他前置詞（例如`dcs.demdex.net`、`fast.demdex.net`等）。 無論首碼為何，對`something.demdex.net`的呼叫一律為對[!DNL Adobe]的呼叫，而非對某些未知或可疑的第三方網域的呼叫。 |
| `dpm` | [!DNL DPM] 是的縮 [!DNL Data Provider Match]寫。它會告訴內部[!DNL Adobe]系統，來自[!DNL Audience Manager]或[!DNL Adobe Experience Cloud ID Service]的呼叫正傳入客戶資料以進行同步或請求ID。 這是您最常從[!DNL Audience Manager]或[!DNL Adobe Experience Cloud ID Service]看到的`demdex.net`呼叫。 <br><br>[!DNL DPM] 呼叫基本須知： <ul><li>[!DNL Audience Manager]:來自 [!DNL DPM] 的呼叫 [!DNL Audience Manager] 會將資料傳送至 [!DNL Data Collection Servers] 和 [!DNL Profile Cache Servers]。請參閱[資料收集元件](../reference/system-components/components-data-collection.md)。</li><li>[!DNL Adobe Experience Cloud ID Service]:來 [!DNL DPM] 自的呼 [!DNL Adobe Experience Cloud ID Service] 叫是訪客ID的要求。請參閱[Cookie與Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hant/id-service/using/intro/cookies.html)及[Adobe Experience Platform Identity Service如何要求與設定ID](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html)。</li></ul><br>注意： [!DNL Adobe Experience Cloud ID Service] 客戶可以變 [!DNL DPM] 更網域名稱中的首碼。請參閱[audienceManager伺服器及audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html)。 |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform 身分服務](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Audience Manager Cookie](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-am.translate.html)

