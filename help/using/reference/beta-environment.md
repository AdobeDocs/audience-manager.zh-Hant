---
description: 測試版環境是用來測試您的Audience Manager實作。在測試版中所做的變更不會影響生產資料。如果您對使用測試版環境感興趣，請與Audience Manager合作夥伴解決方案代表連絡。
keywords: 沙盒
seo-description: 測試版環境是用來測試您的Audience Manager實作。在測試版中所做的變更不會影響生產資料。如果您對使用測試版環境感興趣，請與Audience Manager合作夥伴解決方案代表連絡。
seo-title: 測試版環境
solution: Audience Manager
title: 測試版環境
uuid: de4a1a46-cfa4-4f64-8569-48a7650 fd8 cf
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# 測試版環境 {#beta-environment}

測試版環境是用來測試您的Audience Manager實作。在測試版中所做的變更不會影響生產資料。如果您對使用測試版環境感興趣，請與Audience Manager合作夥伴解決方案代表連絡。

## 概述

beta版環境是製作環境的精確復本，沒有任何實驗性或未釋放的功能。來自生產環境的登入憑證在測試環境中有效。

**更新排程**

測試版環境會在每月結束時每月結束。

**傳出流量**

測試版環境未啓用傳出流量。

<!-- 

Added re: AAM-30826.

 -->

## 端點



| 服務 | URL/主機名稱 | 如何取得存取權 |
|--- |--- | --- |
| S3 | 聯絡您的Audience Manager合作夥伴解決方案代表或客戶服務 | 請聯絡Audience Manager合作夥伴解決方案代表或客戶服務，為您的測試版執行個體設定Amazon S儲存貯體。Read about the [advantages of using Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | See [Accessing the DCS in the Beta Environment](../reference/beta-environment.md#access-dcs-beta-environment). |
| UI | `https://bank-beta.demdex.com` | 您的生產環境認證適用於測試版環境。 |
| API | `https://api-beta.demdex.com/...` | 您的生產環境認證適用於測試版環境。We recommend that you create a generic API user, [see details](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Accessing the DCS in the Beta Environment {#access-dcs-beta-environment}

1. Make a DCS call, using the curl [command](https://curl.haxx.se/docs/manpage.html). Curl是使用多種支援通訊協定，從伺服器傳輸資料的工具。

   例如:

   `curl -v https://dcs-beta.demdex.net/event`

1. 在DCS回應標題中尋找「沙盒」，確認您的要求是由測試版DCS提供。

   例如:

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