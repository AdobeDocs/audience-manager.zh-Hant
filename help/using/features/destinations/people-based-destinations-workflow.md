---
description: 「以人為本的目標」提供多種實作策略，視客戶資料的結構而定。 本文概述了您在「以人為本的目標」上需要遵循的實作步驟，視您的藍本而定。
seo-description: '「以人為本的目標」提供多種實作策略，視客戶資料的結構而定。 本文概述了您在「以人為本的目標」上需要遵循的實作步驟，視您的藍本而定。  '
seo-title: 以人為本的目的地實作指引
solution: Audience Manager
title: 實施指南
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

---


# 實施指南 {#implementation-guidance}

[!DNL People-Based Destinations] 根據客戶資料的結構，提供多種實作策略。 本文概述您需要遵循的實作步驟，視您的 [!DNL People-Based Destinations]藍本而定。

## 概述 {#overview}

此設定會 [!DNL People-Based Destinations] 帶您檢視Audience manager的多個區段，並需要不同的設定和資料登入方法，這取決於您在Audience manager中已擁有的客戶資料類型，以及您想要執行的目標受眾類型。

>[!IMPORTANT]
> 在設定 [!DNL People-Based Destinations]之前，請務必仔細完整地閱讀本文。 閱讀本指南後，您應清楚瞭解將透過啟用的藍本 [!DNL People-Based Destinations]。

在使用之前，您需要先釐清6個實作方面 [!DNL People-Based Destinations]。 本文將協助您瞭解目前的設定，以便您能夠正確遵循藍本的實施步驟。

![pbd實施](assets/pbd-implementation.png)

## 1.定義您的使用案例 {#defining-your-use-case}

在開始實作 [!DNL People-Based Destinations]之前，您必須清楚定義您將使用此功能的使用案例。 您可以根 [!DNL People-Based Destinations] 據受眾活動，以兩種方式來定位受眾：

**A)根據您結合的線上和線下使用者活動鎖定受眾**。 在此案例中，您想要結合Audience manager的現有觀眾資料與內部系統的資料， [!DNL CRM] 並傳送產生的觀眾區隔 [!DNL People-Based Destinations]。 以下是說明此情形的範例：

Your company, an airline, has different customer tiers (Bronze, Silver, and Gold), and you want to provide each of the tiers with personalized offers via social platforms. 您使用Audience manager分析網站上的客戶活動。 不過，並非所有客戶都使用該航空公司的行動應用程式，其中有些客戶尚未登入該公司網站。 Your customer data is mostly limited to membership IDs and email addresses.

To target them across social media and similar people-based channels, you can bring your hashed email addresses into Audience Manager and combine them with your existing online activity traits, to build new audience segments. [](people-based-destinations-prerequisites.md)Next, you can use those segments to target your audience through .[!DNL People-Based Destinations]

**B) Audience targeting based exclusively on your offline user activity.** In this scenario, your  system contains your customer email addresses and other customer attributes, but customers have not interacted with your website at all, so you don't have any customer activity in Audience Manager. [!DNL CRM]Here's an example that illustrates this scenario:

Your company, a telecom services provider, keeps customer data like email addresses and purchased telecom plans in an internal . [!DNL CRM]You want to target existing customers in social platforms to offer them upgrade packages based on their existing subscriptions. To do this, you can ingest your hashed customer email addresses into Audience Manager, and create segments based on the existing customer subscriptions. Then, you can send these segments to  to target your customers with personalized offers.[!DNL People-Based Destinations]

## 2. Define the Type of Targeted Email Addresses {#define-target-email}

The second step in defining your implementation strategy is deciding what type of customer email addresses you want to target.

**A) Audience targeting based on your authenticated email addresses.** In this scenario, your users have multiple accounts associated with multiple email addresses, and you want to target them with personalized offers, based only on the email address that they authenticate on your website, in real time.

**B)根據您所有相關電子郵件地址鎖定受眾**。 在此案例中，您的使用者有多個帳戶與多個電子郵件地址相關聯，而且不論已驗證的活動為何，您都想在所有相關電子郵件地址中定位這些帳戶。

## 3.識別您擁有的客戶ID(CRM ID)類型 {#identify-customer-id}

在中定位 [!DNL People-Based Destinations] 受眾需要您傳 [送SHA256雜湊版本的客戶電子郵件地址](people-based-destinations-prerequisites.md) 。 視您現有的Audience manager設定而定，您可能會在下列兩種情況中發現自己：

**A)您的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))已是小寫、雜湊的電子郵件地址**。 在此案例中，您可以使用這些現有ID來定位您的對象 [!DNL People-Based Destinations]。

**B)您的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))不是小寫、雜湊的電子郵件地址**。 在此案例中，您現有的客戶ID無法傳送至 [!DNL People-Based Destinations]。 若要使 [!DNL People-Based Destinations]用，您必須在現有客戶ID和小寫、雜湊版本的客戶電子郵件地址之間執行ID同步。 您可以透過檔案 [型ID同步或使用宣告的ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) , [來執行此動作](../declared-ids.md)。

## 4.特徵資格 {#trait-qualification}

若要精確定位您的受 [!DNL People-Based Destinations]眾，您的使用者必須符合規則型或已登入特徵的資格，這取決於您要執行的受眾定位類型。

**A)即時符合客戶ID和裝置ID的規則型特徵**。 此選項適用於使用案例A(自 [1起)。 定義您的使用案例](people-based-destinations-workflow.md#defining-your-use-case)。 如果您的計畫是根據線上和離線活動來鎖定對象，則您很可能已經針對規則型特徵對 [對象進行了資格確認](../traits/trait-qualification-reference.md)。

**B)透過傳入資料檔案，針對客戶ID建立線上特徵**。 此選項適用於使用案例B的 [1。 定義您的使用案例](people-based-destinations-workflow.md#defining-your-use-case)。 當您根據純離線活動鎖定受眾時，需要透過傳入資料檔案確認客戶ID是否具有已登入 [的特徵](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。

## 5.建立或標示資料來源和板載雜湊電子郵件地址 {#create-label-data-sources}

視您在Audience manager中擁有的客戶ID類型而定(請參 [閱3。 識別您擁有的客戶ID(CRM ID)類型](people-based-destinations-workflow.md#identify-customer-id)，您會發現您身處下列其中一種情形：

**A)標示現有資料來源**。 此選項適用於Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))已是小寫雜湊電子郵件地址的案例。 在這種情況下，您需要將ID儲存在的資料來源標示為資 [!DNL PII] 料來源。 如需 [資料來源設定的詳細資訊](../datasources-list-and-settings.md) ，請參閱資料來源設定。 您需要做的是，確定未選中「無法與個人識別資訊綁定」選項。

**B)建立新的資料來源**。 This option applies to the scenario where your Audience Manager customer IDs (DPUUIDs) are not hashed email addresses. [](../../reference/ids-in-aam.md)In this case, you need to create a new cross-device data source and onboard your hashed email addresses against it. 您可以透過兩種方式進行此作業：

* Use file-based ID synchronization. See Name and Content Requirements for ID Synchronization Files for details on what ID synchronization files should look like. [](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)When using this method, you can target all of your hashed email addresses from your  database.[!DNL CRM]
* Use declared IDs to declare your hashed email addresses when passing in authenticated customer IDs. [](../declared-ids.md)When using this method, Audience Manager, on your behalf, only targets your hashed email addresses from users who have authenticated online. The email addresses targeted in people-based channels are only the ones in the declared ID event calls. Other email addresses associated with the customer ID are not activated in real-time.

## 6. Use a Profile Merge Rule for Segmentation {#use-profile-merge-rules}

Depending on your use case (see 1. [定義使用案例](people-based-destinations-workflow.md#defining-your-use-case))，有兩種方法可用於 [!DNL Profile Merge Rules] 分段。

**A)使用現有[!DNL Profile Merge Rules]**。 This option applies to the first use case (audience targeting based on combined online and offline user activity). 在此案例中，您在Audience manager中已有現有客戶活動，而且您已定義至少一個用於劃分的描述檔合併規則。 在這種情況下，您不需要建立任何新 [!DNL Profile Merge Rules]。

**B) Create a new,  Merge Rule.[!DNL All Cross-Device Profiles]**&#x200B;此選項適用於第二個使用案例（觀眾鎖定完全以離線使用者活動為基礎）。 在此案例中，您會將離線客戶資料從您的 [!DNL CRM] Audience manager中匯入，並想從該資料建立區段。 為此，引入 [!DNL People-Based Destinations] 新的第四個描述檔合併規則，稱為 **[!DNL All Cross-Device Profiles]**。 這是您劃分純離線資料時需要使用的規則。
