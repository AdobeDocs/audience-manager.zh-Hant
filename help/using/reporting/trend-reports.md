---
description: 趨勢報表傳回特徵和區段上的趨勢資料。
seo-description: 趨勢報表傳回特徵和區段上的趨勢資料。
seo-title: 趨勢報表
solution: Audience Manager
title: 趨勢報表
uuid: debug7d4-7cbb-4403-9104-312f9230aea1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# Trend Reports{#trend-reports}

趨勢報表傳回特徵和區段上的趨勢資料。

## 概述 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] uses [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) to extend user-group permissions to the [!UICONTROL Trend] reports.使用者只能在報告中看到具有檢視權限的特性和區段。[!UICONTROL RBAC] 功能可讓您控制可供內部團隊檢視的報告資料。

例如，管理不同廣告商帳戶的代理商可以設定使用者群組權限，讓管理廣告商A帳戶的團隊無法看見廣告商B的報表資料。

Run a [!UICONTROL Trend] report when you need to:

* 依據特徵和細分來審核趨勢資料。
* 以1、7、14、30、60和90天間隔追蹤趨勢。
* 比較特徵和區段趨勢隨時間變化。
* 識別強大或不良的績效特徵和區段。
* 匯出資料(. csv格式)以進行進一步分析和共用。

The following illustration provides a high-level overview of key elements in the [!UICONTROL Trend] report.

![](assets/trend_reports.png)

1. 設定以下選項: 

   **報表類型：** 選取所需的報表類型(特徵或區段)。

   **日期範圍：** 指定報表的日期範圍(開始日期和結束日期)。

   **顯示間隔：** 指定顯示間隔(1、7、14、30、60和90天間隔)。

2. 依名稱或ID搜尋特徵或區段。
3. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.
4. 產生報表以以圖形格式顯示資料，或將報表匯出為CSV格式。

## Run a Trend Report {#run-trend-report}

This procedure describes how to run a [!UICONTROL Trend] report.

<!-- 

t_working_with_trend_reports.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL Trend Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: **[!UICONTROL Trait]** or **[!UICONTROL Segment]**.
1. 按一下日期方塊以顯示日曆，然後選取報表的開始和結束日期。
1. 指定顯示間隔：以1、7、14、30、60或90天為單位。
1. 依名稱或ID搜尋特徵或區段。
1. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.

   For best performance, run a [!UICONTROL Trend] report on fewer than 20 traits or segments at a time.
1. Click **[!UICONTROL Graph Traits]** or **[!UICONTROL Graph Segments]**, depending on which type of report you are viewing (Traits or Segments).

   這些選項會忽略所有資料夾，並僅繪制個別選取的特徵或區段。

   或

   Click **[!UICONTROL Export to CSV]** to export the trait or segment data and all folders in CSV format for further analysis and sharing. This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 僅供計算。[!UICONTROL Rule-based Traits]

1. (選擇性)將滑鼠指標暫留在個別特徵或區段上，以顯示每個資料點的瀏覽次數和日期。

   您可以按一下表格中的欄標題，以遞增或遞減順序排序結果。

[!UICONTROL Trended Trait] 對於報表，零表示未 [!DNL Audience Manager] 收集當天資料的零。空白項目表示特徵不存在。下列範例顯示兩種類型的項目範例：

![](assets/trended_data.png)
