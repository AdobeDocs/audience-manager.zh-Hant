---
description: '以人物為基礎的目的地引入了「可分享的對象」概念以供Audience Manager。 此量度可協助您了解雜湊電子郵件地址Audience Manager可與目的地平台共用的數量。 '
seo-description: '以人物為基礎的目的地引入了「可分享的對象」概念以供Audience Manager。 此量度可協助您了解雜湊電子郵件地址Audience Manager可與目的地平台共用的數量。 '
seo-title: 可共用的受眾
solution: Audience Manager
title: 可共用的受眾
feature: 以人物為基礎的目的地
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# 可共用的受眾 {#shareable-audiences}

>[!IMPORTANT]
>本文包含的產品檔案旨在引導您完成此功能的設定與使用。 這裡沒有任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

[!DNL People-Based Destinations] 將概念帶 [!DNL Shareable Audiences] 入Audience Manager。此量度可協助您了解雜湊電子郵件地址Audience Manager可與目的地平台共用的數量。

[!DNL Shareable Audiences] 是可協助您在內容中解讀對象資料的量 [!DNL People-Based Destinations]度。您可以在[!UICONTROL Destinations]頁面和[!UICONTROL Segment]頁面中看到此量度。

## 區段可共用受眾{#segment-shareable-audiences}

區段頁面中的[!DNL Segment Shareable Audience]量度會指出來自資料來源且符合[DPUUID](../../reference/ids-in-aam.md)的雜湊電子郵件地址數量，只要套用的設定檔合併規則，該量度在指定回顧期間內也符合定義區段的資格，且該Audience Manager可與目標平台共用。

此量度有1天回顧期間。 這可協助您了解特定目的地區段的對象觸及率。

## 目標可共用受眾{#destination-shareable-audience}

以人物為基礎的目的地頁面中的[!DNL Destination Shareable Audience]量度會指出來自資料來源的雜湊電子郵件地址總數，而符合[DPUUID](../../reference/ids-in-aam.md)的Audience Manager可從對應至該目的地的所有區段與目的地平台共用。

![可共用的受眾](assets/dest-shareable-audiences.png)

此量度具有期限回顧期間。 這可協助您了解從雜湊電子郵件地址資料來源可觸及的對象規模。

## 範例

Audience Manager客戶的資料來源為110,000 [DPUUIDs](../../reference/ids-in-aam.md)(CRM ID)。 他們會將100,000個雜湊電子郵件地址擷取至Audience Manager，以便與多個以人物為基礎的目的地搭配使用，並針對CRM ID對100,000個雜湊電子郵件地址執行ID同步。 客戶可使用[!DNL All Cross-Device Profiles]合併規則來建立三個受眾區段：

* 區段A，人口計數為10,000，對應至目的地A;
* 區段B，人口計數為20,000，對應至目的地A;
* 區段C，人口計數為50,000，對應至目的地B。

此情境中：

* 劃分A可共用受眾= 10,000;
* 區段B可分享的受眾= 20,000;
* 區段C可分享的受眾= 50,000;
* 目的地A可分享的受眾=區隔可分享的受眾+區隔B可分享的受眾= 30,000;
* 目的地B可共用的受眾=區段C可共用的受眾= 50,000。

![可共用對象圖](assets/shareable-audiences.png)

>[!NOTE]
>
>在上述範例中，這並不意味著三個區段的所有80,000個雜湊電子郵件地址都符合目標平台中的現有帳戶。 這隻表示Audience Manager會將三個區段的雜湊識別碼傳送至其個別目的地。 將受眾區段傳送至以人物為基礎的目的地時，會在合作夥伴端進行受眾比對。 目的地A最多可以有30,000個相符的使用者帳戶，而目的地B最多可以有50,000個相符的使用者帳戶，但無法保證符合率。 Adobe無法存取合作夥伴特定量度。 如需符合率中以人物為基礎的目的地可見性的相關常見問題，請參閱[符合率](../../faq/faq-people-based-destinations.md#match-rates)。
