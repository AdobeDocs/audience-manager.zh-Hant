---
description: 您可以透過用戶端或伺服器端整合，將符合資格的區段傳送至Google Ad Manager。 以下列出兩種方法的需求和相關資訊。
seo-description: 您可以透過用戶端或伺服器端整合，將符合資格的區段傳送至Google Ad Manager。 以下列出兩種方法的需求和相關資訊。
seo-title: 使用Google Publisher標籤(GPT)將區段傳送至Google廣告管理員的需求與方法
solution: Audience Manager
title: 使用Google Publisher標籤(GPT)將區段傳送至Google廣告管理員的需求與方法
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 使用Google Publisher標籤(GPT){#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}將區段傳送至Google Ad Manager的需求和方法

您可以透過用戶端或伺服器端整合，將合格區段傳送至[!DNL Google Ad Manager]（先前稱為DFP）。 以下列出兩種方法的需求和相關資訊。

## 用戶端整合{#client-side-integration}

對於客戶端整合，您需要在Audience Manager中設定[!DNL GPT]目標。 當您要將[!DNL GPT]設為Audience Manager目的地時，請考慮以下幾點：

* **新增 [!UICONTROL DIL]:** 在 [!UICONTROL Data Integration Library (DIL)] 您要定位的所有頁面上部署程式碼。[!UICONTROL DIL] 將Audience Manager區段資料和使用者ID寫入Cookie，供您用 [!DNL GPT] 於定位。

* **建立 [!UICONTROL Cookie Destination]:** [!DNL GPT] 必須設為Audience Manager中以Cookie為基礎的目標。

* **實作Cookie檢查代碼：將** API方 [!DNL GPT] `.setTargeting` 法包裝在我們建議的 [Cookie檢查代碼中](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)。此程式碼可在`.setTargeting`方法被呼AAM叫之前，先尋找有效的Cookie，協助防止錯誤。

* **新增 `AamGpt` 函式：** 程 `AamGpt` 式碼會從Audience ManagerCookie擷取資料並傳送至 [!DNL GPT]。將[Google Publisher標籤的Audience Manager程式碼(`AamGpt`)置於頁面頂端或`<head>`程式碼區塊內。](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   >[!NOTE]
   >
   >如果您使用自己的程式碼讀取Audience ManagerCookie資料，則不需要`AamGpt`函式。

* **傳送傳送記錄檔至Audience Manager:** 如果您想要區段傳送報表（選用），請為Audience Manager提供包含印象層級傳送資料的每日記錄檔。資料可以是原始格式，但每個記錄必須包含Audience Manager`UUID`。 Audience Manager可以通過[!DNL FTP]接收這些檔案。

### 僅將合格區段傳送至GPT

傳入至[!DNL GPT]的資料量取決於特定使用者符合的區段數。 例如，假設您設定了100個Audience Manager區段。 如果某位網站訪客符合其中5個區段的資格，則只有這5個區段會傳送至[!DNL GPT]（並非全部100）。

>[!NOTE]
>
>您可傳送的索引鍵值數目沒有限制，但[!DNL Google]要求[!DNL URL]的字元數目有限制。 請參閱[使用GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712)設定目標和大小。

## 伺服器端整合{#server-side-integration}

如果您想要使用[!DNL GPT]設定與[!DNL Google Ad Manager]的伺服器端整合，請洽詢您的Audience Manager顧問或客戶服務。 您必須提供[!DNL Google Ad Manager]帳戶網路ID和觀眾連結ID。

>[!IMPORTANT]
>
>如果您的網頁正在執行[加速媒體頁面](https://www.ampproject.org/)([!DNL AMP])程式庫，您必須使用伺服器端與Audience Manager的整合。 如果您位於[!DNL AMP]，且與[!DNL AMP]有用戶端整合，則必須移轉至伺服器端整合。 請聯絡您的Audience Manager顧問或客戶服務以討論移轉事宜。

>[!MORELIKETHIS]
>
>* [GPT API參考指南](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

