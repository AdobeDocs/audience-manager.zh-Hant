---
description: 以人物為基礎的目的地提供多種實作策略，端視客戶資料的結構而定。 根據您的案例，本文提供您需要遵循的以人物為基礎的目的地實作步驟概覽。
seo-description: '以人物為基礎的目的地提供多種實作策略，端視客戶資料的結構而定。 根據您的案例，本文提供您需要遵循的以人物為基礎的目的地實作步驟概覽。  '
seo-title: 以人物為基礎的目的地實作指南
solution: Audience Manager
title: 實施指南
feature: 以人物為基礎的目的地
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 2%

---

# 實施指南{#implementation-guidance}

>[!IMPORTANT]
>本文包含的產品檔案旨在引導您完成此功能的設定與使用。 這裡沒有任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

[!DNL People-Based Destinations] 根據客戶資料的結構方式，提供多種實作策略。本文概略說明您需要遵循[!DNL People-Based Destinations]的實作步驟，視您的案例而定。

## 概述 {#overview}

[!DNL People-Based Destinations]的設定會帶您完成多個Audience Manager區段，並需要不同的設定和資料上線方法，具體取決於您在Audience Manager中已有的客戶資料類型，以及您要執行的對象鎖定目標類型。

>[!IMPORTANT]
> 在配置[!DNL People-Based Destinations]之前，請務必仔細、完整地閱讀本文。 閱讀本指南後，您應已清楚了解將透過[!DNL People-Based Destinations]啟用的案例。

使用[!DNL People-Based Destinations]前，您需要釐清六個實作方面。 本文將協助您了解目前的設定，以便您能正確遵循案例的實作步驟。

![pbd實施](assets/pbd-implementation.png)

## 1.定義使用案例{#defining-your-use-case}

開始實作[!DNL People-Based Destinations]之前，您必須清楚定義將用於此功能的使用案例。 您可以根據對象活動，以兩種方式使用[!DNL People-Based Destinations]來鎖定對象：

**A)根據您合併的線上和離線使用者活動鎖定受眾**。此情境中，您想要結合來自Audience Manager的現有受眾資料與來自內部[!DNL CRM]系統的資料，並將產生的受眾區段傳送至[!DNL People-Based Destinations]。 以下範例說明此情境：

您的公司（一家航空公司）擁有不同的客戶層級（銅牌、銀牌和金牌），而您想要透過社交平台為每個層級提供個人化優惠方案。 您可使用Audience Manager來分析網站上的客戶活動。 不過，並非所有客戶都使用航空公司的行動應用程式，其中有些客戶尚未登入公司網站。 您的客戶資料主要限於會籍ID和電子郵件地址。

若要跨社交媒體和類似以人物為基礎的管道鎖定目標，您可以將您的[雜湊電子郵件地址](people-based-destinations-prerequisites.md)Audience Manager，並將它們與您現有的線上活動特徵結合，以建立新的受眾區段。 接下來，您可以使用這些區段來透過[!DNL People-Based Destinations]鎖定對象。

**B)對象鎖定目標僅根據您的離線使用者活動**。在此案例中，您的[!DNL CRM]系統包含您的客戶電子郵件地址和其他客戶屬性，但客戶完全未與您的網站互動，因此您的Audience Manager中沒有任何客戶活動。 以下範例說明此情境：

您的公司（電信服務提供商）將客戶資料（如電子郵件地址）和購買的電信計畫保留在內部[!DNL CRM]中。 您想要鎖定社交平台中的現有客戶，根據其現有訂閱提供升級套件。 若要這麼做，您可以將雜湊客戶電子郵件地址內嵌至Audience Manager，並根據現有客戶訂閱建立區段。 然後，您可以將這些區段傳送至[!DNL People-Based Destinations]，以使用個人化優惠方案鎖定客戶。

## 2.定義目標電子郵件地址的類型{#define-target-email}

定義實施策略的第二步，是決定您要鎖定的客戶電子郵件地址類型。

**A)根據您已驗證的電子郵件地址進行受眾鎖定目標**。在此案例中，您的使用者有多個帳戶與多個電子郵件地址相關聯，而您只想根據使用者在您網站上即時驗證的電子郵件地址，以個人化優惠方案來鎖定目標。

**B)根據所有相關聯的電子郵件地址鎖定受眾**。在此案例中，您的使用者有多個帳戶與多個電子郵件地址相關聯，而無論已驗證的活動為何，您都想將目標鎖定於所有相關聯的電子郵件地址。

## 3.識別您擁有{#identify-customer-id}的客戶ID(CRM ID)類型

在[!DNL People-Based Destinations]中鎖定目標對象需要您傳送[ SHA256雜湊](people-based-destinations-prerequisites.md)版本的客戶電子郵件地址。 根據您現有的Audience Manager設定，您可能會在下列兩種情況之一中找到自己：

**A)您的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))已是小寫、雜湊的電子郵件地址**。此情境中，您可以使用這些現有ID來鎖定[!DNL People-Based Destinations]中的對象。

**B)您的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))不是小寫、雜湊的電子郵件地址**。在此情況下，您的現有客戶ID無法傳送至[!DNL People-Based Destinations]。 若要使用[!DNL People-Based Destinations]，您需要在現有客戶ID和小寫雜湊版本的客戶電子郵件地址之間執行ID同步。 您可以透過[檔案式ID同步](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)或使用[宣告ID](../declared-ids.md)來執行此作業。

## 4.特徵資格{#trait-qualification}

若要在[!DNL People-Based Destinations]中準確鎖定對象，您的使用者必鬚根據您要執行的對象鎖定目標類型，符合規則型或已上線特徵的資格。

**A)即時符合客戶ID和裝置ID的規則型特徵資格**。此選項適用於[1中的使用案例A。 定義您的使用案例](people-based-destinations-workflow.md#defining-your-use-case)。 如果您的計畫是根據線上和離線活動鎖定對象，則您很可能已經符合對象[規則型特徵](../traits/trait-and-segment-qualification-reference.md)的資格。

**B)透過傳入資料檔案，將特徵帶入客戶ID**。此選項適用於[1中的使用案例B。 定義您的使用案例](people-based-destinations-workflow.md#defining-your-use-case)。 根據純離線活動鎖定目標對象時，您需要透過[傳入資料檔案](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)讓客戶ID符合已上線特徵的資格。

## 5.建立或標籤資料來源及板載雜湊電子郵件地址{#create-label-data-sources}

視您在Audience Manager中的客戶ID類型而定(請參閱[3。 識別您擁有的客戶ID類型(CRM ID)](people-based-destinations-workflow.md#identify-customer-id)，您會在下列其中一種情況下找到自己：

**A)標示現有資料來源**。此選項適用於您的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))已為小寫、雜湊電子郵件地址的案例。 在此情況下，您需要做的是將您儲存ID的資料來源標示為[!DNL PII]資料來源。 有關資料源設定的詳細資訊，請參閱[資料源設定](../datasources-list-and-settings.md)。 您需要執行的是，確認未勾選「無法與個人識別資訊系結」選項。

**B)建立新資料來源**。此選項適用於您的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))未經雜湊電子郵件地址的案例。 在此情況下，您需要建立新的跨裝置資料來源，並將雜湊電子郵件地址上線。 您可以透過兩種方式來執行此作業：

* 使用檔案式 ID 同步。如需 ID 同步檔案的詳細資訊，請參閱 [ID 同步檔案的名稱和內容要求](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)。使用此方法時，您可以鎖定[!DNL CRM]資料庫中的所有雜湊電子郵件地址。
* 傳入已驗證的客戶ID時，請使用[宣告ID](../declared-ids.md)來宣告雜湊電子郵件地址。 使用此方法時，請代表您Audience Manager，只會鎖定已線上驗證之使用者的雜湊電子郵件地址。 以人物為基礎的管道中，目標定位的電子郵件地址只是宣告ID事件呼叫中的電子郵件地址。 與客戶 ID 相關聯的其他電子郵件地址不會即時啟用。

## 6.使用設定檔合併規則進行細分{#use-profile-merge-rules}

視您的使用案例而定(請參閱[1。 定義您的使用案例](people-based-destinations-workflow.md#defining-your-use-case))，有兩種方式可使用[!DNL Profile Merge Rules]進行分段。

**A)使用現有[!DNL Profile Merge Rules]**。此選項適用於第一個使用案例（根據結合的線上和離線使用者活動鎖定目標對象）。 在此案例中，您的Audience Manager中有現有客戶活動，且您已定義至少一個您已用於細分的「設定檔合併規則」。 在這種情況下，您不需要建立任何新的[!DNL Profile Merge Rules]。

**B)建立新的合 [!DNL All Cross-Device Profiles] 並規則**。此選項適用於第二個使用案例（對象鎖定目標僅限根據離線使用者活動）。 在此案例中，您會將[!DNL CRM]的離線客戶資料帶入Audience Manager，並想從該資料建立區段。 為此，[!DNL People-Based Destinations]引進了名為&#x200B;**[!DNL All Cross-Device Profiles]**&#x200B;的新的第四個設定檔合併規則。 這是您在將純離線資料分段時需要使用的規則。
