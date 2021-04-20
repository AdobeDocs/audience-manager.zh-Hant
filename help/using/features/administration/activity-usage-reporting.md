---
description: 「活動使用情況報告」可協助您檢視及追蹤Audience Manager實例的活動使用情況，以便您比較實際使用情形與合約承諾。
keywords: 活動，使用，報告，承諾
seo-description: 「活動使用情況報告」可協助您檢視及追蹤Audience Manager實例的活動使用情況，以便您比較實際使用情形與合約承諾。
seo-title: 活動使用情況報表
solution: Audience Manager
title: 活動使用情況報表
feature: Usage and Billing
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 6%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## 概述 {#overview}

[!UICONTROL Activity Usage Report] 可協助您檢視及追蹤 Audience Manager 例項的活動使用情況，讓您清楚瞭解活動使用情況與合約承諾的比較情形。

此外，您還可以視需要下載[!UICONTROL Activity Usage Report]，以便保留記錄和自訂分析。

## 考量事項 {#considerations}

[!UICONTROL Activity Usage Report]適用於具有[管理員權限](edit-account-settings.md)的所有Audience Manager用戶。

>[!IMPORTANT]
>
>[!UICONTROL Activity Usage Report]顯示Audience Manager實例的活動使用統計資訊。 如需任何與您活動使用情況相關的帳單查詢，請聯絡您的Adobe代表。

## 使用個案 {#use-cases}

[!UICONTROL Activity Usage Report]有兩個主要使用案例：

* **根據您的活動使用承諾追蹤實際例項活動使用情況**:大多數客戶每個Audience Manager例項都有每月預估的活動承諾，然後累積到所有例項的年度活動承諾中。雖然此報表不是帳單報表，但可針對您是否超過已承諾活動使用量提供實用的指引。
* **實作變更的驗證**:如果您最近更新了實作，例如設定 [!DNL Adobe Analytics]  [!DNL Adobe Target] 伺服器端轉送或變更伺服器呼叫設定，此報告可協助您檢查新活動卷是否符合您預期的活動卷。

## 在連結中使用 [!UICONTROL Activity Usage Report] {#using}

若要查看[!UICONTROL Activity Usage Report]，請登入您的Audience Manager帳戶，然後前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Usage]**。

![aur-ui](assets/aur-ui.png)

接著，使用&#x200B;**[!UICONTROL Reporting Interval]**&#x200B;篩選器來選擇產生報表的時間間隔。 您可以選擇30、60、90天或自訂日期範圍。

報表載入後，您可以看到所選時段的[!UICONTROL Activities]劃分。

[!UICONTROL Activities] 定義與Audience Manager的所有站內和站外互動的總計，並分為下列類別：

* **[!UICONTROL Server Calls]**:從網站、伺服器、電子郵件、行動應用程式或其他系統傳送至Audience Manager的任何資料收集或擷取事件。
* **[!UICONTROL Pixel Calls](先前稱為 [!UICONTROL Impression Server Calls])**:從廣告收集的資料（例如來自定位平台的曝光量）或電子郵件曝光呼叫中對Audience Manager所做的呼叫。這些要求查詢字串中必須有`d_event`參數。
* **[!UICONTROL On-Boarded Records]**:從您自己的客戶關係管理系統(CRM)或其他離線資料檔案（例如話務中心記錄、裝置ID和來自外部資料提供者的自訂資料饋送）所擷取的獨特記錄。
* **[!UICONTROL Log File Records]**:來自記錄檔的獨特記錄，從定位平台傳入Audience Manager。

>[!NOTE]
>
>唯一記錄定義了代表Audience Manager客戶的Adobe儲存的檔案中的每個單獨資料記錄。

此外，您還可以使用[!UICONTROL Activity Usage Trends]圖形類型在兩種圖形類型之間切換。

![aur-ui-graphs](assets/aur-ui-graphs.png)

您也可以將游標停留在時間軸中的特定日期上，以檢視該日期的詳細使用情形。

![aur-hover](assets/aur-hover.png)

## 導出[!UICONTROL Activity Usage Reports] {#export}

如需Audience Manager活動使用級別的更佳概覽，您可以根據要包含的記錄類型導出[!UICONTROL Activity Usage Report]。

![aur-export](assets/aur-export.png)

**[!UICONTROL Onboarded Records Breakdown]**&#x200B;和&#x200B;**[!UICONTROL Onsite Server Calls Breakdown]**&#x200B;報表可提供這些活動可用來源資料的最詳細分析。 這些劃分所屬的量會根據您的實施而定。

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

此報表包含依資料來源劃分的已登入記錄。

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

此報告包含來自三個來源的伺服器呼叫劃分：[!UICONTROL Analytics]、[!UICONTROL Target]和[!UICONTROL Other]。

* **[!UICONTROL Analytics]**:這些是從所有實例傳遞給Audience Manager的可計 [!UICONTROL Adobe Analytics] 費伺服器調用，包括伺服器端轉發。次要伺服器呼叫或重複伺服器呼叫（如同來自多個報表套裝的伺服器端轉送）不是計費活動，因此這些呼叫不包含在此劃分中。
* **[!UICONTROL Target]**:這些是伺服器端對Audience Manager [!UICONTROL Adobe Target] 的呼叫，以擷取Audience Manager區段資料，做為伺服器對伺服器整合的一部分。
* **[!UICONTROL Other]**:包括來自任何其他網站或系統（合作夥伴網站、直接伺服器呼叫等）、行動瀏覽器／應用程式呼叫 [!DNL SDK]、 [!DNL DIL]事件呼叫和呼 [!DNL DCS] 叫。如果設定為Cookie整合（而非伺服器對伺服器），也包含來自[!DNL Target]的呼叫。
