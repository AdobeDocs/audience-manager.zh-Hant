---
description: 「趨勢」報表會傳回特徵和區段的趨勢資料。
seo-description: 「趨勢」報表會傳回特徵和區段的趨勢資料。
seo-title: 趨勢報表
solution: Audience Manager
title: 趨勢報表
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
translation-type: tm+mt
source-git-commit: 760818663ff3eb32c6de876c756697e1d9034369

---


# 趨勢報表{#trend-reports}

「趨勢」報表會傳回特徵和區段的趨勢資料。

## 概述 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])將使用者群組權限延伸至報 [!UICONTROL Trend] 表。 使用者在報告中只能看到他們有權檢視的特徵和區段。 [!UICONTROL RBAC] 功能可讓您控制內部團隊可檢視的報表資料。

例如，管理不同廣告商帳戶的代理商可以設定使用者群組權限，讓管理廣告商A帳戶的團隊看不到廣告商B的報告資料。

當您需 [!UICONTROL Trend] 要時，執行報表：

* 依特徵和區段檢視趨勢資料。
* 依1、7、14、30、60和90天間隔追蹤趨勢。
* 比較特徵和區段趨勢隨時間的變化。
* 識別強或弱的效能特徵和群體。
* 匯出資料（.csv格式）以進一步分析和共用。

下圖提供報表關鍵元素的高階概 [!UICONTROL Trend] 觀。

![](assets/trend_reports.png)

1. 設定以下選項: 
   **報表類型：** 選取所要的報表類型（特徵或區段）。
   **日期範圍：** 指定報表的日期範圍（開始日期和結束日期）。
   **顯示間隔：** 指定顯示間隔（1、7、14、30、60和90天間隔）。
1. 依名稱或ID搜尋特徵或區段。
1. 從資料夾清單中，將您要報告的特徵或區段拖放至右 [!UICONTROL Selections] 側的面板。
1. 產生報告以圖形格式顯示資料，或將報告匯出為CSV格式。

## Run a Trend Report {#run-trend-report}

此程式說明如何執行報 [!UICONTROL Trend] 表。

<!-- 

t_working_with_trend_reports.xml

 -->

1. 在控制面 **[!UICONTROL Analytics]** 板中，按一下 **[!UICONTROL Trend Reports]**。
1. 從下拉 **[!UICONTROL Report Type]** 式清單中，選取所要的類型：或 **[!UICONTROL Trait]** 者 **[!UICONTROL Segment]**。
1. 按一下日期方塊以顯示日曆，然後選取報表的開始和結束日期。
1. 指定顯示間隔：1、7、14、30、60或90天。
1. 依名稱或ID搜尋特徵或區段。
1. 從資料夾清單中，將您要報告的特徵或區段拖放至右 [!UICONTROL Selections] 側的面板。
   * 為獲得最佳效能， [!UICONTROL Trend] 請一次執行少於20個特徵或區段的報表。
1. 按一 **[!UICONTROL Graph Traits]** 下或 **[!UICONTROL Graph Segments]**，視您檢視的報表類型（特徵或區段）而定。 這些選項僅忽略個別選取的特徵或區段的所有資料夾和圖形。

   或

   按一 **[!UICONTROL Export to CSV]** 下以匯出特徵或區段資料以及所有CSV格式的檔案夾，以進一步分析和共用。 這會匯出 [!UICONTROL Unique Trait Realizations]所有 [!UICONTROL Total Trait Realizations]日期 [!UICONTROL Total Trait Population] 範圍的、和。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 的值 [!UICONTROL Rule-based Traits] 。

1. （選擇性）將滑鼠移至個別特徵或區段上，以顯示每個資料點的瀏覽次數和日期。 您可以按一下表格中的欄標題，以遞增或遞減順序來排序結果。

## 特徵的趨勢報表結果 {#trend-report-results-traits}

當您執行並選取為報表類型時，以 [!UICONTROL Trend Report] 下篩 **[!UICONTROL Trait]** 選器可供使用。

篩選結果時，依 [!UICONTROL Device ID]據：

* [!UICONTROL Unique Trait Realizations] 是所選時間範圍內將特徵新增至其描述檔的匿名裝置訪客數。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內的匿名滑鼠特徵實現總數。
* [!UICONTROL Total Trait Population] 是您的匿名裝置訪客在其個人資料上具有此特徵的數目。

篩選結果時，依 [!UICONTROL Cross-Device ID]據：

* [!UICONTROL Unique Trait Realizations] 是已驗證的訪客在所選時間範圍內將特徵新增至其描述檔的數量。
* [!UICONTROL Total Trait Realization] 是所選時間範圍內已驗證特徵實現的總數。
* [!UICONTROL Total Trait Population] 是已驗證訪客在其個人資料上具有此特徵的數量。

![trend-report-traits](assets/trend-report-traits.png)

零表示未 [!DNL Audience Manager] 收集當天的資料。 空白項目表示特徵不存在。

## 區段的趨勢報表結果 {#segment-report-results-traits}

當您執行並選取為報表類型時，以 [!UICONTROL Trend Report] 下篩 **[!UICONTROL Segments]** 選器可供使用。

* **[!UICONTROL Real-time Segment Population]**:在所選時間範圍內符合區段的訪客數。
* **[!UICONTROL Total Segment Population]**:符合區段的訪客總數。

![trend-report-segments](assets/trend-report-segments.png)