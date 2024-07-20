---
description: 以人物為基礎的目的地會根據客戶資料的結構方式，提供多種實施策略。 本文會根據您的情境，提供以人物為基礎的目的地所需遵循的實作步驟概述。
seo-description: People-Based Destinations offers multiple implementation strategies, depending on how your customer data is structured. This article provides an overview of the implementation steps that you need to follow for People-Based Destinations, depending on your scenario.
seo-title: People-Based Destinations Implementation Guidance
solution: Audience Manager
title: 實施指導
feature: People-based Destinations
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 2%

---

# 實施指導 {#implementation-guidance}

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 此處未包含任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

[!DNL People-Based Destinations]會根據您客戶資料的結構方式，提供多種實施策略。 本文會根據您的情境，提供您需要針對[!DNL People-Based Destinations]遵循的實施步驟概述。

## 概述 {#overview}

[!DNL People-Based Destinations]的設定會帶您瀏覽多個Audience Manager區段，並需要不同的設定和資料上線方法，具體取決於您在Audience Manager中已有的客戶資料型別，以及您要執行的對象目標定位型別。

>[!IMPORTANT]
> 在設定[!DNL People-Based Destinations]之前，請務必仔細且完整地閱讀本文。 閱讀本指南後，您應該清楚瞭解透過[!DNL People-Based Destinations]啟用的情境。

在使用[!DNL People-Based Destinations]之前，您需要澄清六個實作方面。 本文會幫助您瞭解您目前的設定，以便您可以正確遵循情境的實作步驟。

![pbd — 實作](assets/pbd-implementation.png)

## 1.定義您的使用案例 {#defining-your-use-case}

開始實作[!DNL People-Based Destinations]之前，您必須明確定義您將使用此功能的使用案例。 您可以根據對象活動，以兩種方式使用[!DNL People-Based Destinations]來鎖定對象：

**A)根據您的線上和離線使用者活動合併的受眾目標定位**。 在此案例中，您想要結合Audience Manager的現有對象資料與內部[!DNL CRM]系統的資料，並將產生的對象區段傳送至[!DNL People-Based Destinations]。 以下是說明此情況的範例：

貴公司是一家航空公司，擁有不同的客戶層級（銅、銀和金），而您希望透過社交平台為每個層級提供個人化優惠。 您可以使用Audience Manager來分析網站上的客戶活動。 不過，並非所有客戶都使用航空公司的行動應用程式，其中部分客戶尚未登入公司網站。 您的客戶資料大多僅限於會員ID和電子郵件地址。

若要在社群媒體和類似的以人物為基礎的頻道中鎖定這些對象，您可以將[雜湊電子郵件地址](people-based-destinations-prerequisites.md)納入Audience Manager，並將其與您現有的線上活動特徵結合，以建立新的對象區段。 接下來，您可以透過[!DNL People-Based Destinations]使用這些區段來鎖定您的對象。

**B)僅根據您的離線使用者活動進行對象目標定位**。 在此案例中，您的[!DNL CRM]系統包含您的客戶電子郵件地址和其他客戶屬性，但客戶完全沒有與您的網站互動，因此您在Audience Manager中沒有任何客戶活動。 以下是說明此情況的範例：

您的公司是電信服務提供者，會將客戶資料（如電子郵件地址）和購買的電信方案保留在內部[!DNL CRM]中。 您想要在社交平台中鎖定現有客戶，以根據其現有訂閱提供升級套件。 若要這麼做，您可以將雜湊的客戶電子郵件地址擷取至Audience Manager，並根據現有的客戶訂閱建立區段。 然後，您可以傳送這些區段至[!DNL People-Based Destinations]，以個人化優惠定位您的客戶。

## 2.定義目標電子郵件地址的型別 {#define-target-email}

定義實作策略的第二個步驟，是決定您要鎖定的客戶電子郵件地址型別。

**A)根據您驗證的電子郵件地址來鎖定受眾目標**。 在此案例中，您的使用者有多個與多個電子郵件地址相關聯的帳戶，而您想要僅根據他們在您的網站上即時驗證的電子郵件地址，透過個人化優惠來鎖定他們。

**B)根據您所有關聯的電子郵件地址來鎖定受眾目標**。 在此案例中，您的使用者有多個與多個電子郵件地址相關聯的帳戶，而您想要跨所有相關聯的電子郵件地址來鎖定這些帳戶，無論已驗證的活動為何。

## 3.識別您擁有的客戶ID (CRM ID)型別 {#identify-customer-id}

在[!DNL People-Based Destinations]中鎖定目標對象需要您傳送客戶電子郵件地址的[SHA256雜湊](people-based-destinations-prerequisites.md)版本。 根據您現有的Audience Manager設定，您可能會發現自己處於以下兩種情況之一：

**A)您的Audience Manager客戶ID ([DPUUID](../../reference/ids-in-aam.md))已經是小寫、雜湊的電子郵件地址**。 在此案例中，您可以使用這些現有的ID在[!DNL People-Based Destinations]中鎖定您的對象。

**B)您的Audience Manager客戶識別碼([DPUUID](../../reference/ids-in-aam.md))不是小寫、雜湊電子郵件地址**。 在此案例中，您現有的客戶ID無法傳送至[!DNL People-Based Destinations]。 若要使用[!DNL People-Based Destinations]，您必須在現有客戶ID與小寫、雜湊版本的客戶電子郵件地址之間執行ID同步。 您可以透過[以檔案為基礎的ID同步處理](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)或使用[宣告的ID](../declared-ids.md)來執行此作業。

## 4.特徵資格 {#trait-qualification}

若要在[!DNL People-Based Destinations]中準確鎖定您的對象，您的使用者必須符合規則型或已上線特徵，視您要執行的對象鎖定目標型別而定。

**A)即時讓您的客戶ID和裝置ID符合規則型特徵**。 此選項適用於[1的使用案例A。 定義您的使用案例](people-based-destinations-workflow.md#defining-your-use-case)。 如果您的計畫是根據線上和離線活動來鎖定對象，那麼您很可能已經讓對象符合[規則型特徵](../traits/trait-and-segment-qualification-reference.md)。

**B)透過傳入資料檔針對您的客戶ID將特徵上線**。 此選項適用於[1的使用案例B。 定義您的使用案例](people-based-destinations-workflow.md#defining-your-use-case)。 以純離線活動鎖定您的對象時，您需要透過[傳入資料檔](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)來限定客戶ID的已上線特徵。

## 5.建立或標示資料來源及上線雜湊電子郵件地址 {#create-label-data-sources}

視您在Audience Manager中的客戶ID型別而定(請參閱[3。 識別您擁有](people-based-destinations-workflow.md#identify-customer-id)的客戶ID (CRM ID)型別，您會在下列其中一種情況中找到自己：

**A)標籤現有的資料來源**。 此選項適用於您的Audience Manager客戶ID ([DPUUID](../../reference/ids-in-aam.md))已經是小寫、雜湊電子郵件地址的情況。 在此情況下，您需要做的是將您儲存ID的資料來源標示為[!DNL PII]資料來源。 如需資料來源設定的詳細資訊，請參閱[資料Source設定](../datasources-list-and-settings.md)。 您必須確認未勾選「無法繫結至個人識別資訊」選項。

**B)建立新的資料來源**。 此選項適用於您的Audience Manager客戶ID ([DPUUID](../../reference/ids-in-aam.md))不是雜湊電子郵件地址的情況。 在這種情況下，您需要建立新的跨裝置資料來源，並針對該來源加入雜湊電子郵件地址。 您可以透過兩種方式達成此目的：

* 使用檔案式ID同步。 如需 ID 同步檔案的詳細資訊，請參閱 [ID 同步檔案的名稱和內容要求](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)。使用此方法時，您可以鎖定[!DNL CRM]資料庫中的所有雜湊電子郵件地址。
* 傳入已驗證的客戶ID時，請使用[宣告ID](../declared-ids.md)來宣告雜湊的電子郵件地址。 使用此方法時，代表您Audience Manager僅會鎖定已線上驗證的使用者之雜湊電子郵件地址。 以人物為基礎的管道中所定位的電子郵件地址，只是宣告ID事件呼叫中的電子郵件地址。 與客戶 ID 相關聯的其他電子郵件地址不會即時啟用。

## 6.使用設定檔合併規則進行分段 {#use-profile-merge-rules}

視您的使用案例而定(請參閱[1。 定義您的使用案例](people-based-destinations-workflow.md#defining-your-use-case))，有兩種方式可使用[!DNL Profile Merge Rules]進行分段。

**A)使用現有的[!DNL Profile Merge Rules]**。 此選項適用於第一個使用案例（根據合併的線上和離線使用者活動的對象目標定位）。 在此案例中，您在Audience Manager中有現有的客戶活動，且您已定義至少一個您已在細分中使用的設定檔合併規則。 在此情況下，您不需要建立任何新的[!DNL Profile Merge Rules]。

**B)建立新的[!DNL All Cross-Device Profiles]合併規則**。 此選項適用於第二個使用案例（對象鎖定目標僅以離線使用者活動為基礎）。 在此案例中，您要將離線客戶資料從您的[!DNL CRM]帶入Audience Manager，並想要從該資料建立區段。 為此，[!DNL People-Based Destinations]引入新的第四個設定檔合併規則，稱為&#x200B;**[!DNL All Cross-Device Profiles]**。 這是您在純離線資料分段時需要使用的規則。
