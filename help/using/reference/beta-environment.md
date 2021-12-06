---
description: 測試版環境用於測試您的Audience Manager實作。 在測試版中進行的變更不會影響生產資料。 如果您有興趣使用測試版環境，請連絡您的Audience Manager合作夥伴解決方案代表。
keywords: 沙箱
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

測試版環境用於測試您的Audience Manager實作。 在測試版中進行的變更不會影響生產資料。 Contact your Audience Manager Partner Solutions representative if you&#39;re interested in using the beta environment.

## 概述

The functionality in the bveta environment is an exact replica of the production environment, without any experimental or unreleased features. 您來自生產環境的登入認證在測試版環境中有效。

**更新計畫**

The beta environment is updated at the end of each month during off-peak hours.

>[!IMPORTANT]
>
>Note that your customer data ([signals, traits, and segments](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=en)) is not synced between the production and beta environments.

## Inbound Traffic

測試版環境僅支援用於檔案名稱和內容語法驗證目的的傳入流量。 由於測試版環境中沒有進行ID對應，因此客戶將看不到任何區段母體。

因此， [!UICONTROL Onboarding Status] 頁面將一律報告 [!UICONTROL No matching AAM ID] 在測試版環境中擷取檔案時。

We advise all customers to perform any inbound testing on their production environment.

## 傳出流量

測試版環境未啟用傳出流量。

## 端點

| 服務 | URL/Hostname | 如何取得存取權 |
|--- |--- | --- |
| S3 | 請聯絡您的Audience Manager合作夥伴解決方案代表或客戶服務 | Contact your Audience Manager Partner Solutions representative or Customer Care to set up an Amazon S3 bucket for your beta instance. 閱讀 [使用Amazon S3的優點](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | 請參閱 [存取測試版環境中的DCS](../reference/beta-environment.md#access-dcs-beta-environment). |
| UI | `https://bank-beta.demdex.com` | Your production environment credentials are valid for the beta environment. |
| API | `https://api-beta.demdex.com/...` | Your production environment credentials are valid for the beta environment. 建議您建立一般API使用者， [查看詳細資訊](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## 存取測試版環境中的DCS {#access-dcs-beta-environment}

1. 使用curl進行DCS呼叫 [命令](https://curl.haxx.se/docs/manpage.html). curl是使用許多支援通訊協定之一，從伺服器傳輸資料或傳送至伺服器的工具。

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
