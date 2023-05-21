---
description: 活動使用情況報告可幫助您查看和跟蹤Audience Manager實例的活動使用情況，以便您可以將實際使用情況與合同承諾進行比較。
keywords: 活動，用法，報告，承諾
seo-description: Activity Usage Reporting helps you view and track the activity usage for your Audience Manager instance, so you can compare your actual usage to your contractual commitment.
seo-title: Activity Usage Reporting
solution: Audience Manager
title: 活動使用情況報表
feature: Usage and Billing
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 5%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## 概述 {#overview}

[!UICONTROL Activity Usage Report] 可協助您檢視及追蹤 Audience Manager 例項的活動使用情況，讓您清楚瞭解活動使用情況與合約承諾的比較情形。

此外，您還可以下載 [!UICONTROL Activity Usage Report] 需要時，進行記錄保留和自定義分析。

## 考量事項 {#considerations}

的 [!UICONTROL Activity Usage Report] 可供所有Audience Manager使用 [管理員權限](edit-account-settings.md)。

>[!IMPORTANT]
>
>的 [!UICONTROL Activity Usage Report] 顯示Audience Manager實例的活動使用情況統計資訊。 有關活動使用情況的任何開單查詢，請聯繫您的Adobe代表。

## 使用個案 {#use-cases}

有兩個主要用例 [!UICONTROL Activity Usage Report]:

* **根據活動使用情況承諾跟蹤實際實例活動使用情況**:大多數客戶每個Audience Manager實例都有每月估計的活動承諾，然後將其累計到所有實例的每年活動承諾中。 雖然此報告不是開單報告，但它可以提供有關您是否超過已承諾活動使用情況的有用指導。
* **驗證實施更改**:如果您最近更新了實施，例如設定 [!DNL Adobe Analytics] 伺服器端轉發，或更改 [!DNL Adobe Target] 伺服器調用設定，此報告可幫助您檢查新活動卷是否與預期活動卷一致。

## 在連結中使用 [!UICONTROL Activity Usage Report] {#using}

查看 [!UICONTROL Activity Usage Report]，登錄到您的Audience Manager帳戶，然後轉到 **[!UICONTROL Administration]** > **[!UICONTROL Usage]**。

![奧爾伊](assets/aur-ui.png)

接下來，使用 **[!UICONTROL Reporting Interval]** 篩選器，以選擇生成報告的時間間隔。 您可以選擇30天、60天、90天或自定義日期範圍。

一旦載入報表，您就可以看到 [!UICONTROL Activities] 的下界。

[!UICONTROL Activities] 定義與Audience Manager的所有現場和異地交互的總計，分為以下類別：

* **[!UICONTROL Server Calls]**:從網站、伺服器、電子郵件、移動應用程式或其他系統發送到Audience Manager的任何資料收集或檢索事件。
* **[!UICONTROL Pixel Calls](前稱 [!UICONTROL Impression Server Calls])**:從廣告（例如目標平台的印象卷）或向Audience Manager發送的電子郵件印象呼叫中收集的資料。 這要求 `d_event` 查詢字串中的參數。
* **[!UICONTROL On-Boarded Records]**:從您自己的客戶關係管理系統(CRM)或其他離線資料檔案（如呼叫中心記錄、設備ID和來自外部資料提供商的自定義資料饋送）中攝取的唯一記錄。
* **[!UICONTROL Log File Records]**:從目標平台接收到Audience Manager的日誌檔案中的唯一記錄。

>[!NOTE]
>
>唯一記錄定義了代表Audience Manager客戶Adobe儲存的檔案中資料的每個單獨記錄。

此外，您還可以 [!UICONTROL Activity Usage Trends] 圖形類型以在兩種類型的圖形之間切換。

![aur-ui圖](assets/aur-ui-graphs.png)

您還可以將游標懸停在時間軸中的特定日期上，以查看該日期的詳細用法。

![阿爾沃](assets/aur-hover.png)

## 導出 [!UICONTROL Activity Usage Reports] {#export}

要更好地概述Audience Manager活動使用級別，您可以導出 [!UICONTROL Activity Usage Report] 基於要包括的記錄類型。

![aur-export](assets/aur-export.png)

的 **[!UICONTROL Onboarded Records Breakdown]** 和 **[!UICONTROL Onsite Server Calls Breakdown]** 報告提供了這些活動可用的源資料的最精確的洞察。 由這些故障造成的卷基於您的實施。

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

此報表包含按資料源細分的已登錄記錄。

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

此報表包含來自以下三個來源的伺服器調用的細分： [!UICONTROL Analytics]。 [!UICONTROL Target], [!UICONTROL Other]。

* **[!UICONTROL Analytics]**:這些是從所有 [!UICONTROL Adobe Analytics] 實例到Audience Manager，包括伺服器端轉發。 從屬伺服器呼叫或重複伺服器呼叫（如從多個報告套件進行伺服器端轉發）不是可計費活動，因此這些活動不包括在此細分中。
* **[!UICONTROL Target]**:這些是來自 [!UICONTROL Adobe Target] 要Audience Manager，請檢索Audience Manager段資料，將其作為伺服器到伺服器整合的一部分。
* **[!UICONTROL Other]**:包括來自任何其他網站或系統（合作夥伴站點、直接伺服器呼叫等）的呼叫、通過 [!DNL SDK]。 [!DNL DIL]、事件調用和 [!DNL DCS] 呼叫。 還包括來自 [!DNL Target] 設定為cookie整合（而不是伺服器到伺服器）。
