---
description: 「活動使用量報表」可協助您檢視及追蹤Audience Manager例項的活動使用量，以便您比較實際使用量與合約承諾使用量。
keywords: 活動，使用，報告，承諾
seo-description: 「活動使用量報表」可協助您檢視及追蹤Audience Manager例項的活動使用量，以便您比較實際使用量與合約承諾使用量。
seo-title: 活動使用情況報表
solution: Audience Manager
title: 活動使用情況報表
feature: 使用與帳單
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 6%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## 概述 {#overview}

[!UICONTROL Activity Usage Report] 可協助您檢視及追蹤 Audience Manager 例項的活動使用情況，讓您清楚瞭解活動使用情況與合約承諾的比較情形。

此外，您可以視需要下載[!UICONTROL Activity Usage Report]以保留記錄和自訂分析。

## 考量事項 {#considerations}

[!UICONTROL Activity Usage Report]適用於具有[管理員權限](edit-account-settings.md)的所有Audience Manager用戶。

>[!IMPORTANT]
>
>[!UICONTROL Activity Usage Report]會顯示Audience Manager例項的活動使用情況統計資料。 如需與活動使用情況相關的任何帳單查詢，請洽詢您的Adobe代表。

## 使用個案 {#use-cases}

[!UICONTROL Activity Usage Report]有兩個主要使用案例：

* **根據活動使用量承諾量追蹤實際例項活動使用量**:大部分的Audience Manager具有每個客戶例項的每月預估活動承諾量，然後累計至所有例項的每年活動承諾量。雖然此報表不是帳單報表，但對於您是否超過已承諾的活動使用量，它可提供實用的指引。
* **實作變更的驗證**:如果您最近更新了實作，例如設 [!DNL Adobe Analytics] 定伺服器端轉送或變更 [!DNL Adobe Target] 伺服器呼叫設定，此報告可協助您檢查新活動卷是否符合您預期的活動量。

## 在連結中使用 [!UICONTROL Activity Usage Report] {#using}

若要查看[!UICONTROL Activity Usage Report]，請登入您的Audience Manager帳戶，然後前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Usage]**。

![阿爾烏伊](assets/aur-ui.png)

接下來，使用&#x200B;**[!UICONTROL Reporting Interval]**&#x200B;篩選器選擇要為其生成報告的時間間隔。 您可以選擇30、60、90天或自訂日期範圍。

報表載入後，您就會看到所選期間的[!UICONTROL Activities]劃分。

[!UICONTROL Activities] 定義與Audience Manager的所有站上和離站互動的匯總總計，並分為下列類別：

* **[!UICONTROL Server Calls]**:從網站、伺服器、電子郵件、行動應用程式或其他系統傳送至Audience Manager的任何資料收集或擷取事件。
* **[!UICONTROL Pixel Calls](原稱 [!UICONTROL Impression Server Calls]為**:從廣告收集的資料（例如來自目標平台的曝光量）或對Audience Manager進行的電子郵件曝光呼叫。這些要求查詢字串中須有`d_event`參數。
* **[!UICONTROL On-Boarded Records]**:從您自己的客戶關係管理系統(CRM)或其他離線資料檔案（例如客服中心記錄、裝置ID以及來自外部資料提供者的自訂資料摘要）擷取的不重複記錄。
* **[!UICONTROL Log File Records]**:來自從目標平台擷取至Audience Manager之記錄檔的唯一記錄。

>[!NOTE]
>
>唯一記錄會定義Adobe代表Audience Manager客戶儲存的檔案中的每個個別資料記錄。

此外，您可以使用[!UICONTROL Activity Usage Trends]圖表類型在兩種類型的圖表之間切換。

![aur-ui-graphs](assets/aur-ui-graphs.png)

您也可以將游標暫留在時間軸中的特定日期上，以查看該日期的詳細用法。

![奧爾韋](assets/aur-hover.png)

## 導出[!UICONTROL Activity Usage Reports] {#export}

如需Audience Manager活動使用水準的更佳概覽，您可以根據要包含的記錄類型匯出[!UICONTROL Activity Usage Report]。

![aur-export](assets/aur-export.png)

**[!UICONTROL Onboarded Records Breakdown]**&#x200B;和&#x200B;**[!UICONTROL Onsite Server Calls Breakdown]**&#x200B;報表可提供這些活動可用之來源資料的最詳細分析。 歸因於這些劃分的量會根據您的實施而定。

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

此報表包含依資料來源劃分的已上線記錄。

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

此報表包含來自三個來源的伺服器呼叫劃分：[!UICONTROL Analytics]、[!UICONTROL Target]和[!UICONTROL Other]。

* **[!UICONTROL Analytics]**:這些是從所有執行個體傳遞至Audience Manager [!UICONTROL Adobe Analytics] 的計費伺服器呼叫，包括伺服器端轉送。次要伺服器呼叫或重複的伺服器呼叫（如同從多個報表套裝進行伺服器端轉送的情況）不是可計費活動，因此這些呼叫不包含在劃分中。
* **[!UICONTROL Target]**:這些是從到Audience Manager的伺 [!UICONTROL Adobe Target] 服器端呼叫，以在伺服器對伺服器整合中擷取Audience Manager區段資料。
* **[!UICONTROL Other]**:包括來自任何其他網站或系統（合作夥伴網站、直接伺服器呼叫等）的呼叫、透過、、事件呼叫和呼叫來自行動瀏覽 [!DNL SDK]器/ [!DNL DIL]應用程式的 [!DNL DCS] 呼叫。如果設定為Cookie整合（而非伺服器對伺服器），也會包含來自[!DNL Target]的呼叫。
