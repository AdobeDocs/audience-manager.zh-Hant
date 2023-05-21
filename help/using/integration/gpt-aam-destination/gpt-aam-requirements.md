---
description: 您可以通過客戶端或伺服器端整合將限定的段發送到Google廣告管理器。 下面列出了有關這兩種方法的要求和相關資訊。
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: 使用Google發佈器標籤(GPT)向Google廣告管理器發送段的要求和方法
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# 使用Google發佈者標籤(GPT)向Google廣告管理器發送段的要求和方法 {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

可將限定段發送到 [!DNL Google Ad Manager] （以前稱為DFP），通過客戶端或伺服器端整合。 下面列出了有關這兩種方法的要求和相關資訊。

## 客戶端整合 {#client-side-integration}

對於客戶端整合，您需要設定 [!DNL GPT] 目標Audience Manager。 要設定時請考慮以下幾點 [!DNL GPT] 作為Audience Manager目標：

* **添加 [!UICONTROL DIL]:** 部署 [!UICONTROL Data Integration Library (DIL)] 要瞄準的所有頁面上的代碼。 [!UICONTROL DIL] 將Audience Manager段資料和用戶ID寫入Cookie中， [!DNL GPT] 目標。

* **建立 [!UICONTROL Cookie Destination]:** [!DNL GPT] 必須設定為Audience Manager中的基於cookie的目標。

* **實現Cookie檢查代碼：** 繞排 [!DNL GPT] `.setTargeting` 我們推薦的API方法 [Cookie檢查代碼](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)。 此代碼通過在Cookie之前查找有效AAM的Cookie幫助防止錯誤 `.setTargeting` 調用方法。

* **添加 `AamGpt` 函式：** 的 `AamGpt` 代碼從Audience Managercookie中捕獲資料並將其發送到 [!DNL GPT]。 放置 [Audience ManagerGoogle發佈者標籤代碼](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`)，位於頁面頂部或 `<head>` 代碼塊。

   >[!NOTE]
   >
   >的 `AamGpt` 如果使用您自己的代碼讀取Audience Managercookie資料，則不需要函式。

* **將傳遞日誌發送到Audience Manager:** 如果要生成段交貨報表（可選），請向Audience Manager提供包含印象級交貨資料的日誌。 資料可以是原始格式，但每條記錄必須包含Audience Manager `UUID`。 Audience Manager可以通過 [!DNL FTP]。

### 只將限定段發送到GPT

傳入到的資料量 [!DNL GPT] 取決於特定用戶需要多少段。 例如，假設您設定了100個Audience Manager段。 如果站點訪問者有資格獲得其中五個，則僅將這五個段發送給 [!DNL GPT] （不是全部100個）。

>[!NOTE]
>
>您可以發送的鍵值數沒有限制，但 [!DNL Google] 請求 [!DNL URL] 對它可接受的字元數有限制。 請參閱 [使用GPT設定目標和大小](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712)。

## 伺服器端整合 {#server-side-integration}

如果您想與Audience Manager顧問或客戶服務部門建立伺服器端整合，請與 [!DNL Google Ad Manager]，使用 [!DNL GPT]。 你需要提供 [!DNL Google Ad Manager] 帳戶網路ID和受眾連結ID。

>[!IMPORTANT]
>
>如果您的網頁正在運行 [加速的媒體頁](https://www.ampproject.org/) ([!DNL AMP])庫，您必須使用與Audience Manager的伺服器端整合。 如果你在 [!DNL AMP] 與 [!DNL AMP]，必須遷移到伺服器端整合。 請聯繫您的Audience Manager顧問或客戶服務以討論遷移。

>[!MORELIKETHIS]
>
>* [GPT API參考指南](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

