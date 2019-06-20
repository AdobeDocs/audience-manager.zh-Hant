---
description: 「一般」報表會傳回特徵、區段和目的地上的績效資料。
seo-description: Audience Manager中的「一般」報表會傳回特性、區段和目的地的績效資料。
seo-title: Audience Manager中的一般報表
solution: Audience Manager
title: 一般報表
uuid: csea75a0-969e-4ee3-971a-60b911711e52
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# General Reports{#general-reports}

[!UICONTROL General] 報表會傳回特徵、區段和目的地上的績效資料。

## 概述 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] uses [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) to extend user-group permissions to the [!UICONTROL General] reports.使用者只能在報告中看到具有檢視權限的特性和區段。[!UICONTROL RBAC] 功能可讓您控制可供內部團隊檢視的報告資料。例如，管理不同廣告商帳戶的代理商可以設定使用者群組權限，讓管理廣告商A帳戶的團隊無法看見廣告商B的報表資料。

Run a [!UICONTROL General] report when you need to:

* 依特徵、區段或目的地來檢閱績效。
* 追蹤印象(總計和獨特)1、7、14、30、60、90天和期限間隔。
* 檢閱總計和獨特載入計數。
* 比較特徵和區段績效。
* 識別強大或不良的績效特徵和區段、分析需求，或比較第三方報表的負載/發射資料。
* 匯出資料(. csv格式)以進行進一步分析和共用。

The following illustration provides a high-level overview of key elements in the [!UICONTROL General] report.

![](assets/general_reports.png)

1. 設定以下選項: 

   * **報表類型：** 選取所要的報表類型(特徵、區段或目的地)。

   * **日期透過：** 指定報表的日期範圍。

2. 依名稱或ID搜尋特徵、區段或目的地。
3. From the folder list, drag and drop the traits, segments, or destinations you want to report to the [!UICONTROL Selections] panel on the right side.
4. 產生報表以顯示在可導出表格中。

## Run a General Report {#run-general-report}

This section describes how to run a [!UICONTROL General] report and set time and other performance options.

<!-- 

t_run_general_report.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL General Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: Trait, Segment, or Destination.
1. *條件* 點按日期方塊以顯示日曆，然後如果您想要指定今天以外的日期，請選取報表的結束日期。
1. 依名稱或ID搜尋特徵、區段或目的地。
1. From the folder list, drag and drop the traits, segments, or destinations you want to report to the [!UICONTROL Selections] panel on the right side.
1. Click **[!UICONTROL Run Report]**.

   結果會顯示在可導出的表格中。按一下欄標題，以遞增或遞減順序排序結果。
1. Select the desired option button at the top of the report to filter data by performance ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], or [!UICONTROL Total Trait Population]) or by time (1, 7, 14, 30, 60, 90-day range or lifetime).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 僅供計算。[!UICONTROL Rule-based Traits]

1. *選擇性* 按 **[!UICONTROL Export to CSV]** 一下。This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

## General Reports Results Explained {#general-reports-explained}

The numbers in the [!UICONTROL General Reports] are generated directly from our [!UICONTROL User Profile Store]. The results reflect the number of users that [!DNL Audience Manager] contained in the backend at the time these reporting numbers were generated.

* 這些數字不包含流量過多的訪客ID。在到達後端系統之前，會篩選機器人的流量。此外，當每周清理工作在後端執行時，會捨棄某些機器人流量。
* If you onboard data via inbound processing keyed off the [!DNL Audience Manager] UUID, and these IDs include users that are no longer active in our system, these inactive [!DNL Audience Manager] UUIDs never reach the [!UICONTROL User Profile Store] and are not reported.
* [!UICONTROL Total Trait Realizations] 僅供計算。[!UICONTROL Rule-based Traits]

## General Reports Results for Traits {#general-report-results-traits}

The metrics below are available when you run a General report and select **[!UICONTROL Trait]** as the report type:

**獨特特徵實作**

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. 例如，如果使用者在10/1上瀏覽首頁三次，就會看到一個獨特特徵實現。

**特徵實作總數**

此度量代表特徵在您所選時間範圍內引發的特徵總數。例如，如果使用者瀏覽首頁，然後瀏覽到您的技術新聞和您的體育新聞區段，則在「一般報表」中會顯示為三個整體特徵實作，以及一個獨特特徵實現。

**特徵總人數**

此度量代表目前適用於特徵的Audience Manager UUID總量。使用此數目可瞭解您可用於劃分和定位的使用者總數。Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). 例如，使用者今天瀏覽首頁三次，而不返回之後，則每天都以使用者身分繼續，直到120天後。在120天標記中，將會從人口中移除。Read our [Trait Qualification Reference](../features/traits/trait-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

下圖顯示執行「特徵」報表類型一般報表的結果。

![](assets/general_reports_metrics.png)

## General Reports Results for Segments {#general-report-results-segments}

The metrics below are available when you run a General report and select **[!UICONTROL Segment]** as the report type:

**即時細分人口**

此度量代表指定時間範圍內即時看到的實際訪客數量，以及Audience Manager檢視區段時的合格訪客人數。

**區段總人口數**

此度量代表在您選取的回顧期間內，符合區段資格的Audience Manager UUID總數。您的天「區段總計」代表您最準確的定位使用者群。

>[!NOTE]
>
>Select **[!UICONTROL Include Destination Mappings]** to see a breakdown of segment population for activated destinations.

下圖顯示執行區段報表類型一般報表的結果。

![](assets/general_reports_segment_metrics.png)

## General Reports Results for Destinations {#general-report-results-destinations}

The metrics below are available when you run a General report and select **[!UICONTROL Destination]** as the report type:

**即時細分人口**

此度量代表指定時間範圍內即時看到的實際訪客數量，以及Audience Manager檢視區段時的合格訪客人數。

**區段總人口數**

此度量代表在回顧期間內，屬於一個群體的Audience Manager UUID總數。

下圖顯示執行「目標」報表類型一般報表的結果。

![](assets/general_reports_destinations.png)
