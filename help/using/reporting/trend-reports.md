---
description: 趨勢報表會傳回特徵和區段的趨勢資料。
seo-description: A Trend report returns trend data on traits and segments.
seo-title: Trend Reports
solution: Audience Manager
title: 趨勢報表
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: General & Trend Reports
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: 42f9b32edcde423369f7e8254b04fdc6162130d0
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# 趨勢報表{#trend-reports}

趨勢報表會傳回特徵和區段的趨勢資料。

## 概述 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager]使用[!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])將使用者群組許可權延伸至[!UICONTROL Trend]報告。 使用者在報表中只能看見他們有權檢視的特徵和區段。 [!UICONTROL RBAC]功能可讓您控制內部團隊可以檢視哪些報告資料。

例如，管理不同廣告商帳戶的機構可以設定使用者群組許可權，好讓管理廣告商A帳戶的團隊無法看到廣告商B的報表資料。

當您需要以下任務時，請執行[!UICONTROL Trend]報告：

* 依特徵和區段檢閱趨勢資料。
* 按1、7、14、30、60和90天間隔追蹤趨勢。
* 比較特徵和區段在一段時間內的趨勢。
* 識別效能強大或效能不佳的特徵和區段。
* 匯出資料（.csv格式）以供進一步分析和共用。

下圖提供[!UICONTROL Trend]報表中重要元素的高階概觀。

![](assets/trend_reports.png)

1. 設定以下選項: 
   **報表型別：**選取所需的報表型別（特徵或區段）。
   **日期範圍：**指定報表的日期範圍（開始日期和結束日期）。
   **顯示間隔：**&#x200B;指定顯示間隔（1、7、14、30、60和90天間隔）。
1. 依名稱或ID搜尋特徵或區段。
1. 從資料夾清單中，拖放您要報告的特徵或區段至右側的[!UICONTROL Selections]面板。
1. 產生報表以圖形格式顯示資料，或將報表匯出為CSV格式。

## 執行趨勢報表 {#run-trend-report}

此程式說明如何執行[!UICONTROL Trend]報告。

<!-- 

t_working_with_trend_reports.xml

 -->

1. 在&#x200B;**[!UICONTROL Analytics]**&#x200B;儀表板中，按一下&#x200B;**[!UICONTROL Trend Reports]**。
1. 從&#x200B;**[!UICONTROL Report Type]**&#x200B;下拉式清單中，選取所要的型別： **[!UICONTROL Trait]**&#x200B;或&#x200B;**[!UICONTROL Segment]**。
1. 按一下日期方塊以顯示行事曆，然後選取報表的開始和結束日期。
1. 指定顯示間隔：1、7、14、30、60或90天。
1. 依名稱或ID搜尋特徵或區段。
1. 從資料夾清單中，拖放您要報告的特徵或區段至右側的[!UICONTROL Selections]面板。
   * 為獲得最佳效能，一次對少於20個特徵或區段執行[!UICONTROL Trend]報告。
1. 根據您檢視的報表型別（特徵或區段），按一下&#x200B;**[!UICONTROL Graph Traits]**&#x200B;或&#x200B;**[!UICONTROL Graph Segments]**。 這些選項會忽略所有資料夾，而只顯示個別選取的特徵或區段。

   或

   按一下&#x200B;**[!UICONTROL Export to CSV]**&#x200B;將特徵或區段資料以及所有資料夾匯出為CSV格式，以供進一步分析和共用。 這會匯出所有日期範圍的[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]和[!UICONTROL Total Trait Population]。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations]僅針對[!UICONTROL Rule-based Traits]計算。

1. （選用）將滑鼠移至個別特徵或區段上，即可顯示每個資料點的造訪次數和日期。 您可以按一下表格中的欄標題，以遞增或遞減順序排序結果。

## 特徵的趨勢報表結果 {#trend-report-results-traits}

當您執行[!UICONTROL Trend Report]並選取&#x200B;**[!UICONTROL Trait]**&#x200B;作為報表型別時，可使用下列篩選器。

依[!UICONTROL Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations]是您在所選時間範圍內將特徵新增至其設定檔的匿名裝置訪客數量。
* [!UICONTROL Total Trait Realization]是所選時間範圍內的匿名滑鼠特徵實現總數。
* [!UICONTROL Total Trait Population]是您的匿名裝置訪客在其設定檔中擁有此特徵的數目。

依[!UICONTROL Cross-Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations]是在選取的時間範圍內，將特徵新增至設定檔的已驗證訪客數量。
* [!UICONTROL Total Trait Realization]是所選時間範圍內已驗證的特徵實現總數。
* [!UICONTROL Total Trait Population]是您的已驗證訪客在其設定檔中擁有此特徵的數量。

![趨勢報表特徵](assets/trend-report-traits.png)

零表示[!DNL Audience Manager]未收集當天的資料。 空白專案表示該特徵不存在。

請觀看下方的影片，詳細瞭解跨裝置量度的運作方式。

[瞭解Audience Manager中的跨裝置量度](https://experienceleague.adobe.com/en/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager)

## 區段的趨勢報表結果 {#segment-report-results-traits}

當您執行[!UICONTROL Trend Report]並選取&#x200B;**[!UICONTROL Segments]**&#x200B;作為報表型別時，可使用下列篩選器。

* **[!UICONTROL Real-time Segment Population]**：在選取的時間範圍內符合區段資格的訪客數。
* **[!UICONTROL Total Segment Population]**：符合區段資格的訪客總數。

![趨勢報表區段](assets/trend-report-segments.png)
