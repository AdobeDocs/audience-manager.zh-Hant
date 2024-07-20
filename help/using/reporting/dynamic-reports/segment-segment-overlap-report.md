---
description: 傳回區段之間共用多少不重複使用者的資料。
seo-description: Returns data on how many unique users are shared between your segments.
seo-title: Segment-to-Segment Overlap Report
solution: Audience Manager
title: 區段對區段重疊報表
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Overlap Reports
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 6%

---

# 區段對區段重疊報表{#segment-to-segment-overlap-report}

傳回區段之間共用多少不重複使用者的資料。

>[!NOTE]
>
>Audience Manager中的重疊報表遵循RBAC原則。 您只能根據您所屬的[RBAC使用者群組](/help/using/features/administration/administration-overview.md)，從您有權存取的資料來源檢視區段。

<!-- 

c_segment_segment_overlap.xml

 -->

## 概述

[!UICONTROL Segment-to-Segment Overlap]報告可協助您：

* 視您的需求識別高重疊或低重疊的區段。 重疊程度高的特徵可為您提供目標受眾，但獨特訪客較少。 重疊程度低的特徵對於觸及較大的不重複訪客集很有幫助。
* 找出非預期的重疊，然後使用該資訊來建立新的高效能區段。

## 範例報告

下圖提供[!UICONTROL Segment-to-Segment Overlap]報表的整體概觀。

>[!NOTE]
>
>[!UICONTROL Segment-to-Segment Overlap]報表將相同區段與其本身進行比較時，會傳回空白欄位。

![](assets/segment-to-segment-overlap.png)

## 深入研究個別資料點

選取個別點，以在快顯視窗中檢視資料詳細資訊。 您的點按動作會自動更新報表中顯示的資料。

## 定義的區段對區段重疊資料Pop欄位 {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

[!UICONTROL Segment-to-Segment Overlap]報表的快顯視窗包含下列量度。 請注意，表格中的不重複量度代表您的&#x200B;*即時使用者*。

| 量度 | 說明 |
|---|---|
| **[!UICONTROL Base Segment ID]** | 顯示在報表結果中的區段的不重複數值ID。 顯示為區段的列ID。 |
| **[!UICONTROL Base Segment Name]** | 顯示在報表結果列中的區段名稱。 |
| **[!UICONTROL Overlapping Segment ID]** | 您在執行報表時選取之區段的唯一數值ID。 顯示為區段的欄ID。 |
| **[!UICONTROL Overlapping Segment Name]** | 執行報表時選取的區段名稱。 顯示在報告結果欄中。 |
| **[!UICONTROL Base Segment Uniques]** | 基礎區段中的不重複訪客數量。 |
| **[!UICONTROL Base Segment Uniques]** | 重疊區段中的不重複訪客數量。 |
| **[!UICONTROL Overlapping Uniques]** | 在比較的區段之間共用的不重複訪客數量。 |
| **[!UICONTROL Overlap %]** | 若要取得重疊%，Audience Manager會使用下列公式：「重疊唯一值」/（基本區段唯一值+重疊區段唯一值 — 重疊唯一值） |



>[!MORELIKETHIS]
>
>* [使用資料滑桿篩選報表結果](../../reporting/dynamic-reports/data-sliders.md)
>* [互動式報表中使用的形狀、顏色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [報告圖示和工具說明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重疊報表：更新排程和最小區段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [所選Audience Manager報表中的資料取樣和錯誤率……](../../reporting/report-sampling.md)
>* [重疊報表的 CSV 檔案](../../reporting/dynamic-reports/overlap-csv-files.md)
