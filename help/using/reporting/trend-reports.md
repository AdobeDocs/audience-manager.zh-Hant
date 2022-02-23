---
description: 趨勢報表返回有關特徵和段的趨勢資料。
seo-description: A Trend report returns trend data on traits and segments.
seo-title: Trend Reports
solution: Audience Manager
title: 趨勢報表
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: General & Trend Reports
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 1%

---

# 趨勢報表{#trend-reports}

趨勢報表返回有關特徵和段的趨勢資料。

## 概述 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])將用戶組權限擴展到 [!UICONTROL Trend] 報告。 用戶只能在報告中查看他們有權查看的那些特徵和段。 [!UICONTROL RBAC] 功能允許您控制內部團隊可以查看的報告資料。

例如，管理不同廣告商帳戶的代理可以配置用戶組權限，以便管理廣告商A帳戶的團隊無法查看廣告商B的報告資料。

運行 [!UICONTROL Trend] 需要時報告：

* 按特徵和段查看趨勢資料。
* 按1、7、14、30、60和90天間隔跟蹤趨勢。
* 比較特性和段趨勢。
* 識別效能強弱和效能差的特性和片段。
* 導出資料（.csv格式）以便進一步分析和共用。

下圖提供了中關鍵元素的高級概述 [!UICONTROL Trend] 報告。

![](assets/trend_reports.png)

1. 設定以下選項: 
   **報告類型：** 選擇所需的報告類型（特性或段）。
   **日期範圍：** 指定報表的日期範圍（起始日期和終止日期）。
   **顯示間隔：** 指定顯示間隔（1、7、14、30、60和90天間隔）。
1. 按名稱或ID搜索特性或段。
1. 從資料夾清單中，拖放要報告到的特徵或段 [!UICONTROL Selections] 右側的面板。
1. 生成以圖形格式顯示的報告或將報告導出為CSV格式。

## 運行趨勢報告 {#run-trend-report}

此過程介紹如何運行 [!UICONTROL Trend] 報告。

<!-- 

t_working_with_trend_reports.xml

 -->

1. 在 **[!UICONTROL Analytics]** 操控板，按一下 **[!UICONTROL Trend Reports]**。
1. 從 **[!UICONTROL Report Type]** 下拉清單中，選擇所需類型： **[!UICONTROL Trait]** 或 **[!UICONTROL Segment]**。
1. 按一下日期框以顯示日曆，然後選擇報表的起始和終止日期。
1. 指定顯示間隔：1、7、14、30、60或90天。
1. 按名稱或ID搜索特性或段。
1. 從資料夾清單中，拖放要報告到的特徵或段 [!UICONTROL Selections] 右側的面板。
   * 為獲得最佳效能，請運行 [!UICONTROL Trend] 一次報告少於20個特徵或片段。
1. 按一下 **[!UICONTROL Graph Traits]** 或 **[!UICONTROL Graph Segments]**，具體取決於您正在查看的報表類型（「特徵」或「段」）。 這些選項僅忽略單獨選定的特徵或段的所有資料夾和圖形。

   或

   按一下 **[!UICONTROL Export to CSV]** 導出特性或段資料以及所有CSV格式的資料夾，以便進一步分析和共用。 這將導出 [!UICONTROL Unique Trait Realizations]。 [!UICONTROL Total Trait Realizations], [!UICONTROL Total Trait Population] 全天範圍。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 為 [!UICONTROL Rule-based Traits] 只是。

1. （可選）將滑鼠懸停在單個特徵或段上以顯示訪問次數和每個資料點的日期。 可以按一下表中的列標題以按升序或降序對結果進行排序。

## 特徵趨勢報告結果 {#trend-report-results-traits}

以下篩選器在您運行 [!UICONTROL Trend Report] 選擇 **[!UICONTROL Trait]** 按鈕。

篩選結果時，按 [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] 是在所選時間範圍內將特性添加到其配置檔案的匿名設備訪問者的數量。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內匿名滑鼠特徵實現的總數。
* [!UICONTROL Total Trait Population] 是您的匿名設備訪問者在他們的檔案中具有這個特徵的人數。

篩選結果時，按 [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] 是在所選時間範圍內向其配置檔案添加該特性的已驗證訪問者的數量。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內經過驗證的特性實現的總數。
* [!UICONTROL Total Trait Population] 是你經過認證的訪問者在他們的檔案中有這個特點。

![趨勢報告特徵](assets/trend-report-traits.png)

零表示 [!DNL Audience Manager] 沒有收集那天的資料。 空條目表示該特性不存在。

觀看下面的視頻，詳細瞭解跨設備指標的工作原理。

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## 段的趨勢報告結果 {#segment-report-results-traits}

以下篩選器在您運行 [!UICONTROL Trend Report] 選擇 **[!UICONTROL Segments]** 按鈕。

* **[!UICONTROL Real-time Segment Population]**:選定時間範圍內符合段的訪問者數。
* **[!UICONTROL Total Segment Population]**:符合該分部資格的訪客總數。

![趨勢報告段](assets/trend-report-segments.png)
