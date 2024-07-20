---
description: 活動使用情況報告可幫助您檢視和追蹤Audience Manager例項的活動使用情況，以便您可以將實際使用情況與合約承諾進行比較。
keywords: 活動，使用量，報告，承諾
seo-description: Activity Usage Reporting helps you view and track the activity usage for your Audience Manager instance, so you can compare your actual usage to your contractual commitment.
seo-title: Activity Usage Reporting
solution: Audience Manager
title: 活動使用情況報表
feature: Usage and Billing
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 5%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## 概述 {#overview}

[!UICONTROL Activity Usage Report] 可協助您檢視及追蹤 Audience Manager 例項的活動使用情況，讓您清楚瞭解活動使用情況與合約承諾的比較情形。

此外，您隨時都可以下載[!UICONTROL Activity Usage Report]，以保留記錄和自訂分析。

## 考量事項 {#considerations}

[!UICONTROL Activity Usage Report]可供具有[系統管理員許可權](edit-account-settings.md)的所有Audience Manager使用者使用。

>[!IMPORTANT]
>
>[!UICONTROL Activity Usage Report]會顯示Audience Manager執行個體的活動使用統計資料。 如需與您的活動使用方式相關的任何計費查詢，請聯絡您的Adobe代表。

## 使用個案 {#use-cases}

[!UICONTROL Activity Usage Report]有兩個主要使用案例：

* **根據您的活動使用量承諾追蹤實際執行個體活動使用量**：大多數客戶具有每個Audience Manager執行個體的每月估計活動承諾使用量，然後累積到所有執行個體的每年活動承諾使用量。 雖然此報告不是計費報告，但可提供關於您是否超過認可活動使用量的實用指引。
* **驗證實作變更**：如果您最近更新了實作，例如設定[!DNL Adobe Analytics]伺服器端轉送或變更[!DNL Adobe Target]伺服器呼叫設定，此報表可協助您檢查新的活動磁碟區是否與預期的活動磁碟區一致。

## 使用[!UICONTROL Activity Usage Report] {#using}

若要檢視[!UICONTROL Activity Usage Report]，請登入您的Audience Manager帳戶，然後前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Usage]**。

![aur-ui](assets/aur-ui.png)

接下來，使用&#x200B;**[!UICONTROL Reporting Interval]**&#x200B;篩選器來選取產生報告的時間間隔。 您可以選擇30、60、90天或自訂日期範圍。

報告載入後，您就能看到所選期間的[!UICONTROL Activities]劃分。

[!UICONTROL Activities]定義與Audience Manager的所有站上和離站互動的總計，分為下列類別：

* **[!UICONTROL Server Calls]**：從網站、伺服器、電子郵件、行動應用程式或其他系統傳送給Audience Manager的任何資料收集或擷取事件。
* **[!UICONTROL Pixel Calls]（先前稱為[!UICONTROL Impression Server Calls]）**：從廣告收集的資料（例如來自目標平台的曝光量）或向Audience Manager發出的電子郵件曝光呼叫。 這些需要在查詢字串中存在`d_event`引數。
* **[!UICONTROL On-Boarded Records]**：從您自己的客戶關係管理系統(CRM)或其他離線資料檔擷取的不重複記錄，例如客服中心記錄、裝置ID以及來自外部資料提供者的自訂資料摘要。
* **[!UICONTROL Log File Records]**：從目標平台擷取到Audience Manager之記錄檔的唯一記錄。

>[!NOTE]
>
>唯一記錄會定義Adobe代表Audience Manager客戶儲存之檔案中的每一筆資料記錄。

此外，您可以使用[!UICONTROL Activity Usage Trends]圖表型別，在兩個圖表型別之間切換。

![aur-ui-graphs](assets/aur-ui-graphs.png)

您也可以將游標暫留在時間軸中的特定日期上，以檢視該日期的詳細使用情形。

![aur-hover](assets/aur-hover.png)

## 正在匯出[!UICONTROL Activity Usage Reports] {#export}

如需您的Audience Manager活動使用層級的更佳概觀，您可以根據要包含的記錄型別匯出[!UICONTROL Activity Usage Report]。

![自動匯出](assets/aur-export.png)

**[!UICONTROL Onboarded Records Breakdown]**&#x200B;和&#x200B;**[!UICONTROL Onsite Server Calls Breakdown]**&#x200B;報告可提供這些活動可用來源資料的最精細分析。 歸因到這些劃分的磁碟區會以您的實施為基礎。

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

此報表包含依資料來源劃分的已上線記錄。

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

此報表包含來自三個來源的伺服器呼叫劃分： [!UICONTROL Analytics]、[!UICONTROL Target]及[!UICONTROL Other]。

* **[!UICONTROL Analytics]**：這些是從所有[!UICONTROL Adobe Analytics]執行個體傳遞到Audience Manager的可計費伺服器呼叫，包括伺服器端轉送。 次要伺服器呼叫或重複的伺服器呼叫（如來自多個報表套裝的伺服器端轉送）不徵收費用，因此這些呼叫不會包含在此劃分中。
* **[!UICONTROL Target]**：這些是從[!UICONTROL Adobe Target]到Audience Manager的伺服器端呼叫，用於擷取Audience Manager區段資料，做為伺服器對伺服器整合的一部分。
* **[!UICONTROL Other]**：包含來自任何其他網站或系統（合作夥伴網站、直接伺服器呼叫等）的呼叫、透過[!DNL SDK]、[!DNL DIL]、事件呼叫和[!DNL DCS]呼叫的行動瀏覽器/應用程式呼叫。 如果設定為Cookie整合（而非伺服器對伺服器），也會包含來自[!DNL Target]的呼叫。
