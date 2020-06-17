---
description: 資料處理元件包括Hadoop、Snowflake、SOLR和Tableau。
seo-description: 資料處理元件包括Hadoop、Snowflake、SOLR和Tableau。
seo-title: 資料處理元件
solution: Audience Manager
title: 資料處理元件
uuid: d458d869-7a23-4016-871d-0b994cf4af06
translation-type: tm+mt
source-git-commit: 9a92420b1f0116c0fd71db56895720e0ee894f30
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

在 [!DNL Audience Manager]中，Hadoop是主資料庫，它包含了用戶 [!DNL Audience Manager] 的所有知識。 例如，當Profile Cache Servers [建立包含有關用戶資料的日誌檔案時](../../reference/system-components/components-data-collection.md) ，它將該資料發送到Hadoop以進行儲存。 其他重要的Hadoop元素包括：

* **蜂巢：** 適用於Hadoop的資料倉庫。 Hive管理對Hadoop中儲存的資料的臨機查詢。

* **HBase:** 非常大的Hadoop資料庫。 它處理並管理傳入和傳出的資料、特徵規則、演算法模型資訊，並執行許多其他與儲存和移動資料至不同系統相關的功能。

客戶無法直接存取這些系統。 不過，客戶確實會間接與他們合作，因為這些元件會儲存有關其網站訪客的重要資料。

## 雪花 {#snowflake}

[雪花](https://www.snowflake.net/) ，是海量的雲資料庫。 它會提供資料給許多控制面板圖形及其相關的文字方塊，以顯示圖形中每個項目的變更百分比。 如果您使 [!DNL Audience Manager] 用並檢視控制面板報表，則您會與由提供的資料互動 [!UICONTROL Snowflake]。



![](assets/dashboardreport.png)

這絕非完整清單，但是有些常見的控制面板報表需 [!UICONTROL Snowflake] 負責包括：

* [每日特徵變化報表](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* 所有重疊報表(如需每個重疊報 [表的相關資訊](/help/using/reporting/dynamic-reports/dynamic-reports.md) ，請參閱互動報表區段)。
* [未使用的訊號報表](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR是Apache的開源資料庫和伺服器系統。 它提供強穩且快速的搜尋功能，來覆蓋我們的大型資料集。 身為客 [!DNL Audience Manager] 戶，您可以在建立區段時看到SOLR的實際運作。 它提供資料至報 [!UICONTROL Estimated Historic Segment Size] 表。 SOLR因其速度而最適合此角色。 例如，SOLR可在您建立規則並新增特徵至區段時更新歷史大小資料。



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] 使用 [Tableau](https://www.tableausoftware.com/) ，在互動式報表和對象最佳化報表中顯示資料 [](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)[](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。 互動式報表會顯示特徵和區段的效能和重疊資料。 它們不使用列和列中排列的數字，而是使用不同的形狀、顏色和大小傳回資料。 此外，您可以選擇個別或資料點群組，並深入檢視報表結果以取得詳細資訊。 這些視覺化技巧和報表互動功能可協助您更容易瞭解大量數值資料。



![](assets/advertiser_analytics.png)

