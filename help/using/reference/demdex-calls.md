---
description: Audience Manager和Adobe Experience Platform Identity服務會呼叫並從demdex.net網域接收資料。 這看起來像Adobe使用不尋常的協力廠商網域，但事實並非如此。 本節說明demdex.net呼叫中的元素。
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: 瞭解向Demdex網域進行的呼叫
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 4%

---

# 瞭解向[!DNL Demdex]網域進行的呼叫 {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager]和[!DNL Adobe Experience Platform Identity Service]會呼叫並接收來自`demdex.net`網域的資料。 這可能看起來像[!DNL Adobe]使用不尋常的協力廠商網域，但情況並非如此。 本節說明`demdex.net`呼叫中的專案。

| 呼叫元素 | 說明 |
|---|---|
| `demdex.net` | 這是由[!DNL Adobe]控制的舊網域。 它反映了[!DNL Audience Manager] ([!DNL Demdex])的原始贏取前名稱。 [!DNL Adobe] 於 2011 年收購 [!DNL Demdex]，並將該公司重新命名為 [!DNL Audience Manager]。變更此網域很困難，因為它與[!DNL Audience Manager]、[!DNL Adobe Experience Cloud ID Service]和我們的已安裝使用者群有很深的關聯。 您可能會看到附加至舊版`demdex.net`呼叫的其他首碼（例如`dcs.demdex.net`、`fast.demdex.net`等）。 無論首碼為何，對`something.demdex.net`的呼叫永遠是對[!DNL Adobe]的呼叫，而不是對未知或可疑的第三方網域的呼叫。 |
| `dpm` | [!DNL DPM]是[!DNL Data Provider Match]的縮寫。 它會告訴內部[!DNL Adobe]系統，來自[!DNL Audience Manager]或[!DNL Adobe Experience Cloud ID Service]的呼叫正傳入客戶資料以進行同步或請求ID。 這是您將會從`demdex.net`或[!DNL Audience Manager]看到的最常見的[!DNL Adobe Experience Cloud ID Service]呼叫。 <br><br>[!DNL DPM]呼叫基本資訊： <ul><li>[!DNL Audience Manager]：來自[!DNL DPM]的[!DNL Audience Manager]呼叫會將資料傳送至[!DNL Data Collection Servers]和[!DNL Profile Cache Servers]。 請參閱[資料收集元件](../reference/system-components/components-data-collection.md)。</li><li>[!DNL Adobe Experience Cloud ID Service]：來自[!DNL DPM]的[!DNL Adobe Experience Cloud ID Service]呼叫是訪客ID的要求。 請參閱[Cookie與Adobe Experience Platform Identity服務](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html)和[Adobe Experience Platform Identity服務如何要求與設定ID](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html)。</li></ul><br>注意： [!DNL Adobe Experience Cloud ID Service]客戶可以變更網域名稱中的[!DNL DPM]首碼。 請參閱[audienceManager伺服器和audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html)。 |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity服務](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Audience Manager Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)
