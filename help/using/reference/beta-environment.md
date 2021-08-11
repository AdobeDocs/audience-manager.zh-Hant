---
description: 測試版環境用於測試您的Audience Manager實作。 在測試版中進行的變更不會影響生產資料。 如果您有興趣使用測試版環境，請連絡您的Audience Manager合作夥伴解決方案代表。
keywords: 沙箱
seo-description: 測試版環境用於測試您的Audience Manager實作。 在測試版中進行的變更不會影響生產資料。 如果您有興趣使用測試版環境，請連絡您的Audience Manager合作夥伴解決方案代表。
seo-title: 測試版環境
solution: Audience Manager
title: 測試版環境
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: 參考
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
source-git-commit: 6eefe6ac6db011e99a02cfc38abfe773a8f62e0d
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 4%

---

# 測試版環境 {#beta-environment}

測試版環境用於測試您的Audience Manager實作。 在測試版中進行的變更不會影響生產資料。 如果您有興趣使用測試版環境，請連絡您的Audience Manager合作夥伴解決方案代表。

## 概述

測試版環境中的功能是生產環境的精確副本，沒有任何實驗性或未發行的功能。 您來自生產環境的登入認證在測試版環境中有效。

**更新計畫**

測試版環境會在每月底的非尖峰時段更新。

>[!IMPORTANT]
>
>請注意，您的客戶資料（[訊號、特徵和區段](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=en)）沒有在生產環境和測試環境之間同步。

**傳出流量**

測試版環境未啟用傳出流量。

## 端點

| 服務 | URL/主機名稱 | 如何取得存取權 |
|--- |--- | --- |
| S3 | 請聯絡您的Audience Manager合作夥伴解決方案代表或客戶服務 | 請連絡您的Audience Manager合作夥伴解決方案代表或客戶服務，為您的測試版執行個體設定Amazon S3貯體。 閱讀有關使用Amazon S3](../reference/amazon-s3.md)的優點。[ |
| DCS | `https://dcs-beta.demdex.net/...` | 請參閱[存取測試版環境中的DCS](../reference/beta-environment.md#access-dcs-beta-environment)。 |
| UI | `https://bank-beta.demdex.com` | 您的生產環境認證對測試版環境有效。 |
| API | `https://api-beta.demdex.com/...` | 您的生產環境認證對測試版環境有效。 建議您建立一般API使用者[，請參閱詳細資料](../api/rest-api-main/aam-api-getting-started.md#requirements)。 |

## 存取測試版環境中的DCS {#access-dcs-beta-environment}

1. 使用curl [command](https://curl.haxx.se/docs/manpage.html)進行DCS呼叫。 curl是使用許多支援通訊協定之一，從伺服器傳輸資料或傳送至伺服器的工具。

   例如：

   `curl -v https://dcs-beta.demdex.net/event`

1. 尋找DCS回應標題中的「沙箱」，確認測試版DCS已提供您的請求。

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
