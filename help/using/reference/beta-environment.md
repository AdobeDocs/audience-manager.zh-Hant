---
description: 測試版環境可用來測試您的Audience Manager實作。 在Beta版中進行的變更不會影響生產資料。 如果您有興趣使用測試版環境，請聯絡您的Audience Manager合作夥伴解決方案代表。
keywords: 沙箱
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: Beta環境
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
source-git-commit: fce39268f1c8c4dd1b7ff21b61a9830a20fa0b4e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# Beta環境 {#beta-environment}

測試版環境可用來測試您的Audience Manager實作。 在Beta版中進行的變更不會影響生產資料。 如果您有興趣使用測試版環境，請聯絡您的Audience Manager合作夥伴解決方案代表。

## 概述

bveta環境中的功能是生產環境的精確復本，沒有任何實驗性或未發行的功能。 您從生產環境取得的登入憑證在Beta版環境中有效。

**更新排程**

測試版環境會在每個月的月底非尖峰時段更新。

>[!IMPORTANT]
>
>請注意，您的客戶資料（[訊號、特徵和區段](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=en)）並未在生產環境和Beta版環境之間同步。

## 傳入流量

測試版環境僅針對檔案名稱和內容語法驗證目的支援傳入流量。 由於測試版環境中不會進行ID對應，因此客戶不會看到任何區段人口。

因此，在Beta版環境中擷取檔案時，[!UICONTROL Onboarding Status]頁面一律會報告[!UICONTROL No matching AAM ID]。

我們建議所有客戶在其生產環境中執行任何傳入測試。

## 傳出流量

測試版環境未啟用傳出流量。

## 端點

| 服務 | url/主機名稱 | 如何取得存取權 |
|--- |--- | --- |
| S3 | 請聯絡您的Audience Manager合作夥伴解決方案代表或客戶服務 | 請聯絡您的Audience Manager合作夥伴解決方案代表或客戶服務，為您的Beta版執行個體設定Amazon S3貯體。 閱讀使用Amazon S3[的](../reference/amazon-s3.md)優點。 |
| DCS | `https://dcs-beta.demdex.net/...` | 請參閱[在Beta環境中存取DCS](../reference/beta-environment.md#access-dcs-beta-environment)。 |
| UI | `https://bank-beta.demdex.com` | 您的生產環境憑證對測試版環境有效。 |
| API | `https://api-beta.demdex.com/...` | 您的生產環境憑證對測試版環境有效。 建議您建立一般API使用者，[檢視詳細資料](../api/rest-api-main/aam-api-getting-started.md#requirements)。 |

## 存取Beta環境中的DCS {#access-dcs-beta-environment}

1. 使用curl [命令](https://curl.haxx.se/docs/manpage.html)進行DCS呼叫。 Curl是一種工具，可使用多種支援的通訊協定之一，將資料從伺服器傳輸或傳輸到伺服器。

   例如：

   `curl -v https://dcs-beta.demdex.net/event`

1. 在DCS回應標頭中尋找「沙箱」，確認您的請求是由Beta版DCS提供。

   例如：

   ```
   curl -v http://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

<!--

1. Determine the load balancer's endpoint IP addresses.

   Run the `dig`  [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the [!DNL Audience Manager] [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

2. Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file.

   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts].

   For example:

   [!DNL 52.87.15.51 *`samplepartner`*.demdex.net]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

   [!DNL 52.87.15.51 dpm.demdex.net]. 

3. Make a DCS call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

   [!DNL https://<domain>/event?product=camera] 

4. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

   -->
