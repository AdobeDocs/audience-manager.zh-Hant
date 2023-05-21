---
description: 返回有關段之間共用的唯一用戶數的資料。
seo-description: Returns data on how many unique users are shared between your segments.
seo-title: Segment-to-Segment Overlap Report
solution: Audience Manager
title: 區段至區段重疊報表
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Overlap Reports
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 10%

---

# 區段至區段重疊報表{#segment-to-segment-overlap-report}

返回有關段之間共用的唯一用戶數的資料。

>[!NOTE]
>
>Audience Manager中的Overlap報告遵循RBAC原則。 您只能從資料源中查看您基於 [RBAC用戶組](/help/using/features/administration/administration-overview.md) 屬於你。

<!-- 

c_segment_segment_overlap.xml

 -->

## 概述

的 [!UICONTROL Segment-to-Segment Overlap] 報告可幫助您：

* 根據您的需要確定重疊程度高或低的段。 具有高度重疊的特性可為您提供目標受眾，但獨特訪問者較少。 具有低重疊的特徵可用於訪問更大、唯一的訪問者集。
* 查找意外的重疊，並使用該資訊構建新的高效能資料段。

## 示例報告

下圖提供了對 [!UICONTROL Segment-to-Segment Overlap] 報告。

>[!NOTE]
>
>的 [!UICONTROL Segment-to-Segment Overlap] report在將同一段與自身進行比較時返回空欄位。

![](assets/segment-to-segment-overlap.png)

## 細化單個資料點

選擇單個點以在彈出窗口中查看資料詳細資訊。 您的按一下操作會自動更新報告中顯示的資料。

## 段到段重疊資料彈出欄位已定義 {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

的彈出窗口 [!UICONTROL Segment-to-Segment Overlap] 報告包含以下度量。 請注意，表中的單位度量表示 *即時用戶*。

| 量度 | 說明 |
|---|---|
| **[!UICONTROL Base Segment ID]** | 報表結果中顯示的段的唯一數字ID。 顯示為段的行ID。 |
| **[!UICONTROL Base Segment Name]** | 顯示在報告結果行中的段的名稱。 |
| **[!UICONTROL Overlapping Segment ID]** | 運行報表時所選段的唯一數字ID。 顯示為段的列ID。 |
| **[!UICONTROL Overlapping Segment Name]** | 運行報表時所選段的名稱。 顯示在報告結果列中。 |
| **[!UICONTROL Base Segment Uniques]** | 基本段中的唯一訪問者數。 |
| **[!UICONTROL Base Segment Uniques]** | 重疊段中的唯一訪問者數。 |
| **[!UICONTROL Overlapping Uniques]** | 在比較的段之間共用的唯一訪問者數。 |
| **[!UICONTROL Overlap %]** | 要獲取重疊%,Audience Manager使用以下公式：重疊單位/（基段單位+重疊段單位 — 重疊單位） |



>[!MORELIKETHIS]
>
>* [使用資料滑桿篩選報表結果](../../reporting/dynamic-reports/data-sliders.md)
>* [Interactive Reports中使用的形狀、顏色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [報告表徵圖和說明的工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重疊報表：更新排程和最小區段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [所選 Audience Manager 報表中的資料取樣和錯誤率...](../../reporting/report-sampling.md)
>* [重疊報表的 CSV 檔案](../../reporting/dynamic-reports/overlap-csv-files.md)

