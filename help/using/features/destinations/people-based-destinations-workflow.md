---
description: 基於人員的目標根據客戶資料的結構提供多種實施策略。 本文概述了根據您的方案，在「基於人員的目標」中需要遵循的實施步驟。
seo-description: People-Based Destinations offers multiple implementation strategies, depending on how your customer data is structured. This article provides an overview of the implementation steps that you need to follow for People-Based Destinations, depending on your scenario.
seo-title: People-Based Destinations Implementation Guidance
solution: Audience Manager
title: 實作指導
feature: People-based Destinations
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 3%

---

# 實作指導 {#implementation-guidance}

>[!IMPORTANT]
>本文包含旨在指導您完成此功能的設定和使用的產品文檔。 這裡沒有法律建議。 請咨詢您自己的法律顧問以獲得法律指導。

[!DNL People-Based Destinations] 根據客戶資料的結構提供多種實施策略。 本文概述了您需要執行的實施步驟 [!DNL People-Based Destinations]，具體取決於您的方案。

## 概述 {#overview}

配置 [!DNL People-Based Destinations] 帶您瞭解多個Audience Manager部分，並需要不同的設定和資料載入方法，具體取決於您已經在Audience Manager中擁有的客戶資料類型，以及您想要執行的目標受眾類型。

>[!IMPORTANT]
> 配置前 [!DNL People-Based Destinations]請務必仔細、完整地閱讀這篇文章。 閱讀本指南後，您應清楚地瞭解將通過以下方式啟用的方案 [!DNL People-Based Destinations]。

在使用之前，您需要先澄清六個實施方面 [!DNL People-Based Destinations]。 本文將幫助您瞭解當前的配置是什麼，以便您能夠正確執行方案的實施步驟。

![pbd實施](assets/pbd-implementation.png)

## 1。定義使用案例 {#defining-your-use-case}

開始實施之前 [!DNL People-Based Destinations]，需要明確定義要為此功能使用的使用案例。 您可以使用 [!DNL People-Based Destinations] 根據觀眾活動，以兩種方式來瞄準觀眾：

**A)基於線上和離線用戶活動組合的受眾目標**。 在此方案中，您希望將來自Audience Manager的現有受眾資料與來自內部的資料相結合 [!DNL CRM] 系統，並將生成的受眾段發送到 [!DNL People-Based Destinations]。 下面是一個示例，說明了此方案：

您的公司（一家航空公司）擁有不同的客戶層（銅牌、銀牌和金牌），您希望通過社交平台為每個層提供個性化的服務。 您可以使用Audience Manager來分析網站上的客戶活動。 然而，並非所有客戶都使用該航空公司的移動應用，其中一些客戶還沒有登錄該公司的網站。 您的客戶資料主要限於成員身份證和電子郵件地址。

要通過社交媒體和類似的以人為本的渠道來瞄準他們，你可以 [散列的電子郵件地址](people-based-destinations-prerequisites.md) 將它們與您現有的線上活動特徵結合起來，構建新的受眾群。 接下來，您可以使用這些段來針對您的受眾 [!DNL People-Based Destinations]。

**B)僅基於離線用戶活動的受眾目標**。 在此情況下， [!DNL CRM] 系統包含您的客戶電子郵件地址和其他客戶屬性，但客戶根本沒有與您的網站進行交互，因此您沒有在Audience Manager中進行任何客戶活動。 下面是一個示例，說明了此方案：

您的公司是電信服務提供商，將客戶資料（如電子郵件地址和購買的電信計畫）保存在內部 [!DNL CRM]。 您希望針對社交平台中的現有客戶，根據現有訂閱提供升級包。 為此，您可以將散列的客戶電子郵件地址錄入Audience Manager，並根據現有客戶訂閱建立段。 然後，您可以將這些段發送到 [!DNL People-Based Destinations] 以個性化服務為目標。

## 2.定義目標電子郵件地址的類型 {#define-target-email}

定義實施策略的第二步是確定您要針對的客戶電子郵件地址類型。

**A)基於已驗證電子郵件地址的受眾目標**。 在此方案中，您的用戶具有多個與多個電子郵件地址關聯的帳戶，並且您希望根據他們在您的網站上進行身份驗證的電子郵件地址即時地以個性化優惠作為目標。

**B)基於所有關聯電子郵件地址的受眾目標**。 在此方案中，您的用戶具有多個與多個電子郵件地址關聯的帳戶，並且您希望將這些帳戶作為所有關聯電子郵件地址的目標，而不考慮經過身份驗證的活動。

## 3.確定您擁有的客戶ID(CRM ID)的類型 {#identify-customer-id}

針對 [!DNL People-Based Destinations] 要求您發送 [SHA256散列](people-based-destinations-prerequisites.md) 客戶電子郵件地址的版本。 根據您現有的Audience Manager配置，您可能會發現以下兩種情況之一：

**A)您的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))已經是小寫，已散列的電子郵件地址**。 在此方案中，您可以使用這些現有ID將目標對象 [!DNL People-Based Destinations]。

**B)您的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))不是小寫，散列的電子郵件地址**。 在此方案中，無法將您的現有客戶ID發送到 [!DNL People-Based Destinations]。 要使用 [!DNL People-Based Destinations]，您需要在現有客戶ID和小寫、散列的客戶電子郵件地址版本之間執行ID同步。 你要麼通過 [基於檔案的ID同步](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 或 [聲明的ID](../declared-ids.md)。

## 4.特質鑑定 {#trait-qualification}

準確地瞄準您的受眾 [!DNL People-Based Destinations]，您的用戶需要根據您要執行的受眾目標類型，符合基於規則或已登錄的特徵。

**A)即時確認客戶ID和設備ID以瞭解基於規則的特性**。 此選項適用於使用案例A自 [1。 定義使用案例](people-based-destinations-workflow.md#defining-your-use-case)。 如果您的計畫是基於線上和離線活動來針對受眾，則您很可能已經為受眾提供了資格 [基於規則的特徵](../traits/trait-and-segment-qualification-reference.md)。

**B)通過入站資料檔案針對客戶ID的板載特徵**。 此選項適用於使用案例B自 [1。 定義使用案例](people-based-destinations-workflow.md#defining-your-use-case)。 當基於純離線活動針對您的受眾時，您需要通過以下方式為客戶ID提供已登錄的特徵 [入站資料檔案](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。

## 5.建立或標籤資料源和板載散列電子郵件地址 {#create-label-data-sources}

根據您在Audience Manager中擁有的客戶ID的類型(請參閱 [3. 確定您擁有的客戶ID(CRM ID)的類型](people-based-destinations-workflow.md#identify-customer-id)，您將發現自己處於以下情形之一：

**A)標籤現有資料源**。 此選項適用於Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))已經是小寫的散列電子郵件地址。 在這種情況下，您需要將ID儲存在的資料源標籤為 [!DNL PII] 資料源。 請參閱 [資料源設定](../datasources-list-and-settings.md) 的子菜單。 您需要做的是確保未選中「無法與個人身份資訊關聯」選項。

**B)建立新資料源**。 此選項適用於Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))沒有散列電子郵件地址。 在這種情況下，您需要建立一個新的跨設備資料源，並將散列的電子郵件地址與之相對應。 可以通過兩種方式實現：

* 使用檔案式 ID 同步。如需 ID 同步檔案的詳細資訊，請參閱 [ID 同步檔案的名稱和內容要求](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)。使用此方法時，您可以針對您的 [!DNL CRM] 資料庫。
* 使用 [聲明的ID](../declared-ids.md) 在傳遞經過驗證的客戶ID時聲明您的散列電子郵件地址。 使用此方法時，Audience Manager僅以您的名義針對已聯機驗證的用戶的散列電子郵件地址。 基於人員的渠道中目標的電子郵件地址僅是聲明的ID事件調用中的電子郵件地址。 與客戶 ID 相關聯的其他電子郵件地址不會即時啟用。

## 6。使用配置檔案合併規則進行分段 {#use-profile-merge-rules}

根據您的使用案例(請參閱 [1。 定義使用案例](people-based-destinations-workflow.md#defining-your-use-case))，有兩種使用方法 [!DNL Profile Merge Rules] 分割。

**A)使用現有[!DNL Profile Merge Rules]**。 此選項適用於第一個使用案例（基於聯機和離線用戶活動組合的受眾目標）。 在此方案中，您有現有的客戶活動正在Audience Manager中，並且您已經至少定義了一個已用於分段的「配置檔案合併規則」。 在這種情況下，您不需要建立新 [!DNL Profile Merge Rules]。

**B)建立 [!DNL All Cross-Device Profiles] 合併規則**。 此選項適用於第二個使用案例（完全基於離線用戶活動的受眾目標）。 在此方案中，您將從您的 [!DNL CRM] Audience Manager，並希望從該資料建立段。 要做到這一點， [!DNL People-Based Destinations] 引入新的、第四個配置檔案合併規則，稱為 **[!DNL All Cross-Device Profiles]**。 這是分割純離線資料時需要使用的規則。
