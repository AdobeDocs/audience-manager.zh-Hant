---
description: 資料處理元件包括Hadoop、Snorflake、SOLR和Tableau。
seo-description: 資料處理元件包括Hadoop、Snorflake、SOLR和Tableau。
seo-title: 資料處理元件
solution: Audience Manager
title: 資料處理元件
uuid: d458d869-7a23-4016-871d-0b994cf4af06
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Processing Components{#data-processing-components}

資料處理元件包括Hadoop、Snorflake、SOLR和Tableau。

<!-- 

c_comproc.xml

 -->

Audience Manager使用下列元件來處理資料：

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop is the master database that contains everything [!DNL Audience Manager] knows about a user. For example, when the [Profile Cache Servers](../../reference/system-components/components-data-collection.md) create log files that contain data about your users, it sends that data to Hadoop for storage. 其他重要的Hadoop元素包括：

* **希伯來文：** Hadoop的資料倉庫。Have管理在Hadoop中儲存的資料的臨機查詢。

* **Hase：** 龐大的Hadoop資料庫。它會處理和管理傳入和傳出資料、特徵規則、演算法模型資訊，並執行許多與儲存和移動資料至不同系統相關的功能。

客戶無法直接存取這些系統。不過，客戶會間接與他們合作，因為這些元件會儲存有關其網站訪客的重要資料。

## Snowflake {#snowflake}

[Snorflake](https://www.snowflake.net/) 是龐大的雲端資料庫。它會將資料提供給許多控制面板圖表及其相關文字方塊，以顯示圖形中每個項目的變更百分比。If you use [!DNL Audience Manager] and look at the dashboard reports, you&#39;re interacting with data provided by [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

This is by no means a comprehensive list, but some common dashboard reports that [!UICONTROL Snowflake] is responsible for include:

* [每日特徵變化報表](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [傳送與效能報告](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* All the overlap reports (see the [Interactive Reports](/help/using/reporting/dynamic-reports/dynamic-reports.md) section for information about each overlap report).
* [未使用的訊號報表](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR是來自Apache的開放原始碼資料庫和伺服器系統。它可為大型資料集提供強穩快速的搜尋功能。[!DNL Audience Manager] 身為客戶，您可以在建立區段時查看SOLR。It provides data to the [!UICONTROL Estimated Historic Segment Size] report. SOLR最適合此角色，因為它的速度更快。例如，SOLR可在您建立規則並新增新特性至區段時，更新歷史大小資料。



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] 使用 [Tableau](https://www.tableausoftware.com/) 在 [互動報表](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 和 [對象最佳化報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)中顯示資料。互動報表會顯示特徵和區段的效能和重疊資料。他們不會使用以欄和列排列的數字，而是使用不同的形狀、顏色和大小傳回資料。此外，您可以選擇個別或資料點群組，並深入探究報表結果，以瞭解詳細資訊。這些視覺化技巧和報表互動功能可讓您更容易瞭解大量的數值資料。



![](assets/advertiser_analytics.png)

