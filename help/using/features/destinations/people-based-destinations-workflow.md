---
description: 「以人為本的目標」提供多種實作策略，視客戶資料的結構而定。 本文概述了您在「以人為本的目標」上需要遵循的實作步驟，視您的藍本而定。
seo-description: '「以人為本的目標」提供多種實作策略，視客戶資料的結構而定。 本文概述了您在「以人為本的目標」上需要遵循的實作步驟，視您的藍本而定。  '
seo-title: 以人為本的目的地實作指引
solution: Audience Manager
title: 實施指南
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# 實施指南 {#implementation-guidance}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

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

您的公司是一家航空公司，有不同的客戶層級（銅、銀和金），您想要透過社交平台為每個層級提供個人化優惠。 您使用Audience manager分析網站上的客戶活動。 不過，並非所有客戶都使用該航空公司的行動應用程式，其中有些客戶尚未登入該公司網站。 您的客戶資料主要限於會籍ID和電子郵件地址。

若要跨社交媒體和類似的以人為本的通道鎖定目標受眾，您可以將雜湊的電子郵件地址匯入Audience [](people-based-destinations-prerequisites.md) Manager，並將它們與您現有的線上活動特徵結合，以建立新的受眾細分。 接下來，您可以使用這些區段來鎖定受眾 [!DNL People-Based Destinations]。

**B)受眾鎖定完全根據您的離線使用者活動**。 在此案例中，您的 [!DNL CRM] 系統包含您的客戶電子郵件地址和其他客戶屬性，但客戶根本沒有與您的網站互動，因此您在Audience manager中沒有任何客戶活動。 以下是說明此情形的範例：

您的公司是電信服務供應商，將客戶資料（例如電子郵件地址和購買的電信計畫）保存在內部 [!DNL CRM]。 您想要鎖定社交平台中的現有客戶，以根據現有訂閱提供升級套件。 若要這麼做，您可以將雜湊的客戶電子郵件地址內嵌至Audience Manager，並根據現有客戶訂閱建立細分。 然後，您可以傳送這些區段給 [!DNL People-Based Destinations] 客戶，以個人化優惠為目標。

## 2.定義目標電子郵件地址的類型 {#define-target-email}

定義實施策略的第二個步驟是決定您要鎖定的客戶電子郵件地址類型。

**A)根據已驗證的電子郵件地址鎖定受眾**。 在此案例中，您的使用者有多個帳戶與多個電子郵件地址相關聯，而您只想根據他們在您網站上即時驗證的電子郵件地址，以個人化優惠來定位他們。

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

**B)建立新的資料來源**。 此選項適用於Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))未雜湊電子郵件地址的情形。 在這種情況下，您需要建立新的跨裝置資料來源，並將雜湊的電子郵件地址加入其中。 您可以透過兩種方式進行此作業：

* 使用檔案式ID同步。 如需 [ID同步檔案的詳細資訊](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ，請參閱ID同步檔案的名稱和內容需求。 使用此方法時，您可以定位資料庫中所有雜湊的電子郵件地址 [!DNL CRM] 。
* 使用 [宣告的ID](../declared-ids.md) ，在傳入已驗證的客戶ID時，宣告您的雜湊電子郵件地址。 當使用此方法時，Audience manager僅會代表您針對已線上驗證之使用者的雜湊電子郵件地址。 以人員為基礎的管道中定位的電子郵件地址，僅是宣告的ID事件呼叫中的電子郵件地址。 與客戶ID關聯的其他電子郵件地址不會即時啟用。

## 6.使用描述檔合併規則進行分段 {#use-profile-merge-rules}

視您的使用案例而定(請參 [閱1。 定義使用案例](people-based-destinations-workflow.md#defining-your-use-case))，有兩種方法可用於 [!DNL Profile Merge Rules] 分段。

**A)使用現有[!DNL Profile Merge Rules]**。 這個選項適用於第一個使用案例（根據結合的線上和離線使用者活動鎖定對象）。 在此案例中，您在Audience manager中已有現有客戶活動，而且您已定義至少一個用於劃分的描述檔合併規則。 在這種情況下，您不需要建立任何新 [!DNL Profile Merge Rules]。

**B)建立新的合[!DNL All Cross-Device Profiles]並規則**。 此選項適用於第二個使用案例（觀眾鎖定完全以離線使用者活動為基礎）。 在此案例中，您會將離線客戶資料從您的 [!DNL CRM] Audience manager中匯入，並想從該資料建立區段。 為此，引入 [!DNL People-Based Destinations] 新的第四個描述檔合併規則，稱為 **[!DNL All Cross-Device Profiles]**。 這是您劃分純離線資料時需要使用的規則。
