---
description: 趨勢報表會傳回特徵和區段的趨勢資料。
seo-description: 趨勢報表會傳回特徵和區段的趨勢資料。
seo-title: 趨勢報表
solution: Audience Manager
title: 趨勢報表
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: 一般與趨勢報表
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---

# 趨勢報表{#trend-reports}

趨勢報表會傳回特徵和區段的趨勢資料。

## 概述 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] 使 [!UICONTROL Role Based Access Control] 用([!UICONTROL RBAC])將使用者群組權限延伸至 [!UICONTROL Trend] 報表。使用者在報表中只能看到他們有權檢視的特徵和區段。 [!UICONTROL RBAC] 功能可讓您控制內部團隊可檢視的報表資料。

例如，管理不同廣告商帳戶的代理可設定使用者群組權限，讓管理廣告商A帳戶的團隊看不到廣告商B的報表資料。

執行[!UICONTROL Trend]報表，以滿足以下需要：

* 依特徵和區段檢閱趨勢資料。
* 依1、7、14、30、60和90天間隔追蹤趨勢。
* 比較特徵和區段隨時間的趨勢。
* 識別強或弱的效能特徵和區段。
* 匯出資料（.csv格式）以供進一步分析和共用。

下圖提供[!UICONTROL Trend]報表中關鍵元素的概觀。

![](assets/trend_reports.png)

1. 設定以下選項: 
   **報表類型：** 選取所需的報表類型（特徵或區段）。
   **日期範圍：** 指定報表的日期範圍（開始日期和結束日期）。
   **顯示間隔：** 指定顯示間隔（1、7、14、30、60和90天間隔）。
1. 依名稱或ID搜尋特徵或區段。
1. 從資料夾清單中，將您要報告的特徵或區段拖放至右側的[!UICONTROL Selections]面板。
1. 產生報表以圖形格式顯示資料，或將報表匯出為CSV格式。

## 執行趨勢報表{#run-trend-report}

此過程說明如何運行[!UICONTROL Trend]報告。

<!-- 

t_working_with_trend_reports.xml

 -->

1. 在&#x200B;**[!UICONTROL Analytics]**&#x200B;控制面板中，按一下&#x200B;**[!UICONTROL Trend Reports]**。
1. 從&#x200B;**[!UICONTROL Report Type]**&#x200B;下拉式清單中，選取所需的類型：**[!UICONTROL Trait]**&#x200B;或&#x200B;**[!UICONTROL Segment]**。
1. 按一下日期方塊以顯示日曆，然後選取報表的開始和結束日期。
1. 指定顯示間隔：1、7、14、30、60或90天。
1. 依名稱或ID搜尋特徵或區段。
1. 從資料夾清單中，將您要報告的特徵或區段拖放至右側的[!UICONTROL Selections]面板。
   * 為獲得最佳效能，請一次對少於20個特徵或區段執行[!UICONTROL Trend]報表。
1. 視您檢視的報表類型（特徵或區段）而定，按一下&#x200B;**[!UICONTROL Graph Traits]**&#x200B;或&#x200B;**[!UICONTROL Graph Segments]**。 這些選項只會忽略所有資料夾和圖形，只會個別選取特徵或區段。

   或

   按一下&#x200B;**[!UICONTROL Export to CSV]**&#x200B;將特徵或區段資料以及所有資料夾匯出為CSV格式，以供進一步分析和共用。 這會匯出所有日期範圍的[!UICONTROL Unique Trait Realizations]、[!UICONTROL Total Trait Realizations]和[!UICONTROL Total Trait Population]。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 只會計 [!UICONTROL Rule-based Traits] 算。

1. （選用）將滑鼠移至個別特徵或區段上，以顯示每個資料點的造訪次數和日期。 您可以按一下表格中的欄標題，以遞增或遞減順序排序結果。

## 特徵的趨勢報表結果{#trend-report-results-traits}

當您執行[!UICONTROL Trend Report]並選取&#x200B;**[!UICONTROL Trait]**&#x200B;作為報表類型時，可使用下列篩選器。

按[!UICONTROL Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations] 是在所選時間範圍內將特徵新增至其設定檔的匿名裝置訪客數量。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內匿名滑鼠特徵實現的總數。
* [!UICONTROL Total Trait Population] 是您的匿名裝置訪客在其設定檔上具有此特徵的數量。

按[!UICONTROL Cross-Device ID]篩選結果時：

* [!UICONTROL Unique Trait Realizations] 是在選取的時間範圍內，已驗證將特徵新增至其設定檔的訪客數。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內已驗證的特徵實現總數。
* [!UICONTROL Total Trait Population] 是已驗證的訪客在其設定檔上具有此特徵的數量。

![trend-report-traits](assets/trend-report-traits.png)

零表示[!DNL Audience Manager]未收集當天的資料。 空白項目表示特徵不存在。

請觀看以下影片，深入了解跨裝置量度的運作方式。

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## 區段的趨勢報表結果{#segment-report-results-traits}

當您執行[!UICONTROL Trend Report]並選取&#x200B;**[!UICONTROL Segments]**&#x200B;作為報表類型時，可使用下列篩選器。

* **[!UICONTROL Real-time Segment Population]**:在所選時間範圍內符合區段資格的訪客數。
* **[!UICONTROL Total Segment Population]**:符合區段的訪客總數。

![趨勢報表區段](assets/trend-report-segments.png)
