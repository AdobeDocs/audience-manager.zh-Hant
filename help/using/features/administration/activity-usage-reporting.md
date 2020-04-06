---
description: 「活動使用狀況報告」可協助您檢視及追蹤Audience Manager例項的活動使用狀況，以便您比較實際使用狀況與合約承諾。
keywords: activity, usage, reporting, commitment
seo-description: 「活動使用狀況報告」可協助您檢視及追蹤Audience Manager例項的活動使用狀況，以便您比較實際使用狀況與合約承諾。
seo-title: 活動使用情況報告
solution: Audience Manager
title: 活動使用情況報告
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# 活動使用情況報告

## 概述 {#overview}

此 [!UICONTROL Activity Usage Report] 功能可協助您檢視及追蹤Audience Manager例項的活動使用情形，讓您清楚瞭解活動使用情形與合約承諾的比較。

此外，您可視需要下 [!UICONTROL Activity Usage Report] 載記錄保留和自訂分析。

## 考量事項 {#considerations}

所有 [!UICONTROL Activity Usage Report] 具有管理員權限的Audience Manager使 [用者皆可使用](edit-account-settings.md)。

>[!IMPORTANT]
>
>此處 [!UICONTROL Activity Usage Report] 顯示您Audience Manager例項的活動使用統計資料。 如需任何與您活動使用有關的帳單查詢，請聯絡您的Adobe代表。

## 使用個案 {#use-cases}

以下是兩個主要的使用案例 [!UICONTROL Activity Usage Report]:

* **根據您的活動使用承諾追蹤實際例項活動使用情況**:大部分客戶每個Audience Manager例項都有每月預估的活動承諾，然後累積到所有例項的年度活動承諾中。 雖然此報表不是帳單報表，但可針對您是否超過已承諾活動使用量提供實用的指引。
* **實作變更的驗證**:如果您最近更新實作，例如設定Analytics伺服器端轉送或變更Target伺服器呼叫設定，此報告可協助您檢查新活動卷是否符合您預期的活動卷。

## 使用活動使用情況報告 {#using}

若要查 [!UICONTROL Activity Usage Report]看，請登入您的Audience Manager帳戶，然後前往 **[!UICONTROL Administration]** > **[!UICONTROL Usage]**。

![aur-ui](assets/aur-ui.png)

接著，使用 **[!UICONTROL Reporting Interval]** 篩選器來選擇產生報表的時間間隔。 您可以選擇30、60、90天或自訂日期範圍。

報表載入後，您就可以看到所選時段 [!UICONTROL Activities] 的劃分資訊。

[!UICONTROL Activities] 定義與Audience Manager的所有Onsite和Offsite互動的總計，並分為下列類別：

* **[!UICONTROL Server Calls]**:從網站、伺服器、電子郵件、行動應用程式或其他系統傳送至Audience Manager的任何資料收集或擷取事件。
* **[!UICONTROL Pixel Calls](先前稱為[!UICONTROL Impression Server Calls])**:從廣告收集的資料（例如來自定位平台的曝光量）或電子郵件曝光呼叫Audience Manager。 這需要查詢字串中`d_event`有參數。
* **[!UICONTROL On-Boarded Records]**:從您自己的客戶關係管理系統(CRM)或其他離線資料檔案（例如話務中心記錄、裝置ID和來自外部資料提供者的自訂資料饋送）所擷取的獨特記錄。
* **[!UICONTROL Log File Records]**:來自記錄檔的獨特記錄，從定位平台傳入Audience Manager。

>[!NOTE]
>
>唯一記錄會代表Audience Manager客戶定義Adobe儲存之檔案中每個個別資料記錄。

此外，您也可以使用 [!UICONTROL Activity Usage Trends] 圖形類型在兩種圖形類型之間切換。

![aur-ui-graphs](assets/aur-ui-graphs.png)

您也可以將游標停留在時間軸中的特定日期上，以檢視該日期的詳細使用情形。

![aur-hover](assets/aur-hover.png)

## 匯出活動使用狀況報表 {#export}

如需Audience Manager活動使用層級的更佳概覽，您可以根 [!UICONTROL Activity Usage Report] 據您要包含的記錄類型匯出。

![aur-export](assets/aur-export.png)

此和 **[!UICONTROL Onboarded Records Breakdown]** 報 **[!UICONTROL Onsite Server Calls Breakdown]** 表可提供這些活動可用來源資料的最詳細分析。 這些劃分所屬的量會根據您的實施而定。

### 已登入記錄劃分 {#onboarded-breakdown}

此報表包含依資料來源劃分的已登入記錄。

### Onsite伺服器呼叫劃分 {#onsite-breakdown}

此報告包含來自三個來源的伺服器呼叫劃分： [!UICONTROL Analytics]、 [!UICONTROL Target]和 [!UICONTROL Other]。

* **[!UICONTROL Analytics]**:這些是從所有Adobe Analytics例項傳遞至Audience Manager的計費伺服器呼叫，包括伺服器端轉送。 次要伺服器呼叫或重複伺服器呼叫（如同來自多個報表套裝的伺服器端轉送）不是計費活動，因此這些呼叫不包含在此劃分中。
* **[!UICONTROL Target]**:這些是從Adobe Target到Audience Manager的伺服器端呼叫，以擷取Audience Manager區段資料，做為伺服器對伺服器整合的一部分。
* **[!UICONTROL Other]**:包括來自任何其他網站或系統（合作夥伴網站、直接伺服器呼叫等）、行動瀏覽器／應用程式呼叫 [!DNL SDK]、 [!DNL DIL]事件呼叫和呼叫的呼 [!DNL DCS] 叫。 也包含來自 [!DNL Target] 的呼叫（若設為Cookie整合），而非伺服器對伺服器的呼叫。
