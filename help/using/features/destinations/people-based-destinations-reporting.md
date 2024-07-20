---
description: 以人物為基礎的目的地為Audience Manager引入可共用對象的概念。 此量度可協助您瞭解Audience Manager可與目的地平台共用多少雜湊電子郵件地址。
seo-description: People-Based Destinations introduce the notion of Shareable Audiences to Audience Manager. This metric helps you understand how many of the hashed email addresses Audience Manager can share with the destination platform.
seo-title: Shareable Audiences
solution: Audience Manager
title: 可共用的受眾
feature: People-based Destinations
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---

# 可共用的受眾 {#shareable-audiences}

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 此處未包含任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

[!DNL People-Based Destinations]將[!DNL Shareable Audiences]的概念帶入Audience Manager。 此量度可協助您瞭解Audience Manager可與目的地平台共用多少雜湊電子郵件地址。

[!DNL Shareable Audiences]是協助您解譯[!DNL People-Based Destinations]內容中對象資料的量度。 您可以在[!UICONTROL Destinations]頁面和[!UICONTROL Segment]頁面中看到此量度。

## 區段可共用的受眾 {#segment-shareable-audiences}

區段頁面中的[!DNL Segment Shareable Audience]量度表示來自資料來源的雜湊電子郵件地址數目，這些地址具有相符的[DPUUID](../../reference/ids-in-aam.md)，在指定的回顧期間內也符合定義的區段（假設已套用設定檔合併規則），而且該Audience Manager可與目的地平台共用。

此量度有1天的回溯期。 這可協助您瞭解特定目的地中區段的受眾觸及率。

## 目的地可共用的對象 {#destination-shareable-audience}

以人物為基礎的目的地頁面中的[!DNL Destination Shareable Audience]量度，代表該Audience Manager可與目的地平台共用的資料來源雜湊電子郵件地址總數（包含相符的[DPUUID](../../reference/ids-in-aam.md)），以及對應至該目的地的所有區段。

![可共用的對象](assets/dest-shareable-audiences.png)

此量度具有期限回顧期間。 這可協助您瞭解從雜湊電子郵件地址資料來源可觸及的受眾規模。

## 範例

Audience Manager客戶的資料來源有110,000個[DPUUID](../../reference/ids-in-aam.md) (CRM ID)。 他們將100,000個雜湊電子郵件地址擷取至Audience Manager，用於多個以人物為基礎的目的地，並針對CRM ID對100,000個雜湊電子郵件地址執行ID同步。 客戶可使用[!DNL All Cross-Device Profiles]合併規則來建立三個受眾區段：

* 母體數為10,000的區段A，已對應至目的地A；
* 人口數為20,000的區段B，已對應至目的地A；
* 母體數為50,000的區段C已對應至目的地B。

在此案例中：

* 區段A可共用的受眾= 10,000；
* 區段B可共用的受眾= 20,000；
* 區段C可共用的受眾= 50,000；
* 目的地A可共用的受眾=區段A可共用的受眾+區段B可共用的受眾= 30,000；
* 目的地B可共用受眾=區段C可共用受眾= 50,000。

![shareable-audiences-diagram](assets/shareable-audiences.png)

>[!NOTE]
>
>在上述範例中，這並不意味著三個區段中的所有80,000個雜湊電子郵件地址都符合目的地平台中的現有帳戶。 這僅表示Audience Manager會從這三個區段將雜湊識別碼傳送至其各自的目的地。 將受眾區段傳送至以人物為基礎的目的地時，會在合作夥伴端進行受眾比對。 目的地A最多可以有30,000個相符的使用者帳戶，而目的地B最多可以有50,000個相符的使用者帳戶，但不保證符合率。 Adobe無法存取合作夥伴特定量度。 若需關於符合率中以人物為基礎的目的地可見度的常見問題，請參閱[符合率](../../faq/faq-people-based-destinations.md#match-rates)。
