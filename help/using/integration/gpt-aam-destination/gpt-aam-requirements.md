---
description: 您可以透過用戶端或伺服器端整合，將合格的區段傳送至DFP。 以下列出兩種方法的需求和相關資訊。
seo-description: 您可以透過用戶端或伺服器端整合，將合格的區段傳送至DFP。 以下列出兩種方法的需求和相關資訊。
seo-title: 使用 Google 發佈商代碼 (GPT) 傳送區段至 DFP 的需求和方法
solution: Audience Manager
title: 使用 Google 發佈商代碼 (GPT) 傳送區段至 DFP 的需求和方法
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e67790b6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 使用 Google 發佈商代碼 (GPT) 傳送區段至 DFP 的需求和方法{#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

您可以透過用戶端或 [!DNL DFP] 伺服器端整合，將符合資格的區段傳送至。 以下列出兩種方法的需求和相關資訊。

## 用戶端整合 {#client-side-integration}

若要進行用戶端整合，您必須在Audience manager中設 [!DNL GPT] 定目標。 當您想要設定為Audience manager目標時，請考 [!DNL GPT] 慮以下幾點：

* **[!UICONTROL DIL]新增**:將程 [!UICONTROL Data Integration Library (DIL)] 式碼部署在您要定位的所有頁面上。 [!UICONTROL DIL] 將Audience manager區段資料和使用者ID寫入Cookie，以供定 [!DNL GPT] 位使用。

* **[!UICONTROL Cookie Destination]建立**:必 [!DNL GPT] 須在Audience manager中設定為Cookie型目標。

* **** 實作Cookie檢查代碼：將 [!DNL GPT] API方 `.setTargeting` 法包裝在我們建議的 [Cookie檢查程式碼中](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)。 此程式碼可在呼叫方法之前先尋找有效的AAM Cookie，以 `.setTargeting` 協助防止錯誤。

* **`AamGpt`添加函** 數：程式 `AamGpt` 碼會從Audience Manager cookie擷取資料並傳送至 [!DNL GPT]。 將Google Publisher標 [簽的Audience Manager代碼](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`)置於頁面頂端或代碼區塊 `<head>` 內。

   >[!NOTE]
   >
   >如果您 `AamGpt` 使用自己的程式碼來讀取Audience Manager cookie資料，則不需要此函式。

* **** 傳送傳送記錄至Audience Manager:如果您想要區段傳送報表（可選），請為Audience manager提供包含曝光層級傳送資料的每日記錄。 資料可以是原始格式，但每個記錄都必須包含Audience Manager `UUID`。 Audience manager可以透過取得或接收這些 [!DNL FTP]。

### 僅將合格區段傳送至GPT

傳入的資料量取決於 [!DNL GPT] 特定使用者符合的區段數。 例如，假設您設定了100個Audience manager區段。 如果某位網站訪客符合其中5個的資格，則只有這5個區段會被傳送 [!DNL GPT] 至（並非全部100個）。

>[!NOTE]
>
>您可以傳送的索引鍵值數目沒有限制，但 [!DNL Google] 請 [!DNL URL] 求可接受的字元數目有限制。 請參 [閱使用GPT設定目標和大小](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712)。

## 伺服器端整合 {#server-side-integration}

如果您想要使用設定伺服器端整合，請洽詢您的Audience manager顧問或客戶服務 [!DNL DFP]人員 [!DNL GPT]。 您必須提供您的帳 [!DNL DFP] 戶網路ID和觀眾連結ID。

>[!IMPORTANT]
>
>如果您的網頁正在執行 [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP])程式庫，您必須使用與Audience manager的伺服器端整合。 如果您位於 [!DNL AMP] 且與用戶端整合， [!DNL AMP]則必須移轉至伺服器端整合。 請連絡您的Audience manager顧問或客戶服務以討論移轉問題。

>[!MORE_LIKE_THIS]
>
>* [GPT API參考指南](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

