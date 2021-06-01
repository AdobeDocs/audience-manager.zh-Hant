---
description: 一般報表會傳回特徵、區段和目的地的效能資料。
seo-description: Audience Manager中的一般報表會傳回特徵、區段和目的地的效能資料。
seo-title: 一般報表Audience Manager
solution: Audience Manager
title: 一般報表
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: 一般與趨勢報表
exl-id: dc16a821-b776-4a04-af60-4b8c914253dd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 1%

---

# 一般報表{#general-reports}

[!UICONTROL General]報表會傳回特徵、區段和目的地的效能資料。

## 概述 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] 使 [!UICONTROL Role Based Access Control] 用([!UICONTROL RBAC])將使用者群組權限延伸至 [!UICONTROL General] 報表。使用者在報表中只能看到他們有權檢視的特徵和區段。 [!UICONTROL RBAC] 功能可讓您控制內部團隊可檢視的報表資料。例如，管理不同廣告商帳戶的代理可設定使用者群組權限，讓管理廣告商A帳戶的團隊看不到廣告商B的報表資料。

執行[!UICONTROL General]報表，以滿足以下需要：

* 依特徵、區段或目的地檢閱效能。
* 以1、7、14、30、60和90天間隔追蹤曝光數（總計和不重複）。
* 檢閱總計和不重複載入計數。
* 比較特徵和區段效能。
* 識別強或弱的效能特徵和區段、分析需求，或將負載/引發資料與第三方報表進行比較。
* 匯出資料（.csv格式）以供進一步分析和共用。

下圖提供[!UICONTROL General]報表中關鍵元素的概觀。

![](assets/general_reports.png)

1. 設定以下選項: 

   * **報表類型：** 選取所需的報表類型（特徵、區段或目的地）。

   * **日期至：** 指定報表的日期範圍。

2. 依名稱或ID搜尋特徵、區段或目的地。
3. 從資料夾清單中，將您要報告的特徵、區段或目的地拖放至右側的[!UICONTROL Selections]面板。
4. 產生報表以在可匯出的表格中顯示。

## 運行一般報告{#run-general-report}

本節介紹如何運行[!UICONTROL General]報告，以及如何設定時間和其他效能選項。

<!-- 

t_run_general_report.xml

 -->

1. 在&#x200B;**[!UICONTROL Analytics]**&#x200B;控制面板中，按一下&#x200B;**[!UICONTROL General Reports]**。
1. 從&#x200B;**[!UICONTROL Report Type]**&#x200B;下拉式清單中，選取所需的類型：特徵、區段或目的地。
1. ** 條件按一下日期方塊以顯示日曆，然後如果您想要指定今天以外的日期，請選取報表的結束日期。
1. 依名稱或ID搜尋特徵、區段或目的地。
1. 從資料夾清單中，將您要報告的特徵、區段或目的地拖放至右側的[!UICONTROL Selections]面板。
1. 按一下 **[!UICONTROL Run Report]**.

   結果顯示在可導出的表中。 按一下欄標題，以遞增或遞減順序排序結果。
1. 選取報表頂端所需的選項按鈕，以依效能（[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]或[!UICONTROL Total Trait Population]）或依時間（1、7、14、30、60或90天範圍）篩選資料。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 只會計 [!UICONTROL Rule-based Traits] 算。

1. ** 選用按一 **[!UICONTROL Export to CSV]**&#x200B;下。這會匯出所有日期範圍的[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]和[!UICONTROL Total Trait Population]。

## 說明的一般報告結果{#general-reports-explained}

[!UICONTROL General Reports]中的數字直接從我們的[!UICONTROL User Profile Store]中產生。 結果會反映產生這些報表數字時後端包含[!DNL Audience Manager]的使用者人數。

* 這些數字不包含流量過多的訪客ID。 系統會在到達後端系統前先篩選來自機器人的流量。 此外，在後端執行的每週清除工作期間，也會捨棄某些機器人流量。
* 如果您透過入站處理將[!DNL Audience Manager] UUID作為輸入資料，且這些ID包含在系統中已不再作用的使用者，則這些非作用中的[!DNL Audience Manager] UUID永遠不會到達[!UICONTROL User Profile Store]，也不會回報。
* [!UICONTROL Total Trait Realizations] 只會計 [!UICONTROL Rule-based Traits] 算。

## 特徵的一般報表結果{#general-report-results-traits}

執行「一般」報表並選取&#x200B;**[!UICONTROL Trait]**&#x200B;作為報表類型時，可使用下列篩選條件。

按[!UICONTROL Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations] 是在所選時間範圍內將特徵新增至其設定檔的匿名裝置訪客數量。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內匿名特徵實現的總數。
* [!UICONTROL Total Trait Population] 是您的匿名裝置訪客在其設定檔上具有此特徵的數量。

![general-report-traits-device](assets/general-report-traits-deviceid.png)

按[!UICONTROL Cross-Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations] 是在選取的時間範圍內，已驗證將特徵新增至其設定檔的訪客數。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內已驗證的特徵實現總數。
* [!UICONTROL Total Trait Population] 是已驗證的訪客在其設定檔上具有此特徵的數量。

![一般報表特徵 — 跨裝置](assets/general-report-traits-cross-device.png)

<!-- 
### Unique Trait Realizations

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. For example, if a user visited your homepage three times on 10/1, you would see one Unique Trait Realization.

### Total Trait Realizations

This metric represents the total amount of trait fires for the trait in your selected time range. For example, if a user visited your homepage, then navigated to your tech news and your sports news sections, they would appear in the General Report as three total trait realizations, and one unique trait realization.

### Total Trait Population

This metric represents the total amount of Audience Manager UUIDs that are currently qualified for the trait. Use this number to understand the total amount of users you could use for segmentation and targeting. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). For example, a user visiting your homepage three times today and never returning afterwards, would remain as a user in this population every day until 120 days from now. At the 120 day mark, they would be removed from the population. Read our [Trait and Segment Qualification Reference](../features/traits/trait-and-segment-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

The illustration below shows the results of running a general report for the Trait report type. -->
<!-- 
![](assets/general_reports_metrics.png) -->


## 區段的一般報表結果{#general-report-results-segments}

執行「一般」報表並選取&#x200B;**[!UICONTROL Segment]**&#x200B;作為報表類型時，可使用下列量度：

### 即時區段母體

此量度代表指定時間範圍內即時檢視的實際不重複訪客數量，以及在Audience Manager看到這些訪客時符合區段資格。

### 總區段母體

此量度代表在您選取的回顧期間內，符合區段資格的Audience ManagerUUID總數。 您的1天總區段母體代表鎖定目標最準確的使用者群。

>[!NOTE]
>
>選取&#x200B;**[!UICONTROL Include Destination Mappings]**&#x200B;以查看已啟動目的地的區段母體劃分。

下圖顯示執行「區段」報表類型一般報表的結果。

![](assets/general_reports_segment_metrics.png)

## 目標的一般報表結果{#general-report-results-destinations}

執行「一般」報表並選取&#x200B;**[!UICONTROL Destination]**&#x200B;作為報表類型時，可使用下列量度：

**即時區段母體**

此量度代表指定時間範圍內即時檢視的實際不重複訪客數量，以及在Audience Manager看到這些訪客時符合區段資格。

**總區段母體**

此量度代表回顧期間內，屬於區段的Audience ManagerUUID總數，已傳送至目的地。

下圖顯示為「目的地」報表類型執行一般報表的結果。

![](assets/general_reports_destinations.png)
