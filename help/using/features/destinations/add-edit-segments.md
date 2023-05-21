---
description: 資料導出標籤與在資料源上設定的導出控制項一起使用。 「資料導出標籤」阻止您向段添加受限制的特性，並阻止將段資料發送到目標。 可以將多個導出標籤設定為新的或現有的Cookie或URL目標。
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: 新增或編輯伺服器對伺服器目的地的區段
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 7%

---

# 新增或編輯伺服器對伺服器目的地的區段 {#add-edit-segments}

只能添加或編輯伺服器到伺服器的段([!DNL S2S])目標。 無法建立 [!DNL S2S] 目標 [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md)。 與顧問聯繫以設定 [!DNL S2S] 目標。 按照以下說明為 [!DNL S2S] 目標。

<!-- destination-s2s-edit.xml -->

添加或編輯段映射 [!DNL S2S] 目標：

1. 轉到 **[!UICONTROL Audience Data > Destinations]**。 選擇 **整合平台>基於設備** 找到 [!DNL S2S] 要使用的目標。
2. 在 [!UICONTROL Action] 列中，按一下鉛筆表徵圖可編輯目標。
   * 在 **[!UICONTROL Search and Add Segments]** 框中，開始鍵入段的名稱，或按一下 **[!UICONTROL Browse All Segments]** 瀏覽可用段的清單。
   * 按一下 **[!UICONTROL Add Selected Segments]** 找到要使用的段。 添加段將開啟 [!UICONTROL Edit Mapping] 的子菜單。
   * 在 [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**:為 [鍵值對](../../features/destinations/key-value-pairs.md) 此目標使用。
      * **[!UICONTROL Start Date]** 和 **[!UICONTROL End Date]**:選擇目標的開始和結束日期。 如果結束日期為空，則目標將永不過期。
3. 按一下 **[!UICONTROL Save]** 然後按一下 **[!UICONTROL Done]**。
