---
description: 段摘要頁顯示詳細資訊，如名稱、段中的特徵、規則、效能資料和目標映射資訊。
seo-description: The segment summary page displays details such as name, traits in the segment, rules, performance data, and destination mapping information.
seo-title: Segment Details Page
solution: Audience Manager
title: 「段詳細資訊」頁
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: 標識類型分解、標識分解、受眾身份報告、跨設備、跨設備ID、設備ID
feature: Segments
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 0%

---

# 「段詳細資訊」頁 {#segment-summary-view}

單個段的詳細資訊頁提供了段詳細資訊的概覽，如段名稱、ID、效能度量、定義段的規則以及目標映射。 要查看這些詳細資訊，請轉至 **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** 並按一下要使用的段的名稱。

## 段管理工具 {#segment-management-tools}

段詳細資訊頁面頂部承載可用於管理段的工具：

1. **[!UICONTROL Add New]**:使用此選項激活 [!UICONTROL Segment Builder] 建立新段。
2. **[!UICONTROL Edit]**:使用此選項可更改當前段的配置。
3. **[!UICONTROL Duplicate]**:使用此選項可建立當前段的副本。
4. **[!UICONTROL Delete]**:使用此選項可從Audience Manager帳戶中刪除當前段。
5. **[!UICONTROL Marketplace Recommendations]**:使用此選項可查找與您正在查看的段相似的段，從 [!UICONTROL Audience Marketplace] 您未訂閱的資料源。 請參閱 [Audience Marketplace資料購買者](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) 瞭解如何導航市場並查找類似的段。

![基本段資訊](assets/basic-segment-information.png)

## 段資訊 {#basics}

在段管理工具下，您可以找到以下段資訊：

1. **[!UICONTROL Basic Information]:** 顯示建立段時指定的必需和可選詳細資訊。 請參閱 [段生成器](segment-builder.md) 的子菜單。
2. **[!UICONTROL Segment Graph]:** 以圖形方式顯示1、7、14、30、60和90天間隔的效能資料。 我們解釋 [單獨的物品](../../features/segments/segment-builder-data.md)。

   ![段圖](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:** 此報表通過計算連結到符合段條件的設備的跨設備ID和/或外部設備圖形ID的數量，顯示符合段條件的人員或家庭數(由 [!UICONTROL Total Segment Population])。 此報表中顯示的跨設備ID和外部設備圖形ID用於將配置檔案與段使用的配置檔案合併規則合併。 僅當在段使用的配置檔案合併規則中選擇了跨設備資料源或外部設備圖形時，才顯示此報告。

   ![段圖](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager僅顯示 [!UICONTROL Identity Type Breakdown] 報告是否具有符合段的跨設備ID。

   觀看下面的視頻，瞭解 [!UICONTROL Identity Type Breakdown]。
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]:** 列出段中的特徵以及資格規則。
5. **[!UICONTROL Destination Mappings]:** 列出段的目標映射。
6. **[!UICONTROL Management Tools]:** 用於建立、編輯、克隆和刪除段的控制項。
