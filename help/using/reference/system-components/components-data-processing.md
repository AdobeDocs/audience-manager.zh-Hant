---
description: 資料處理元件包括Hadoop、Snowflake、SOLR和Tableau。
seo-description: 資料處理元件包括Hadoop、Snowflake、SOLR和Tableau。
seo-title: 資料處理元件
solution: Audience Manager
title: 資料處理元件
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 3%

---


# 資料處理元件{#data-processing-components}

資料處理元件包括Hadoop、Snowflake、SOLR和Tableau。

<!-- 

c_comproc.xml

 -->

Audience Manager使用下列元件來處理資料：

## Hadoop {#hadoop}

在[!DNL Audience Manager]中，Hadoop是包含[!DNL Audience Manager]對用戶所知一切的主資料庫。 例如，當[Profile Cache Servers](../../reference/system-components/components-data-collection.md)建立包含有關用戶資料的日誌檔案時，它將該資料發送到Hadoop以進行儲存。 其他重要的Hadoop元素包括：

* **Hive：適** 用於Hadoop的資料倉庫。Hive管理對Hadoop中儲存的資料的臨機查詢。

* **HBase：一** 個非常大的Hadoop資料庫。它處理並管理傳入和傳出的資料、特徵規則、演算法模型資訊，並執行許多其他與儲存和移動資料至不同系統相關的功能。

客戶無法直接存取這些系統。 不過，客戶確實會間接與他們合作，因為這些元件會儲存有關其網站訪客的重要資料。

## 雪花{#snowflake}

[Snowflakeke是](https://www.snowflake.net/) 一個龐大的雲端資料庫。它會提供資料給許多控制面板圖形及其相關的文字方塊，以顯示圖形中每個項目的變更百分比。 如果您使用[!DNL Audience Manager]並查看控制面板報表，則您會與[!UICONTROL Snowflake]提供的資料互動。



![](assets/dashboardreport.png)

這絕非完整清單，但是有些常見的控制面板報表會負責包含：[!UICONTROL Snowflake]

* [每日特徵變化報表](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* 所有重疊報告（有關每個重疊報告的資訊，請參閱[ Interactive Reports](/help/using/reporting/dynamic-reports/dynamic-reports.md)部分）。
* [未使用的訊號報表](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR是Apache的開源資料庫和伺服器系統。 它提供強穩且快速的搜尋功能，來覆蓋我們的大型資料集。 身為[!DNL Audience Manager]客戶，您可以在建立區段時看到SOLR的實際運作。 它提供資料給[!UICONTROL Estimated Historic Segment Size]報表。 SOLR因其速度而最適合此角色。 例如，SOLR可在您建立規則並新增特徵至區段時更新歷史大小資料。



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] 使用 [](https://www.tableausoftware.com/) 互動式報表和對象最 [佳化](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 報表中的 [表格自動顯示資料](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。互動式報表會顯示特徵和區段的效能和重疊資料。 它們不使用列和列中排列的數字，而是使用不同的形狀、顏色和大小傳回資料。 此外，您可以選擇個別或資料點群組，並深入檢視報表結果以取得詳細資訊。 這些視覺化技巧和報表互動功能可協助您更容易瞭解大量數值資料。



![](assets/advertiser_analytics.png)

