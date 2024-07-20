---
description: 「資料匯出標籤」可與您在資料來源上設定的「匯出控制項」搭配使用。 資料匯出標籤可防止您將受限制的特徵新增至區段，也防止您將區段資料傳送至目的地。 您可以將多個匯出標籤設定到新的或現有的Cookie或URL目的地。
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: 新增或編輯伺服器對伺服器目的地的區段
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# 新增或編輯伺服器對伺服器目的地的區段 {#add-edit-segments}

您只能新增或編輯伺服器對伺服器([!DNL S2S])目的地的區段。 您無法使用[[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md)建立[!DNL S2S]目的地。 請聯絡您的顧問以設定[!DNL S2S]目的地。 請依照這些指示為[!DNL S2S]目的地新增或編輯區段。

<!-- destination-s2s-edit.xml -->

若要新增或編輯[!DNL S2S]目的地的區段對應：

1. 移至&#x200B;**[!UICONTROL Audience Data > Destinations]**。 選取「**整合平台>以裝置為基礎的**」，並尋找您要使用的[!DNL S2S]目的地。
2. 在[!UICONTROL Action]欄中按一下鉛筆圖示以編輯目的地。
   * 在&#x200B;**[!UICONTROL Search and Add Segments]**&#x200B;方塊中，開始輸入區段名稱，或按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;瀏覽可用區段清單。
   * 當您找到要使用的區段時，請按一下&#x200B;**[!UICONTROL Add Selected Segments]**。 新增區段會開啟[!UICONTROL Edit Mapping]視窗。
   * 在[!UICONTROL Edit Mapping]：
      * **[!UICONTROL Mappings]**：設定此目的地所使用的[機碼值組](../../features/destinations/key-value-pairs.md)的值。
      * **[!UICONTROL Start Date]**&#x200B;和&#x200B;**[!UICONTROL End Date]**：選擇目的地的開始和結束日期。 如果結束日期為空白，目的地永遠不會過期。
3. 按一下&#x200B;**[!UICONTROL Save]**，然後按一下&#x200B;**[!UICONTROL Done]**。
