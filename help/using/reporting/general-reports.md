---
description: 常規報告返回有關特徵、段和目標的效能資料。
seo-description: A General report in Audience Manager returns performance data on traits, segments, and destinations.
seo-title: General Reports in Audience Manager
solution: Audience Manager
title: 一般報表
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: General & Trend Reports
exl-id: dc16a821-b776-4a04-af60-4b8c914253dd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 1%

---

# 一般報表{#general-reports}

A [!UICONTROL General] report返回有關特徵、段和目標的效能資料。

## 概述 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])將用戶組權限擴展到 [!UICONTROL General] 報告。 用戶只能在報告中查看他們有權查看的那些特徵和段。 [!UICONTROL RBAC] 功能允許您控制內部團隊可以查看的報告資料。 例如，管理不同廣告商帳戶的代理可以配置用戶組權限，以便管理廣告商A帳戶的團隊無法查看廣告商B的報告資料。

運行 [!UICONTROL General] 需要時報告：

* 按特性、段或目標查看效能。
* 按1天、7天、14天、30天、60天和90天間隔跟蹤印象（總數和唯一）。
* 查看總負荷和唯一負荷計數。
* 比較特性和段效能。
* 確定效能強弱或效能差的特性和段，分析需求，或將負載/火災資料與第三方報告進行比較。
* 導出資料（.csv格式）以便進一步分析和共用。

下圖提供了中關鍵元素的高級概述 [!UICONTROL General] 報告。

![](assets/general_reports.png)

1. 設定以下選項: 

   * **報告類型：** 選擇所需的報告類型（特性、段或目標）。

   * **日期至：** 指定報表的日期範圍。

2. 按名稱或ID搜索特性、段或目標。
3. 從資料夾清單中，拖放要報告到的特徵、段或目標 [!UICONTROL Selections] 右側的面板。
4. 生成要在可導出表中顯示的報告。

## 運行常規報告 {#run-general-report}

本節介紹如何運行 [!UICONTROL General] 報告和設定時間和其他效能選項。

<!-- 

t_run_general_report.xml

 -->

1. 在 **[!UICONTROL Analytics]** 操控板，按一下 **[!UICONTROL General Reports]**。
1. 從 **[!UICONTROL Report Type]** 下拉清單中，選擇所需類型：特性、段或目標。
1. *條件* 按一下日期框以顯示日曆，如果要指定今天以外的日期，請選擇報表的結束日期。
1. 按名稱或ID搜索特性、段或目標。
1. 從資料夾清單中，拖放要報告到的特徵、段或目標 [!UICONTROL Selections] 右側的面板。
1. 按一下 **[!UICONTROL Run Report]**.

   結果顯示在可導出的表中。 按一下列標題以按升序或降序對結果進行排序。
1. 選擇報表頂部的所需選項按鈕以按效能篩選資料( [!UICONTROL Unique Trait Realizations]。 [!UICONTROL Total Trait Realizations]或 [!UICONTROL Total Trait Population])或按時間（1、7、14、30、60或90天範圍）。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 為 [!UICONTROL Rule-based Traits] 只是。

1. *可選* 按一下 **[!UICONTROL Export to CSV]**。 這將導出 [!UICONTROL Unique Trait Realizations]。 [!UICONTROL Total Trait Realizations], [!UICONTROL Total Trait Population] 全天範圍。

## 一般報告結果說明 {#general-reports-explained}

中的數字 [!UICONTROL General Reports] 直接由 [!UICONTROL User Profile Store]。 結果反映了 [!DNL Audience Manager] 生成這些報告編號時包含在後端中。

* 這些數字不包括流量過大的訪問者ID。 在到達我們的後端系統之前，會過濾來自bot的流量。 此外，在後端運行每週清理作業期間，會丟棄某些bot通信。
* 如果通過入站處理將板載資料鎖定 [!DNL Audience Manager] UUID，這些ID包括在系統中不再處於活動狀態的用戶，這些不活動 [!DNL Audience Manager] UUID永遠不會到達 [!UICONTROL User Profile Store] 沒有報告。
* [!UICONTROL Total Trait Realizations] 為 [!UICONTROL Rule-based Traits] 只是。

## 特徵的常規報告結果 {#general-report-results-traits}

運行「常規」報告並選擇時，以下篩選器可用 **[!UICONTROL Trait]** 按鈕。

篩選結果時，按 [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] 是在所選時間範圍內將特性添加到其配置檔案的匿名設備訪問者的數量。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內匿名特性實現的總數。
* [!UICONTROL Total Trait Population] 是您的匿名設備訪問者在他們的檔案中具有這個特徵的人數。

![通用報告特徵裝置](assets/general-report-traits-deviceid.png)

篩選結果時，按 [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] 是在所選時間範圍內向其配置檔案添加該特性的已驗證訪問者的數量。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內經過驗證的特性實現的總數。
* [!UICONTROL Total Trait Population] 是你經過認證的訪問者在他們的檔案中有這個特點。

![通用報告特徵交叉裝置](assets/general-report-traits-cross-device.png)

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


## 段的常規報告結果 {#general-report-results-segments}

運行「一般資訊」報告並選擇時，以下度量可用 **[!UICONTROL Segment]** 報告類型：

### 即時段填充

此度量表示在指定時間範圍內即時看到的具有唯一訪問者的實際數量，以及在Audience Manager看到這些訪問者時符合該段的條件。

### 段總人口

此度量表示所選回溯期間內限定段的Audience ManagerUUID總數。 您的1天總段填充表示您最準確的目標用戶群。

>[!NOTE]
>
>選擇 **[!UICONTROL Include Destination Mappings]** 查看已激活目標的段總量細目。

下圖顯示了運行段報告類型的常規報告的結果。

![](assets/general_reports_segment_metrics.png)

## 目標的常規報告結果 {#general-report-results-destinations}

運行「一般資訊」報告並選擇時，以下度量可用 **[!UICONTROL Destination]** 報告類型：

**即時段填充**

此度量表示在指定時間範圍內即時看到的具有唯一訪問者的實際數量，以及在Audience Manager看到這些訪問者時符合該段的條件。

**段總人口**

此度量表示在回查期間內屬於段的Audience ManagerUUID的總數，這些UUID已發送到目標。

下圖顯示了為目標報告類型運行常規報告的結果。

![](assets/general_reports_destinations.png)
