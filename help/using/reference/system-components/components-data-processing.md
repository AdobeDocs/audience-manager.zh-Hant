---
description: 資料處理元件包括Hadoop、Snowflake、SOLR和Tableau。
seo-description: Data processing components include Hadoop, Snowflake, SOLR, and Tableau.
seo-title: Data Processing Components
solution: Audience Manager
title: 資料處理元件
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: System Components
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 3%

---

# 資料處理元件{#data-processing-components}

資料處理元件包括Hadoop、Snowflake、SOLR和Tableau。

<!-- 

c_comproc.xml

 -->

Audience Manager使用以下元件處理資料：

## Hadoop {#hadoop}

在 [!DNL Audience Manager],Hadoop是包含所有內容的主資料庫 [!DNL Audience Manager] 瞭解用戶。 例如，當 [配置檔案快取伺服器](../../reference/system-components/components-data-collection.md) 建立包含有關用戶資料的日誌檔案，然後將該資料發送到Hadoop以進行儲存。 其他重要Hadoop要素包括：

* **配置單元：** 用於Hadoop的資料倉庫。 Hive管理對儲存在Hadoop中的資料的即席查詢。

* **HBase:** 一個非常大的Hadoop資料庫。 它處理和管理入站和出站資料、特性規則、算法建模資訊，並執行與儲存和將資料移動到不同系統相關的許多其它功能。

客戶沒有直接訪問這些系統的權限。 但是，客戶會間接與他們合作，因為這些元件儲存有關其站點訪問者的重要資料。

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/) 是一個海量的雲資料庫。 它向許多面板圖形及其相關文本框提供資料，這些文本框顯示圖形中每個項的更改百分比。 如果您使用 [!DNL Audience Manager] 查看儀表板報告，您正在與 [!UICONTROL Snowflake]。



![](assets/dashboardreport.png)

這絕不是一個全面的清單，但是一些常見的儀表板報告 [!UICONTROL Snowflake] 負責包括：

* [每日特徵變化報表](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* 所有重疊報告(請參閱 [互動式報告](/help/using/reporting/dynamic-reports/dynamic-reports.md) )的正平方根。
* [未使用的訊號報表](/help/using/reporting/dynamic-reports/unused-signals.md)

## 索爾 {#solr}

SOLR是Apache提供的開源資料庫和伺服器系統。 它為我們的大型資料集提供了強大而快速的搜索功能。 作為 [!DNL Audience Manager] 客戶，您可以在生成段時看到SOLR正在執行中。 它向 [!UICONTROL Estimated Historic Segment Size] 報告。 SOLR由於其速度快，非常適合此角色。 例如，SOLR能夠在您構建規則和向段添加新特徵時更新歷史大小資料。



![](assets/audsize.png)

## 塔布洛 {#tableau}

[!DNL Audience Manager] 使用 [塔布洛](https://www.tableausoftware.com/) 在 [互動式報告](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 和 [Audience Optimization報告](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。 互動式報告顯示特徵和段的效能和重疊資料。 它們不使用排列在列和行中的數字，而是使用不同的形狀、顏色和大小返回資料。 此外，您可以選擇單個或一組資料點，並細化到報表結果，以瞭解更多詳細資訊。 這些可視化技術和報告交互性有助於使大量數字資料更易於理解。



![](assets/advertiser_analytics.png)
