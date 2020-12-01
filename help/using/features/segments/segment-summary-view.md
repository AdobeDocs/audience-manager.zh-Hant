---
description: 區段摘要頁面會顯示詳細資訊，例如名稱、區段中的特徵、規則、效能資料及目標對應資訊。
seo-description: 區段摘要頁面會顯示詳細資訊，例如名稱、區段中的特徵、規則、效能資料及目標對應資訊。
seo-title: 「段詳細資料」頁
solution: Audience Manager
title: 「段詳細資料」頁
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---


# 區段詳細資料頁面{#segment-summary-view}

個別區段的詳細資料頁面提供區段詳細資料的概述，例如區段名稱、ID、效能度量、定義區段的規則以及目標映射。 若要檢視這些詳細資訊，請前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**，然後按一下您要使用的區段名稱。

## 區段管理工具{#segment-management-tools}

區段詳細資料頁面頂端會代管可用於管理區段的工具：

1. **[!UICONTROL Add New]**:使用此選項可啟動並 [!UICONTROL Segment Builder] 建立新區段。
2. **[!UICONTROL Edit]**:使用此選項可更改當前段的配置。
3. **[!UICONTROL Duplicate]**:使用此選項可建立目前區段的復本。
4. **[!UICONTROL Delete]**:使用這個選項可從您的Audience Manager帳戶移除目前的區段。
5. **[!UICONTROL Marketplace Recommendations]**:使用這個選項，從您未訂閱的資料饋送中，尋找與您所 [!UICONTROL Audience Marketplace] 檢視的類似區段。請參閱[資料購買者的觀眾市場](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)，瞭解如何導覽市場並尋找類似區段。

![基本區段資訊](assets/basic-segment-information.png)

## 區段資訊{#basics}

在區段管理工具下方，您可以找到下列區段資訊：

1. **[!UICONTROL Basic Information]：顯** 示建立區段時指定的必要和選用詳細資訊。請參閱[區段產生器](segment-builder.md)以取得這些欄位的詳細概觀。
2. **[!UICONTROL Segment Graph]:** 以圖形方式顯示固定1、7、14、30、60和90天間隔的效能資料。我們會在[個別文章](../../features/segments/segment-builder-data.md)中說明區段人口數。

   ![區段圖](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:** 報表會計算連結至符合區段資格之裝置的跨裝置ID和／或外部裝置圖形ID的數目，以顯示符合區段資格的人數或家庭數目(如所示 [!UICONTROL Total Segment Population])。此報表中顯示的跨裝置ID和外部裝置圖形ID可用來合併描述檔與區段所使用的描述檔合併規則。 只有當您在區段使用的描述檔合併規則中選取跨裝置資料來源或外部裝置圖表時，才會顯示此報表。

   ![區段圖](assets/segment-type.png)

   >[!NOTE]
   >
   >如果跨裝置ID符合區段的資格，Audience Manager只會顯示[!UICONTROL Identity Type Breakdown]報表。

   觀看以下影片以取得[!UICONTROL Identity Type Breakdown]的概觀。
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]：列** 出區段中的特徵以及資格規則。
5. **[!UICONTROL Destination Mappings]：列** 出區段的目標映射。
6. **[!UICONTROL Management Tools]:** 可讓您建立、編輯、仿製和刪除區段的控制項。