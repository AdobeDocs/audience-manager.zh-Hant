---
description: 「一般」報表會傳回特徵、區段和目的地的效能資料。
seo-description: Audience Manager中的「一般」報表會傳回特徵、區段和目的地的效能資料。
seo-title: Audience Manager中的一般報表
solution: Audience Manager
title: 一般報告
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# 一般報告{#general-reports}

報表 [!UICONTROL General] 會傳回特徵、區段和目的地的效能資料。

## 概述 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] 使用 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])將使用者群組權限延伸至報 [!UICONTROL General] 表。 使用者在報告中只能看到他們有權檢視的特徵和區段。 [!UICONTROL RBAC] 功能可讓您控制內部團隊可檢視的報表資料。 例如，管理不同廣告商帳戶的代理商可以設定使用者群組權限，讓管理廣告商A帳戶的團隊看不到廣告商B的報告資料。

當您需 [!UICONTROL General] 要時，執行報表：

* 依特徵、區段或目的地檢視效能。
* 以1、7、14、30、60和90天間隔追蹤印象（總計和唯一）。
* 檢視總負載和唯一負載計數。
* 比較特徵和區段效能。
* 識別強或弱的效能特徵和區段、分析需求，或將負載／火力資料與協力廠商報表進行比較。
* 匯出資料（.csv格式）以進一步分析和共用。

下圖提供報表關鍵元素的高階概 [!UICONTROL General] 觀。

![](assets/general_reports.png)

1. 設定以下選項: 

   * **報表類型：** 選取所要的報表類型（特徵、區段或目標）。

   * **日期至：** 指定報表的日期範圍。

2. 依名稱或ID搜尋特徵、區段或目標。
3. 從資料夾清單中，將您要報告的特徵、區段或目標拖放至右 [!UICONTROL Selections] 側的面板。
4. 產生要顯示在可匯出表格中的報表。

## Run a General Report {#run-general-report}

本節說明如何執行報表，以 [!UICONTROL General] 及設定時間和其他效能選項。

<!-- 

t_run_general_report.xml

 -->

1. 在控制面 **[!UICONTROL Analytics]** 板中，按一下 **[!UICONTROL General Reports]**。
1. 從下拉 **[!UICONTROL Report Type]** 式清單中，選取所要的類型：特徵、區段或目標。
1. *條件* ：按一下日期方塊以顯示日曆，然後如果您想要指定非今天的日期，請選取報表的結束日期。
1. 依名稱或ID搜尋特徵、區段或目標。
1. 從資料夾清單中，將您要報告的特徵、區段或目標拖放至右 [!UICONTROL Selections] 側的面板。
1. 按一下 **[!UICONTROL Run Report]**.

   結果會顯示在可匯出的表格中。 按一下欄標題，以遞增或遞減順序排序結果。
1. 選取報表頂端的所需選項按鈕，以依效能( [!UICONTROL Unique Trait Realizations]、 [!UICONTROL Total Trait Realizations]或 [!UICONTROL Total Trait Population])或依時間（1、7、14、30、60或90天範圍）篩選資料。

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 的值 [!UICONTROL Rule-based Traits] 。

1. *可選* ，按一 **[!UICONTROL Export to CSV]**&#x200B;下。 這會匯出 [!UICONTROL Unique Trait Realizations]所有 [!UICONTROL Total Trait Realizations]日期 [!UICONTROL Total Trait Population] 範圍的、和。

## 一般報表結果說明 {#general-reports-explained}

這些數字是直 [!UICONTROL General Reports] 接由我們產生的 [!UICONTROL User Profile Store]。 結果反映產生這些報表 [!DNL Audience Manager] 編號時，後端所包含的使用者人數。

* 這些數字不包含流量過多的訪客ID。 在到達後端系統之前，會先篩選來自機器人的流量。 此外，在後端執行每週清理作業時，會捨棄某些機器人流量。
* 如果您透過UUID的傳入處理將資料加以登入，而這些 [!DNL Audience Manager] ID包含在我們系統中不再作用的使用者，則這些非作用中的 [!DNL Audience Manager] UUID永遠無法到達 [!UICONTROL User Profile Store] 且不會報告。
* [!UICONTROL Total Trait Realizations] 的值 [!UICONTROL Rule-based Traits] 。

## 特徵的一般報告結果 {#general-report-results-traits}

當您執行「一般」報表並選取作為報表類型時，可使 **[!UICONTROL Trait]** 用下列度量：

**獨特特性實現**

此量度代表在所選時間範圍內 [符合特徵的Audience Manager唯一使用者ID(UUID)](../reference/ids-in-aam.md) 。 例如，如果使用者在10/1瀏覽您的首頁三次，您會看到一個獨特特徵實現。

**特徵實現總計**

此量度代表所選時間範圍內特徵所觸發的特徵總數。 例如，如果使用者瀏覽您的首頁，接著導覽至您的技術新聞和體育新聞區段，這些資訊會以三個特徵實現和一個獨特特徵實現的形式出現在「一般報告」中。

**特徵總人口**

此量度代表目前符合特徵的Audience Manager UUID總量。 使用此數字可瞭解您可用於區段和定位的使用者總數。 通常，使用者會在120天內保留某 [個特徵](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)。 例如，今天三次瀏覽您首頁，之後再也不返回的使用者，每天都會以使用者的身分，直到現在120天。 在120天大關時，他們將被從人口中移走。 閱讀我們 [的特徵與區段資格參考](../features/traits/trait-and-segment-qualification-reference.md) ，以取得有關獨特特徵實現與總特徵人口之間的差異的更多範例。

下圖顯示為特徵報表類型執行一般報表的結果。

![](assets/general_reports_metrics.png)

## 區段的一般報表結果 {#general-report-results-segments}

當您執行「一般」報表並選取作為報表類型時，可使 **[!UICONTROL Segment]** 用下列度量：

**即時區段人口**

此量度代表在指定時間範圍內即時檢視的獨特訪客的實際數量，以及Audience Manager在檢視這些訪客時符合區段資格的訪客。

**區段總人口**

此量度代表在您選取的回顧期間內，符合區段條件的Audience Manager UUID總數。 您的1天「區段總人口」代表您最精準的定位使用者群。

>[!NOTE]
>
>選取 **[!UICONTROL Include Destination Mappings]** 可查看已啟用目的地的區段人口劃分。

下圖顯示執行區段報表類型一般報表的結果。

![](assets/general_reports_segment_metrics.png)

## 目標的一般報告結果 {#general-report-results-destinations}

當您執行「一般」報表並選取作為報表類型時，可使 **[!UICONTROL Destination]** 用下列度量：

**即時區段人口**

此量度代表在指定時間範圍內即時檢視的獨特訪客的實際數量，以及Audience Manager在檢視這些訪客時符合區段資格的訪客。

**區段總人口**

此量度代表回顧時段內，已傳送至目的地之區段的Audience Manager UUID總數。

下圖顯示執行「目標」報表類型一般報表的結果。

![](assets/general_reports_destinations.png)
