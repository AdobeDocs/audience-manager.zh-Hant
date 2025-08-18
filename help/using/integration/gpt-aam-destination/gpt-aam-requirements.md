---
description: 您可以透過使用者端或伺服器端整合，將合格的區段傳送至Google Ad Manager。 以下列出這兩種方法的需求和相關資訊。
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: 使用Google發佈商代碼(GPT)傳送區段至Google Ad Manager的需求和方法
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# 使用Google發佈商代碼(GPT)傳送區段至Google Ad Manager的需求和方法 {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

您可以透過使用者端或伺服器端整合將合格的區段傳送至[!DNL Google Ad Manager] （原稱DFP）。 以下列出這兩種方法的需求和相關資訊。

## 使用者端整合 {#client-side-integration}

若要進行使用者端整合，您必須在Audience Manager中設定[!DNL GPT]目的地。 當您想要將[!DNL GPT]設定為Audience Manager目的地時，請考慮以下幾點：

* **新增[!UICONTROL DIL]：**&#x200B;在您要鎖定的所有頁面上部署[!UICONTROL Data Integration Library (DIL)]程式碼。 [!UICONTROL DIL]會將Audience Manager區段資料和使用者ID寫入[!DNL GPT]用來鎖定目標的Cookie。

* **建立[!UICONTROL Cookie Destination]：** [!DNL GPT]必須設定為Audience Manager中以Cookie為基礎的目的地。

* **實作Cookie檢查程式碼：**&#x200B;將[!DNL GPT] `.setTargeting` API方法包裝在我們建議的[Cookie檢查程式碼](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)中。 此程式碼會在叫用`.setTargeting`方法之前尋找有效的AAM Cookie，以協助避免發生錯誤。

* **新增`AamGpt`函式：** `AamGpt`程式碼會從Audience Manager Cookie擷取資料，並將其傳送至[!DNL GPT]。 將Google發行者標籤的[Audience Manager程式碼](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`)放在頁面頂端或`<head>`程式碼區塊內。

  >[!NOTE]
  >
  >如果您使用自己的程式碼來讀取Audience Manager Cookie資料，則不需要使用`AamGpt`函式。

* **傳送傳遞記錄至Audience Manager：**&#x200B;如果您想要區段傳遞報告（選用），請為Audience Manager提供包含曝光層級傳遞資料的每日記錄。 資料可以是原始格式，但每筆記錄都必須包含Audience Manager `UUID`。 Audience Manager可以透過[!DNL FTP]收取或接收這些訊息。

### 只有合格的區段才會傳送至GPT

傳入[!DNL GPT]的資料量取決於特定使用者符合的區段數。 例如，假設您設定100個Audience Manager區段。 如果網站訪客符合其中五個區段的資格，則只會將這五個區段傳送至[!DNL GPT] （並非全部100個）。

>[!NOTE]
>
>您可以傳送的索引鍵值數目沒有限制，但[!DNL Google]要求[!DNL URL]確實有可接受的字元數目限制。 請參閱[使用GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712)設定目標定位與大小。

## 伺服器端整合 {#server-side-integration}

如果您想要使用[!DNL Google Ad Manager]設定與[!DNL GPT]的伺服器端整合，請洽詢您的Audience Manager顧問或客戶服務。 您必須提供您的[!DNL Google Ad Manager]帳戶網路識別碼和對象連結識別碼。

>[!IMPORTANT]
>
>如果您的網頁正在執行[Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP])資料庫，您必須使用伺服器端與Audience Manager的整合。 如果您位於[!DNL AMP]並且與[!DNL AMP]進行使用者端整合，則必須移轉至伺服器端整合。 請聯絡您的Audience Manager顧問或客戶服務，討論移轉事宜。

>[!MORELIKETHIS]
>
>* [GPT API參考指南](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)
