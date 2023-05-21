---
description: Audience Manager和Adobe Experience Platform身份服務向demdex.net域進行呼叫並從其接收資料。 這看起來似乎Adobe在與一個不尋常的第三方領域合作，但事實並非如此。 本節介紹demdex.net調用中的元素。
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: 瞭解向 Demdex 網域進行的呼叫
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 8%

---

# 瞭解呼叫 [!DNL Demdex] 域 {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] 和 [!DNL Adobe Experience Platform Identity Service] 呼叫並接收資料 `demdex.net` 。 這看起來好像 [!DNL Adobe] 與一個不同尋常的第三方領域合作，但情況並非如此。 本節介紹 `demdex.net` 呼叫。

| 調用元素 | 說明 |
|---|---|
| `demdex.net` | 這是由 [!DNL Adobe]。 它反映的是 [!DNL Audience Manager] ([!DNL Demdex])。 [!DNL Adobe] 於 2011 年收購 [!DNL Demdex]，並將該公司重新命名為 [!DNL Audience Manager]。很難改變這個領域，因為它與 [!DNL Audience Manager]，也請參見Wiki頁。 [!DNL Adobe Experience Cloud ID Service]，以及已安裝的用戶群。 您可能會看到附加到舊版前置詞的其他前置詞 `demdex.net` 呼叫(例如， `dcs.demdex.net`。 `fast.demdex.net`等)。 無論前置詞是什麼， `something.demdex.net` 總是要打電話 [!DNL Adobe] 而不是某個未知或可疑的第三方域。 |
| `dpm` | [!DNL DPM] 是 [!DNL Data Provider Match]。 它告訴內部， [!DNL Adobe] 來自 [!DNL Audience Manager] 或 [!DNL Adobe Experience Cloud ID Service] 正在傳遞客戶資料以進行同步或請求ID。 這是最常見的 `demdex.net` 打給你以後 [!DNL Audience Manager] 或 [!DNL Adobe Experience Cloud ID Service]。 <br><br>[!DNL DPM] 呼叫基礎： <ul><li>[!DNL Audience Manager]:A [!DNL DPM] 呼叫 [!DNL Audience Manager] 向 [!DNL Data Collection Servers] 和 [!DNL Profile Cache Servers]。 請參閱[資料收集元件](../reference/system-components/components-data-collection.md)。</li><li>[!DNL Adobe Experience Cloud ID Service]:A [!DNL DPM] 呼叫 [!DNL Adobe Experience Cloud ID Service] 請求訪問者ID。 請參閱 [Cookie和Adobe Experience Platform身份服務](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) 和 [Adobe Experience Platform身份服務請求和設定ID的方式](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html)。</li></ul><br>注： [!DNL Adobe Experience Cloud ID Service] 客戶可以更改 [!DNL DPM] 域名中的前置詞。 請參閱 [audienceManager伺服器和audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html)。 |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Audience Manager Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)

