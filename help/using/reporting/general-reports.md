---
description: 「一般」報表會傳回特徵、區段和目的地的效能資料。
seo-description: Audience Manager中的「一般」報表會傳回特徵、區段和目的地的效能資料。
seo-title: Audience Manager中的一般報表
solution: Audience Manager
title: 一般報表
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: general & trend reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 1%

---


# 一般報表{#general-reports}

[!UICONTROL General]報表會傳回特徵、區段和目的地的效能資料。

## 概述 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])將使用者群組權限延伸至報 [!UICONTROL General] 表。使用者在報告中只能看到他們有權檢視的特徵和區段。 [!UICONTROL RBAC] 功能可讓您控制內部團隊可檢視的報表資料。例如，管理不同廣告商帳戶的代理商可以設定使用者群組權限，讓管理廣告商A帳戶的團隊看不到廣告商B的報告資料。

當您需要時，執行[!UICONTROL General]報表：

* 依特徵、區段或目的地檢視效能。
* 以1、7、14、30、60和90天間隔追蹤印象（總計和唯一）。
* 檢視總負載和唯一負載計數。
* 比較特徵和區段效能。
* 識別強或弱的效能特徵和區段、分析需求，或將負載／火力資料與協力廠商報表進行比較。
* 匯出資料（.csv格式）以進一步分析和共用。

下圖提供[!UICONTROL General]報告中關鍵元素的高階概述。

![](assets/general_reports.png)

1. 設定以下選項: 

   * **報表類型：** 選擇所要的報表類型（特徵、區段或目標）。

   * **對於截止日期：** 指定報表的日期範圍。

2. 依名稱或ID搜尋特徵、區段或目標。
3. 從資料夾清單中，將您要向右側的[!UICONTROL Selections]面板報告的特徵、區段或目標拖放至。
4. 產生要顯示在可匯出表格中的報表。

## 運行常規報告{#run-general-report}

本節介紹如何運行[!UICONTROL General]報告並設定時間和其他效能選項。

<!-- 

t_run_general_report.xml

 -->

1. 在&#x200B;**[!UICONTROL Analytics]**&#x200B;控制面板中，按一下&#x200B;**[!UICONTROL General Reports]**。
1. 從&#x200B;**[!UICONTROL Report Type]**&#x200B;下拉式清單中，選取所要的類型：特徵、區段或目標。
1. *條* 件：按一下日期方塊以顯示日曆，然後如果您想要指定非今天的日期，請選取報表的結束日期。
1. 依名稱或ID搜尋特徵、區段或目標。
1. 從資料夾清單中，將您要向右側的[!UICONTROL Selections]面板報告的特徵、區段或目標拖放至。
1. 按一下 **[!UICONTROL Run Report]**.

   結果會顯示在可匯出的表格中。 按一下欄標題，以遞增或遞減順序排序結果。
1. 選擇報表上方所要的選項按鈕，以依效能（[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]或[!UICONTROL Total Trait Population]）或依時間（1、7、14、30、60或90天範圍）篩選資料。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 只計 [!UICONTROL Rule-based Traits] 算。

1. *可選* 按一下 **[!UICONTROL Export to CSV]**。這會匯出所有日範圍的[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]和[!UICONTROL Total Trait Population]。

## 一般報告結果說明{#general-reports-explained}

[!UICONTROL General Reports]中的數字直接由我們的[!UICONTROL User Profile Store]生成。 結果反映產生這些報告數字時，後端包含[!DNL Audience Manager]的使用者人數。

* 這些數字不包含流量過多的訪客ID。 在到達後端系統之前，會先篩選來自機器人的流量。 此外，在後端執行每週清理作業時，會捨棄某些機器人流量。
* 如果您透過傳入處理將[!DNL Audience Manager] UUID鎖定為板載資料，而這些ID包含在我們系統中不再作用的使用者，則這些非作用中的[!DNL Audience Manager] UUID永遠不會到達[!UICONTROL User Profile Store]，也不會報告。
* [!UICONTROL Total Trait Realizations] 只計 [!UICONTROL Rule-based Traits] 算。

## 特徵的一般報告結果{#general-report-results-traits}

當您執行「一般」報表並選取&#x200B;**[!UICONTROL Trait]**&#x200B;作為報表類型時，以下篩選器可用。

按[!UICONTROL Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations] 是所選時間範圍內將特徵新增至其描述檔的匿名裝置訪客數。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內匿名特徵實現的總數。
* [!UICONTROL Total Trait Population] 是您的匿名裝置訪客在其個人資料上具有此特徵的數目。

![general-report-traits-device](assets/general-report-traits-deviceid.png)

按[!UICONTROL Cross-Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations] 是已驗證的訪客在所選時間範圍內將特徵新增至其描述檔的數量。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內已驗證特徵實現的總數。
* [!UICONTROL Total Trait Population] 是已驗證訪客在其個人資料上具有此特徵的數量。

![general-report-traits-cross-device](assets/general-report-traits-cross-device.png)

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


## 區段的一般報告結果{#general-report-results-segments}

當您執行「一般」報表並選取&#x200B;**[!UICONTROL Segment]**&#x200B;作為報表類型時，可使用下列度量：

### 即時區段人口

此量度代表在指定時間範圍內即時檢視的獨特訪客的實際數量，以及Audience Manager在檢視這些訪客時符合區段資格的訪客。

### 區段總人口

此量度代表在您選取的回顧期間內，符合區段條件的Audience Manager UUID總數。 您的1天「區段總人口」代表您最精準的定位使用者群。

>[!NOTE]
>
>選擇&#x200B;**[!UICONTROL Include Destination Mappings]**&#x200B;以查看已啟用目標的區段人口劃分。

下圖顯示執行區段報表類型一般報表的結果。

![](assets/general_reports_segment_metrics.png)

## 目標的常規報告結果{#general-report-results-destinations}

當您執行「一般」報表並選取&#x200B;**[!UICONTROL Destination]**&#x200B;作為報表類型時，可使用下列度量：

**即時區段人口**

此量度代表在指定時間範圍內即時檢視的獨特訪客的實際數量，以及Audience Manager在檢視這些訪客時符合區段資格的訪客。

**區段總人口**

此量度代表回顧時段內，已傳送至目的地之區段的Audience Manager UUID總數。

下圖顯示執行「目標」報表類型一般報表的結果。

![](assets/general_reports_destinations.png)
