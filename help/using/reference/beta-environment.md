---
description: 測試版環境用於測試您的Audience Manager實施。 在測試版中所做的更改不會影響生產資料。 如果您對使用測試版環境感興趣，請與Audience Manager合作夥伴解決方案代表聯繫。
keywords: 沙坑
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: 測試版環境
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
source-git-commit: fce39268f1c8c4dd1b7ff21b61a9830a20fa0b4e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 3%

---

# 測試版環境 {#beta-environment}

測試版環境用於測試您的Audience Manager實施。 在測試版中所做的更改不會影響生產資料。 如果您對使用測試版環境感興趣，請與Audience Manager合作夥伴解決方案代表聯繫。

## 概述

bveta環境中的功能是生產環境的精確副本，沒有任何實驗性或未發佈的功能。 您來自生產環境的登錄憑據在測試環境中有效。

**更新計畫**

測試版環境在非高峰時段於每月底更新。

>[!IMPORTANT]
>
>請注意，您的客戶資料([信號、特徵和片段](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=en))未在生產環境和測試環境之間同步。

## 入站流量

測試版環境僅支援用於檔案名和內容語法驗證目的的入站流量。 由於測試環境上沒有ID映射，因此客戶將看不到任何段總體。

因此， [!UICONTROL Onboarding Status] 頁面將始終報告 [!UICONTROL No matching AAM ID] 在beta環境上進行檔案攝取。

我們建議所有客戶對其生產環境執行任何入站測試。

## 出站通信

未為測試環境啟用出站通信。

## 端點

| 服務 | URL/主機名 | 如何獲取訪問 |
|--- |--- | --- |
| S3 | 聯繫您的Audience Manager合作夥伴解決方案代表或客戶服務 | 聯繫您的Audience Manager合作夥伴解決方案代表或客戶服務人員，為您的試用版實例設定一個AmazonS3儲存桶。 閱讀 [使用AmazonS3的優勢](../reference/amazon-s3.md)。 |
| DCS | `https://dcs-beta.demdex.net/...` | 請參閱 [在Beta環境中訪問DCS](../reference/beta-environment.md#access-dcs-beta-environment)。 |
| UI | `https://bank-beta.demdex.com` | 您的生產環境憑據對測試環境有效。 |
| API | `https://api-beta.demdex.com/...` | 您的生產環境憑據對測試環境有效。 我們建議您建立通用API用戶， [查看詳細資訊](../api/rest-api-main/aam-api-getting-started.md#requirements)。 |

## 在Beta環境中訪問DCS {#access-dcs-beta-environment}

1. 使用捲曲進行DCS調用 [命令](https://curl.haxx.se/docs/manpage.html)。 Curl是使用許多受支援的協定之一將資料從伺服器傳輸或傳輸到伺服器的工具。

   例如：

   `curl -v https://dcs-beta.demdex.net/event`

1. 通過在DCS響應標頭中查找「沙箱」，驗證測試版DCS是否為您的請求提供了服務。

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
