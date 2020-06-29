---
description: '以人為本的目的地將「可分享的觀眾」概念引入Audience Manager。 此量度可協助您瞭解Audience Manager可與目標平台共用多少雜湊電子郵件地址。 '
seo-description: '以人為本的目的地將「可分享的觀眾」概念引入Audience Manager。 此量度可協助您瞭解Audience Manager可與目標平台共用多少雜湊電子郵件地址。 '
seo-title: 可共用的受眾
solution: Audience Manager
title: 可共用的受眾
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---


# 可共用的受眾 {#shareable-audiences}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

[!DNL People-Based Destinations] 將概念帶 [!DNL Shareable Audiences] 入Audience Manager。 此量度可協助您瞭解Audience Manager可與目標平台共用多少雜湊電子郵件地址。

[!DNL Shareable Audiences] 是一種度量，可協助您在內容中解譯觀眾資料 [!DNL People-Based Destinations]。 您可以在頁面和頁面 [!UICONTROL Destinations] 中看到此 [!UICONTROL Segment] 度量。

## 區段可分享的觀眾 {#segment-shareable-audiences}

區 [!DNL Segment Shareable Audience] 段頁面中的量度會指出來自資料來源的雜湊電子郵件地址數目與相符的 [DPUUID](../../reference/ids-in-aam.md)，這些DPUUID也符合指定回顧期間中已定義區段的資格，因為套用了描述檔合併規則，而且Audience Manager可與目標平台共用。

此量度有1天回顧期。 這可協助您瞭解特定目的地區隔的受眾觸及面。

## 目標可共用對象 {#destination-shareable-audience}

人 [!DNL Destination Shareable Audience] 員型目標頁面中的量度會指出來自資料來源的雜湊電子郵件地址總數，以及Audience Manager可與目標平台共用的 [DPUUID](../../reference/ids-in-aam.md)，這些DPUUID是來自映射至該目標的所有區段。

![可分享的觀眾](assets/dest-shareable-audiences.png)

此量度具有期限回顧期間。 這可協助您瞭解從雜湊電子郵件地址資料來源可觸及的受眾規模。

## 範例

Audience Manager客戶的資料來源有110,000個 [DPUUID](../../reference/ids-in-aam.md) (CRM ID)。 他們會將100,000個雜湊電子郵件位址擷取至Audience Manager，以便與多個以人為本的目的地搭配使用，並針對CRM ID對100,000個雜湊電子郵件地址執行ID同步。 客戶可使用合併規 [!DNL All Cross-Device Profiles] 則來建立三個對象區段：

* 區段A，人口數為10,000，對應至目標A;
* 區段B，人口計數為20,000，對應至目標A;
* 區段C，人口計數為50,000，對應至目標B。

在此案例中：

* 區隔A可分享的對象= 10,000;
* B區段可分享的對象= 20,000;
* 區段C可分享對象= 50,000;
* 目標A可分享的對象=可分享的對象群體A+可分享的對象群體B=30,000;
* 目標B可分享對象=區段C可分享對象= 50,000。

![可共用的觀眾——圖](assets/shareable-audiences.png)

>[!NOTE]
>
>在上述範例中，這並不表示三個區段的所有80,000個雜湊電子郵件地址都符合目標平台中的現有帳戶。 這僅表示Audience Manager會從三個區段傳送雜湊識別碼至其各自的目的地。 將受眾細分傳送至以人為本的目的地時，合作夥伴會進行受眾比對。 目標A最多可有30,000個相符的使用者帳戶，而目標B最多可能有50,000個相符的使用者帳戶，但無法保證符合率。 Adobe無法存取特定於合作夥伴的量度。 如需相 [符率中](../../faq/faq-people-based-destinations.md#match-rates) 「基於人的目的地可見度」的常見問題，請參閱比對率。
