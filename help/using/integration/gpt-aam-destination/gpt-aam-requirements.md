---
description: 您可以透過用戶端或伺服器端整合，將合格區段傳送至DFP。以下列出兩種方法的需求和相關資訊。
seo-description: 您可以透過用戶端或伺服器端整合，將合格區段傳送至DFP。以下列出兩種方法的需求和相關資訊。
seo-title: 使用 Google 發佈商代碼 (GPT) 傳送區段至 DFP 的需求和方法
solution: Audience Manager
title: 使用 Google 發佈商代碼 (GPT) 傳送區段至 DFP 的需求和方法
uuid: 4b2ea81c-29bb-42d3-93d3-3d8e677790b6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 使用 Google 發佈商代碼 (GPT) 傳送區段至 DFP 的需求和方法{#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

You can send qualified segments to [!DNL DFP] either through a client-side or through a server-side integration. 以下列出兩種方法的需求和相關資訊。

## Client-Side Integration {#client-side-integration}

For a client-side integration, you need to set up a [!DNL GPT] destination in Audience Manager. Consider the following points when you want to set up [!DNL GPT] as an Audience Manager destination:

* **新增[!UICONTROL DIL]：** 在您要定位的所有頁面上部署 [!UICONTROL Data Integration Library (DIL)] 程式碼。[!UICONTROL DIL] 將Audience Manager區段資料和使用者ID寫入用於定位 [!DNL GPT] 的Cookie。

* **建立[!UICONTROL Cookie Destination]一個：**[!DNL GPT] 必須設為Audience Manager中的Cookie目的地。

* **實作Cookie檢查代碼：** 將 [!DNL GPT]`.setTargeting` API方法包裝在我們建議 [的Cookie檢查程式碼](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)中。This code helps prevent errors by looking for valid AAM cookies before the `.setTargeting` method gets invoked.

* **新增`AamGpt`函數：**`AamGpt` 程式碼會擷取Audience Manager Cookie中的資料並傳送至 [!DNL GPT]。Place the [Audience Manager Code for Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) at the top of the page or inside the `<head>` code block.

   >[!NOTE]
   >
   >The `AamGpt` function is not required if you use your own code to read Audience Manager cookie data.

* **傳送傳送記錄至Audience Manager：** 如果您想要區段傳送報表(選用)，請提供Audience Manager使用包含曝光層級傳送資料的每日記錄檔。The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### 只有合格區段才會傳送至GPT

The amount of data passed in to [!DNL GPT] depends on how many segments a particular user qualifies for. 例如，假設您設定了100個Audience Manager區段。If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL GPT] (not all 100).

>[!NOTE]
>
>There are no limits to the number of key-values you can send, but the [!DNL Google] request [!DNL URL] does have limits to the number of characters it can accept. See [Setting targeting and sizes with GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Server-Side Integration {#server-side-integration}

Talk to your Audience Manager consultant or Customer Care if you want to set up a server-side integration with [!DNL DFP], using [!DNL GPT]. You&#39;ll need to provide your [!DNL DFP] account Network ID and Audience Link ID.

>[!IMPORTANT]
>
>If your web pages are running the [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) library, you must use the server-side integration with Audience Manager. If you are on [!DNL AMP] and have a client-side integration with [!DNL AMP], you must migrate to the server-side integration. 請聯絡您的Audience Manager顧問或客戶服務，以討論移轉。

>[!MORE_贊_ this]
>
>* [GPT API參考指南](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

