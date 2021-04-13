---
description: 傳回區段間共用多少獨特使用者的資料。
seo-description: 傳回區段間共用多少獨特使用者的資料。
seo-title: 區段至區段重疊報表
solution: Audience Manager
title: 區段至區段重疊報表
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: 重疊報表
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 11%

---

# 區段至區段重疊報表{#segment-to-segment-overlap-report}

傳回區段間共用多少獨特使用者的資料。

>[!NOTE]
>
>Audience Manager中的重疊報告遵循RBAC原則。 您只能根據您所屬的[RBAC使用者群組](/help/using/features/administration/administration-overview.md)，從您有權存取的資料來源看到區段。

<!-- 

c_segment_segment_overlap.xml

 -->

## 概述

[!UICONTROL Segment-to-Segment Overlap]報表可協助您：

* 根據您的需求，識別高重疊或低重疊的區段。 具有高度重疊的特性可讓您鎖定目標受眾，但獨特訪客較少。 重疊率低的特徵有助於觸及更大的獨特訪客集。
* 尋找未預期的重疊，並使用該資訊建立新的高效能區段。

## 範例報表

下圖提供[!UICONTROL Segment-to-Segment Overlap]報表的高階概述。

>[!NOTE]
>
>當[!UICONTROL Segment-to-Segment Overlap]報表將相同區段與自身比較時，會傳回空白欄位。

![](assets/segment-to-segment-overlap.png)

## 深入探究個別資料點

選取個別點，以在快顯視窗中檢視資料詳細資訊。 您的點按動作會自動更新顯示在報表中的資料。

## 區段對區段重疊資料快顯欄位已定義{#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

[!UICONTROL Segment-to-Segment Overlap]報表的快顯功能表包含下列度量。 請注意，表格中的獨特值度量代表您的&#x200B;*即時使用者*。

| 量度 | 說明 |
|---|---|
| **[!UICONTROL Base Segment ID]** | 顯示在報表結果中之區段的唯一數值ID。 顯示為區段的列ID。 |
| **[!UICONTROL Base Segment Name]** | 顯示在報表結果列中的區段名稱。 |
| **[!UICONTROL Overlapping Segment ID]** | 執行報表時，您所選取區段的唯一數值ID。 顯示為區段的欄ID。 |
| **[!UICONTROL Overlapping Segment Name]** | 執行報表時所選區段的名稱。 顯示在報告結果列中。 |
| **[!UICONTROL Base Segment Uniques]** | 基本區段中的獨特訪客數。 |
| **[!UICONTROL Base Segment Uniques]** | 重疊區段中的獨特訪客數。 |
| **[!UICONTROL Overlapping Uniques]** | 比較區段之間共用的獨特訪客數。 |
| **[!UICONTROL Overlap %]** | 要獲得重疊%,Audience Manager使用以下公式：重疊唯一值/（基本段唯一值+重疊段唯一值——重疊唯一值） |



>[!MORELIKETHIS]
>
>* [使用資料滑桿篩選報表結果](../../reporting/dynamic-reports/data-sliders.md)
>* [互動式報表中使用的形狀、顏色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [說明的報表圖示和工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重疊報表：更新排程和最小區段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [所選 Audience Manager 報表中的資料取樣和錯誤率...](../../reporting/report-sampling.md)
>* [重疊報表的 CSV 檔案](../../reporting/dynamic-reports/overlap-csv-files.md)

