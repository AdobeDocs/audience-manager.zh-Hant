---
description: 測試版環境是用於測試您的Audience Manager實作。 在測試中所做的變更不會影響生產資料。 如果您有興趣使用測試版環境，請連絡您的Audience Manager合作夥伴解決方案代表。
keywords: sandbox
seo-description: 測試版環境是用於測試您的Audience Manager實作。 在測試中所做的變更不會影響生產資料。 如果您有興趣使用測試版環境，請連絡您的Audience Manager合作夥伴解決方案代表。
seo-title: 測試版環境
solution: Audience Manager
title: 測試版環境
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 4%

---


# 測試版環境 {#beta-environment}

測試版環境是用於測試您的Audience Manager實作。 在測試中所做的變更不會影響生產資料。 如果您有興趣使用測試版環境，請連絡您的Audience Manager合作夥伴解決方案代表。

## 概述

測試環境是生產環境的精確副本，沒有任何實驗性或未發佈的功能。 您來自生產環境的登入認證在測試環境中有效。

**更新計畫**

測試版環境會在每月月底的非尖峰時段更新。

**出站流量**

測試環境未啟用出站流量。

<!-- 

Added re: AAM-30826.

 -->

## 端點



| 服務 | URL/主機名稱 | 如何取得存取權 |
|--- |--- | --- |
| S3 | 聯絡您的Audience Manager合作夥伴解決方案代表或客戶服務 | 請連絡您的Audience Manager合作夥伴解決方案代表或客戶服務，為您的測試版實例設定Amazon S3儲存貯體。 閱讀有關 [使用Amazon S3的優點](../reference/amazon-s3.md)。 |
| DCS | `https://dcs-beta.demdex.net/...` | 請參 [閱在測試環境中訪問DCS](../reference/beta-environment.md#access-dcs-beta-environment)。 |
| UI | `https://bank-beta.demdex.com` | 您的生產環境認證對測試環境有效。 |
| API | `https://api-beta.demdex.com/...` | 您的生產環境認證對測試環境有效。 我們建議您建立一般API使用者，請參 [閱詳細資訊](../api/rest-api-main/aam-api-getting-started.md#requirements)。 |

## 在測試環境中訪問DCS {#access-dcs-beta-environment}

1. 使用curl命令進行DCS [呼叫](https://curl.haxx.se/docs/manpage.html)。 Curl是使用許多支援的通訊協定之一，將資料從伺服器傳輸或傳輸至伺服器的工具。

   例如：

   `curl -v https://dcs-beta.demdex.net/event`

1. 在DCS回應標題中尋找「沙盒」，確認測試版DCS已支援您的要求。

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