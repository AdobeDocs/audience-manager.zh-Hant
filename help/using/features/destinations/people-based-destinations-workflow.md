---
description: 基於人員的目標提供多種實施策略，取決於客戶資料的結構。本文章概述根據您的藍本而定，您需要遵循的實施步驟。
seo-description: '基於人員的目標提供多種實施策略，取決於客戶資料的結構。本文章概述根據您的藍本而定，您需要遵循的實施步驟。  '
seo-title: 人員目標實施指引
solution: Audience Manager
title: 實施指引
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# 實施指引 {#implementation-guidance}

[!DNL People-Based Destinations] 提供多種實施策略，視客戶資料的結構而定。本文章概述依您的情況而定的 [!DNL People-Based Destinations]實施步驟。

## 概述 {#overview}

您可透過Audience Manager的多個區段 [!DNL People-Based Destinations] 進行設定，並需要不同的設定和資料入門方法，視您在Audience Manager中已擁有的客戶資料，以及想要執行何種目標鎖定而定。

>[!IMPORTANT]
> 在設定 [!DNL People-Based Destinations]之前，請務必仔細且完整地閱讀本文章。閱讀本指南後，您應清楚瞭解您要啓用 [!DNL People-Based Destinations]的情境。

在使用 [!DNL People-Based Destinations]之前，您需要先釐清個實施層面。本文將協助您瞭解目前設定的意義，以便正確遵循藍本的實施步驟。

![pdd-implementation](assets/pbd-implementation.png)

## 1. 定義您的使用案例 {#defining-your-use-case}

在開始實作 [!DNL People-Based Destinations]之前，您必須明確定義您將使用此功能的使用案例。您可以根據 [!DNL People-Based Destinations] 對象活動以兩種方式來定位對象：

**A) 根據線上和離線使用者活動**&#x200B;來鎖定受眾。在此情況下，您想要將Audience Manager現有的觀眾資料與來自內部 [!DNL CRM] 系統的資料結合，並將產生的觀眾區段傳送至 [!DNL People-Based Destinations]。以下是此案例的範例：

您的公司公司擁有不同的客戶層(銅級、銀級和金級)，而且您想要透過社交平台提供個人化優惠。您可以使用Audience Manager分析網站上的客戶活動。但是，並非所有客戶都使用該航空公司的行動應用程式，而有些客戶甚至從未登入公司的網站。您的客戶資料主要限於會籍ID和電子郵件地址。

為了跨社交媒體和類似的人群通道進行鎖定，您可以將 [雜湊電子郵件地址](people-based-destinations-prerequisites.md) 帶入Audience Manager，並將其與現有的線上活動特徵結合，以建立新的受眾細分。接下來，您可以使用這些群體來定位受眾 [!DNL People-Based Destinations]。

**B) 基於離線使用者活動的受眾鎖定**。在這種情況下， [!DNL CRM] 您的系統包含客戶電子郵件地址和其他客戶屬性，但客戶完全沒有與您的網站互動，因此您在Audience Manager中沒有任何客戶活動。以下是此案例的範例：

您的公司是電信服務供應商，負責維護客戶資料，例如電子郵件地址，並在內部購買電信計劃 [!DNL CRM]。您想要定位社交平台中的現有客戶，以根據現有訂閱提供升級套件。若要這麼做，您可以將雜湊的客戶電子郵件地址嵌入Audience Manager中，並根據現有客戶訂閱建立區段。然後，您可以將這些區段 [!DNL People-Based Destinations] 傳送給客戶，以提供個人化優惠。

## 2. 定義目標電子郵件地址的類型 {#define-target-email}

定義實施策略的第二個步驟是決定要定位的客戶電子郵件地址類型。

**A) 根據已驗證的電子郵件地址鎖定受眾**。在這種情況下，您的使用者有多個與多個電子郵件地址關聯的帳戶，而您想要透過個人化選件鎖定他們，這只會根據他們在網站上驗證的電子郵件地址來定位。

**B) 根據所有相關聯的電子郵件地址鎖定受眾**。在此情況下，您的使用者擁有多個與多個電子郵件地址關聯的帳戶，而您想要將其定位在所有關聯的電子郵件地址中，不論已驗證的活動為何。

## 3. 識別您擁有的客戶ID類型(CRM ID) {#identify-customer-id}

鎖定受眾 [!DNL People-Based Destinations] 需要您傳送 [SHA256雜湊](people-based-destinations-prerequisites.md) 版本的客戶電子郵件地址。根據您現有的Audience Manager設定，您可能會發現下列兩種情況之一：

**A) 您的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))已經是小寫、雜湊電子郵件地址**。在此情況下，您可以使用這些現有ID來定位您的觀眾 [!DNL People-Based Destinations]。

**B) 您的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))不是小寫、雜湊電子郵件地址**。在此情況下，您現有的客戶ID無法傳送 [!DNL People-Based Destinations]至。若要使用 [!DNL People-Based Destinations]，您必須在現有客戶ID和小寫、雜湊版本的客戶電子郵件地址之間執行ID同步。您可以透過 [檔案ID同步或](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 使用 [宣告的ID](../declared-ids.md)進行這項作業。

## 4. 特徵資格 {#trait-qualification}

為了準確定位受眾， [!DNL People-Based Destinations]您的使用者必須符合規則型或已上線的特性，視您要執行的對象目標類型而定。

**A) 即時符合規則特徵**&#x200B;的客戶ID和裝置ID。此選項適用於從 [1使用個案A。定義您的使用案例](people-based-destinations-workflow.md#defining-your-use-case)。如果您的計劃是根據線上和線下活動來定位受眾，則您很有可能符合 [規則特徵的讀者](../traits/trait-qualification-reference.md)資格。

**B) 透過傳入的資料檔案，對客戶ID進行到職特徵**。此選項適用於從 [1使用個案B。定義您的使用案例](people-based-destinations-workflow.md#defining-your-use-case)。根據純粹離線活動鎖定受眾時，您需要透過 [傳入的資料檔案，針對已登錄的特性取得客戶ID](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。

## 5. 建立或標籤資料來源和上線雜湊電子郵件地址 {#create-label-data-sources}

視您在Audience Manager中擁有的客戶ID類型而定(請參閱 [3。識別您擁有的客戶ID類型(CRM ID)](people-based-destinations-workflow.md#identify-customer-id)，您會發現下列情形之一：

**A) 標籤現有資料來源**。此選項適用於您的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))為小寫、雜湊電子郵件地址的藍本。在此情況下，您需要做的，是標示您將ID儲存在 [!DNL PII] 資料來源中的資料來源。如需資料來源設定的詳細資訊，請參閱 [資料來源設定](../datasources-list-and-settings.md) 。您需要做的，是確定不會勾選無法與個人識別資訊選項系結。

**B) 建立新資料來源**。此選項適用於您的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))不是雜湊電子郵件地址的藍本。在這種情況下，您需要建立新的跨裝置資料來源，並將雜湊電子郵件地址置於其中。您可以透過兩種方式做到：

* 使用檔案ID同步。如需ID同步檔案的詳細資訊，請參閱 [ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 的名稱和內容需求。使用此方法時，您可以從 [!DNL CRM] 資料庫鎖定所有雜湊的電子郵件地址。
* 在通過驗證的客戶ID時，使用 [宣告的ID](../declared-ids.md) 宣告雜湊電子郵件地址。使用此方法時，Audience Manager只會鎖定已進行線上驗證的使用者的雜湊電子郵件地址。透過Facebook定位的電子郵件地址僅為宣告ID事件呼叫中的一個。與客戶ID相關聯的其他電子郵件地址不會即時啓用。

## 6. 使用區段合併規則進行分段 {#use-profile-merge-rules}

視您的使用案例而定(請參閱 [1)。定義您的使用案例](people-based-destinations-workflow.md#defining-your-use-case))有兩種用於 [!DNL Profile Merge Rules] 劃分的方法。

**A) 使用現有[!DNL Profile Merge Rules]**。此選項適用於第一個使用案例(根據結合線上和離線使用者活動的對象鎖定)。在這種情況下，您在Audience Manager中已有現有的客戶活動，且已經定義了至少一個用於分段的「設定檔合併規則」。在這種情況下，您不需要建立任何新 [!DNL Profile Merge Rules]功能。

**B) 建立新[!DNL All Cross-Device Profiles]的合併規則**。此選項適用於第二個使用案例(基於離線使用者活動的對象鎖定)。在這種情況下，您將離線客戶資料從您 [!DNL CRM] 的Audience Manager帶入，並希望從該資料建立區段。若要這麼做， [!DNL People-Based Destinations] 請引入新的第四個描述檔合併規則，名為 **[!DNL All Cross-Device Profiles]**。這是您在分段純離線資料時需要使用的規則。
