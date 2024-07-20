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
source-wordcount: '395'
ht-degree: 1%

---

# 資料處理元件{#data-processing-components}

資料處理元件包括Hadoop、Snowflake、SOLR和Tableau。

<!-- 

c_comproc.xml

 -->

Audience Manager使用下列元件來處理資料：

## hadoop {#hadoop}

在[!DNL Audience Manager]中，Hadoop是包含[!DNL Audience Manager]所知道有關使用者的所有資訊的主要資料庫。 例如，當[設定檔快取伺服器](../../reference/system-components/components-data-collection.md)建立包含使用者資料的記錄檔時，會將該資料傳送到Hadoop以供儲存。 其他重要的Hadoop元素包括：

* **Hive：**&#x200B;用於Hadoop的資料倉儲。 Hive會針對儲存在Hadoop中的資料管理特定查詢。

* **HBase：**&#x200B;非常大的Hadoop資料庫。 它會處理和管理傳入和傳出的資料、特徵規則、演演算法模型資訊，並執行許多與儲存資料並將資料移動到不同系統相關的其他功能。

客戶無法直接存取這些系統。 不過，客戶確實會間接與他們合作，因為這些元件會儲存有關其網站訪客的重要資料。

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/)是大型雲端資料庫。 它提供許多面板圖形及其相關文字方塊的資料，顯示圖形中每個專案的%變更。 如果您使用[!DNL Audience Manager]並檢視儀表板報告，您正在與[!UICONTROL Snowflake]提供的資料互動。



![](assets/dashboardreport.png)

這絕不是完整的清單，但某些由[!UICONTROL Snowflake]負責的一般儀表板報告包括：

* [每日特徵變化報表](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* 所有重疊報表（如需每個重疊報表的相關資訊，請參閱[互動報表](/help/using/reporting/dynamic-reports/dynamic-reports.md)區段）。
* [未使用的訊號報表](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR是來自Apache的開放原始碼資料庫和伺服器系統。 它針對我們的大型資料集提供強大而快速的搜尋功能。 作為[!DNL Audience Manager]客戶，您可在建立區段時看到SOLR的實際運作。 它提供資料給[!UICONTROL Estimated Historic Segment Size]報表。 SOLR的速度非常適用於此角色。 例如，SOLR可在您建立規則並將新特徵新增至區段時更新歷史大小資料。



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager]使用[Tableau](https://www.tableausoftware.com/)在[互動式報表](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)與[Audience Optimization式報表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)中顯示資料。 互動式報表會顯示特徵和區段的效能和重疊資料。 它們不會使用以欄和列排列的數字，而是會使用不同的形狀、顏色和大小傳回資料。 此外，您可以選擇個別或資料點群組，並深入研究報告結果以取得更多詳細資訊。 這些視覺化技巧和報表互動有助於讓大量數值資料更易於理解。



![](assets/advertiser_analytics.png)
