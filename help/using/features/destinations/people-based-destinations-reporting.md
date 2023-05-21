---
description: 基於人的目的地將可共用受眾的概念引入Audience Manager。 此度量有助於您瞭解Audience Manager可以與目標平台共用多少個散列電子郵件地址。
seo-description: People-Based Destinations introduce the notion of Shareable Audiences to Audience Manager. This metric helps you understand how many of the hashed email addresses Audience Manager can share with the destination platform.
seo-title: Shareable Audiences
solution: Audience Manager
title: 可共用的受眾
feature: People-based Destinations
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 1%

---

# 可共用的受眾 {#shareable-audiences}

>[!IMPORTANT]
>本文包含旨在指導您完成此功能的設定和使用的產品文檔。 這裡沒有法律建議。 請咨詢您自己的法律顧問以獲得法律指導。

[!DNL People-Based Destinations] 帶來了 [!DNL Shareable Audiences] Audience Manager。 此度量有助於您瞭解Audience Manager可以與目標平台共用多少個散列電子郵件地址。

[!DNL Shareable Audiences] 是一種在您閱讀時 [!DNL People-Based Destinations]。 您可以在 [!UICONTROL Destinations] 的 [!UICONTROL Segment] 的子菜單。

## 可共用的受眾 {#segment-shareable-audiences}

的 [!DNL Segment Shareable Audience] 「段」頁中的度量指示來自資料源的散列電子郵件地址的數量與 [DPUUID](../../reference/ids-in-aam.md)，在給定的回查時段內，如果應用了配置檔案合併規則，則該Audience Manager也符合定義的段，並且該段可以與目標平台共用。

此度量具有1天回顧期。 這有助於您瞭解特定目標中該段的受眾。

## 目標可共用受眾 {#destination-shareable-audience}

的 [!DNL Destination Shareable Audience] 基於人員的目標頁中的度量指示來自資料源的散列電子郵件地址的總數，該地址與 [DPUUID](../../reference/ids-in-aam.md)，該Audience Manager可以與目標平台共用映射到該目標的所有段。

![可共用的觀眾](assets/dest-shareable-audiences.png)

此度量具有生命期回溯週期。 這有助於您瞭解您可以從散列電子郵件地址資料源訪問的受眾規模。

## 範例

Audience Manager客戶的資料源為110,000 [DPUUID](../../reference/ids-in-aam.md) (CRM ID)。 他們將100,000個哈希電子郵件地址錄入Audience Manager，以便與多個基於人員的目標一起使用，並根據CRM ID對100,000個哈希電子郵件地址執行ID同步。 客戶可使用 [!DNL All Cross-Device Profiles] 合併規則可建立三個受眾段：

* A段，人口數為10,000，映射到目標A;
* B段，人口數為20,000，映射到目標A;
* 人口數為50,000的段C映射到目標B。

在此情形中：

* A部分可共用受眾= 10 000;
* B類可分享受眾= 20 000;
* C類可分享受眾= 50 000;
* 目標A可共用受眾=可共用受眾群A分段+可共用受眾群B分段= 30,000;
* 目標B可共用受眾= C可共用受眾= 50,000。

![可共用的觀眾圖](assets/shareable-audiences.png)

>[!NOTE]
>
>在上例中，這並不意味著三個網段中所有80,000個散列電子郵件地址都與目標平台中的現有帳戶匹配。 它只表示Audience Manager將散列標識符從三個段發送到它們各自的目的地。 當將受眾段發送到基於人的目標時，在合作夥伴端進行受眾匹配。 目標A最多可以有30,000個匹配的用戶帳戶，而目標B最多可以有50,000個匹配的用戶帳戶，但無法保證匹配率。 Adobe無權訪問特定於合作夥伴的指標。 請參閱 [匹配率](../../faq/faq-people-based-destinations.md#match-rates) 查找有關匹配率中基於人員的目標可見性的常見問題。
