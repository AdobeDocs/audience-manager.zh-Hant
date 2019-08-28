---
description: '以人員為基礎的目標將可分享觀眾概念引進Audience Manager。此度量可協助您瞭解Audience Manager可與目標平台共用的雜湊電子郵件地址。 '
seo-description: '以人員為基礎的目標將可分享觀眾概念引進Audience Manager。此度量可協助您瞭解Audience Manager可與目標平台共用的雜湊電子郵件地址。 '
seo-title: 可分享對象
solution: Audience Manager
title: 可分享對象
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# 可分享對象 {#shareable-audiences}

[!DNL People-Based Destinations] 提供Audience [!DNL Shareable Audiences] Manager的概念。此度量可協助您瞭解Audience Manager可與目標平台共用的雜湊電子郵件地址。

[!DNL Shareable Audiences] 是一個度量，可幫助您解譯上下文中的讀者資料 [!DNL People-Based Destinations]。您可以在 [!UICONTROL Destinations] 頁面和 [!UICONTROL Segment] 頁面中查看此量度。

## 區段可分享對象 {#segment-shareable-audiences}

區段頁面中的 [!DNL Segment Shareable Audience] 量度會指出資料來源中的雜湊電子郵件地址數，這 [](../../reference/ids-in-aam.md)在指定的回顧期間內也符合定義的區段，這個規則也適用於指定的回顧期間，而且Audience Manager可與目的地平台共用。

此度量具有天回顧期間。這有助於您瞭解特定目的地中區段的受眾覆蓋範圍。

## 目的地可共用對象 {#destination-shareable-audience}

以人員為基礎的目的地頁面 [!DNL Destination Shareable Audience] 中的量度會指出來自資料來源的雜湊電子郵件地址總份數與目標 [](../../reference/ids-in-aam.md)平台，Audience Manager可從對應到該目的地的所有區段與目的地平台共用。

![可分享觀眾](assets/dest-shareable-audiences.png)

此量度具有終身回顧期間。如此可幫助您瞭解可透過雜湊電子郵件觸及的觀眾等級，以解決資料來源的問題。

## 範例

Audience Manager客戶的資料來源有110,000 [個DPUUID](../../reference/ids-in-aam.md) (CRM ID)。他們會將100,000個雜湊的電子郵件地址嵌入Audience Manager，以便與多個人型目的地搭配使用，並對100，000個雜湊電子郵件地址執行ID同步，以便對CRM ID執行。客戶可以使用 [!DNL All Cross-Device Profiles] 合併規則建立三個對象區段：

* 人口計數為10,000的區段A，映射至目的地A；
* 人口計數為20,000的區段B(對應至目的地A)；
* 人口計數為50,000的區段C已映射至目的地B。

在此情況下：

* 區段A可分享對象=10,000；
* 區段B可分享讀者=20,000；
* 區段C可分享觀眾=50,000；
* 目標一個可分享對象=區段A可分享讀者+區段B可分享對象=30,000；
* 目標B可分享讀者=區段C可分享觀眾=50,000。

![可分享觀眾圖表](assets/shareable-audiences.png)

> [!NOTE]
>
> 在上述範例中，並不表示這三個區段中的80，000個雜湊電子郵件地址與目的地平台中現有的帳戶相符。這只表示Audience Manager會將雜湊識別碼從三個區段傳送至其各自目的地。將觀眾區段傳送至以人為基礎的目的地時，合作夥伴會在合作夥伴端進行配對。目的地A最多可有30，000個相符使用者帳戶，而目的地B最多可有50,000個相符使用者帳戶，但不保證匹配率。Adobe無法存取合作夥伴特定量度。請參閱 [「基於人物目標的目標」常見問題在匹配比率中的匹配比率](../../faq/faq-people-based-destinations.md#match-rates) 。
