---
description: 您可以透過用戶端或伺服器端整合，將合格區段傳送至Google Ad Manager。 以下列出兩種方法的需求和相關資訊。
seo-description: 您可以透過用戶端或伺服器端整合，將合格區段傳送至Google Ad Manager。 以下列出兩種方法的需求和相關資訊。
seo-title: 使用Google發佈商代碼(GPT)傳送區段至Google Ad Manager的需求和方法
solution: Audience Manager
title: 使用Google發佈商代碼(GPT)傳送區段至Google Ad Manager的需求和方法
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: 協力廠商整合
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# 使用Google發佈商代碼(GPT){#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}傳送區段至Google Ad Manager的需求和方法

您可以透過用戶端或伺服器端整合，將合格區段傳送至[!DNL Google Ad Manager]（原稱DFP）。 以下列出兩種方法的需求和相關資訊。

## 用戶端整合{#client-side-integration}

若為用戶端整合，您需要在Audience Manager中設定[!DNL GPT]目的地。 想要將[!DNL GPT]設定為Audience Manager目的地時，請考量下列幾點：

* **新 [!UICONTROL DIL]增：** 在 [!UICONTROL Data Integration Library (DIL)] 您要鎖定的所有頁面上部署程式碼。[!UICONTROL DIL] 將Audience Manager區段資料和使用者ID寫入供鎖定目標使用 [!DNL GPT] 的Cookie。

* **建立 [!UICONTROL Cookie Destination]:** [!DNL GPT] 必須設為Audience Manager中的Cookie型目的地。

* **實作Cookie檢查程式碼：** 將API方 [!DNL GPT] `.setTargeting` 法包裝在我們建議的Cookie檢 [查程式碼中](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)。在叫用`.setTargeting`方法之前，請先尋找有效的AAM Cookie，此程式碼可協助您避免錯誤。

* **新增 `AamGpt` 函式：** 程式 `AamGpt` 碼會從Audience ManagerCookie擷取資料並將其傳送 [!DNL GPT]至。將[Google發佈商標籤的Audience Manager代碼](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)(`AamGpt`)放在頁面頂端或`<head>`代碼區塊內。

   >[!NOTE]
   >
   >如果您使用自己的程式碼來讀取Audience ManagerCookie資料，則不需要`AamGpt`函式。

* **傳送傳送記錄檔至Audience Manager:** 如果您想要區段傳送報表（選用），請為Audience Manager提供包含曝光層級傳送資料的每日記錄檔。資料可以是原始格式，但每個記錄必須包含Audience Manager`UUID`。 Audience Manager可以透過[!DNL FTP]接收這些檔案。

### 只有合格區段會傳送至GPT

傳遞至[!DNL GPT]的資料量取決於特定使用者符合的區段數。 例如，假設您設定100個Audience Manager區段。 如果網站訪客符合其中5個區段的資格，則只有這5個區段會傳送至[!DNL GPT]（並非全部100個）。

>[!NOTE]
>
>您可以傳送的鍵值數目沒有限制，但[!DNL Google]要求[!DNL URL]對其可接受的字元數目沒有限制。 請參閱[使用GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712)設定目標和大小。

## 伺服器端整合{#server-side-integration}

如果您想使用[!DNL GPT]來設定與[!DNL Google Ad Manager]的伺服器端整合，請洽詢您的Audience Manager顧問或客戶服務。 您需要提供[!DNL Google Ad Manager]帳戶網路ID和對象連結ID。

>[!IMPORTANT]
>
>如果您的網頁執行的是[Accelerated Media Pages](https://www.ampproject.org/)([!DNL AMP])程式庫，您必須搭配Audience Manager使用伺服器端整合。 如果您位於[!DNL AMP]且與[!DNL AMP]有用戶端整合，則必須移轉至伺服器端整合。 請連絡您的Audience Manager顧問或客戶服務，討論移轉事宜。

>[!MORELIKETHIS]
>
>* [GPT API參考指南](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

