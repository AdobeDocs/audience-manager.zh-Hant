---
description: 資料處理元件包括Hadoop、Snowflake、SOLR和Tableau。
seo-description: 資料處理元件包括Hadoop、Snowflake、SOLR和Tableau。
seo-title: 資料處理元件
solution: Audience Manager
title: 資料處理元件
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: 系統元件
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 4%

---

# 資料處理元件{#data-processing-components}

資料處理元件包括Hadoop、Snowflake、SOLR和Tableau。

<!-- 

c_comproc.xml

 -->

Audience Manager使用下列元件來處理資料：

## Hadoop {#hadoop}

在[!DNL Audience Manager]中，Hadoop是包含[!DNL Audience Manager]所知用戶資訊的主資料庫。 例如，當[設定檔快取伺服器](../../reference/system-components/components-data-collection.md)建立包含使用者相關資料的記錄檔時，會將該資料傳送至Hadoop以供儲存。 其他重要Hadoop元素包括：

* **配置單元：** 用於Hadoop的資料倉庫。配置單元管理對儲存在Hadoop中的資料的臨機查詢。

* **HBase:** 一個非常大的Hadoop資料庫。它會處理及管理傳入和傳出的資料、特徵規則、演算法模型資訊，並執行許多其他與儲存和移動資料至不同系統相關的功能。

客戶無法直接存取這些系統。 不過，由於這些元件會儲存有關其網站訪客的重要資料，因此客戶確實會間接與他們合作。

## Snowflake {#snowflake}

[](https://www.snowflake.net/) Snowflake是一個龐大的雲端資料庫。它會提供資料給許多控制面板圖形及其相關文字方塊，以顯示圖形中每個項目的變更%。 如果您使用[!DNL Audience Manager]並查看控制面板報表，表示您正在與[!UICONTROL Snowflake]提供的資料互動。



![](assets/dashboardreport.png)

這絕非完整清單，但有些[!UICONTROL Snowflake]負責的常見控制面板報表包括：

* [每日特徵變化報表](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* 所有重疊報表（如需每個重疊報表的相關資訊，請參閱[互動式報表](/help/using/reporting/dynamic-reports/dynamic-reports.md)區段）。
* [未使用的訊號報表](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR是Apache提供的開放原始碼資料庫和伺服器系統。 它提供強大且快速的搜尋功能，可覆蓋大型資料集。 身為[!DNL Audience Manager]客戶，您在建立區段時可以看到SOLR的作用。 它提供資料給[!UICONTROL Estimated Historic Segment Size]報表。 SOLR因其速度而是該角色的理想之選。 例如，SOLR可在您建立規則時更新歷史大小資料，並將新特徵新增至區段。



![](assets/audsize.png)

## 塔布洛 {#tableau}

[!DNL Audience Manager] 使 [](https://www.tableausoftware.com/) 用互動式報表和 [Audience Optimization](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 報表中的 [表格自動顯示資料](../../reporting/audience-optimization-reports/audience-optimization-reports.md)。互動式報表會顯示特徵和區段的效能和重疊資料。 它們不會使用以欄和列排列的數字，而是會以不同的形狀、顏色和大小傳回資料。 此外，您可以選擇個別資料點或資料點群組，並深入鑽研報表結果以取得詳細資訊。 這些視覺效果技術和報表互動功能有助於輕鬆了解大量數值資料。



![](assets/advertiser_analytics.png)
