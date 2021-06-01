---
description: 資料匯出標籤可與您在資料來源上設定的匯出控制項搭配使用。 「資料匯出標籤」無法將限制特徵新增至區段，也無法將區段資料傳送至目的地。 您可以將多個匯出標籤設定為新或現有的Cookie或URL目的地。
seo-description: 資料匯出標籤可與您在資料來源上設定的匯出控制項搭配使用。 「資料匯出標籤」無法將限制特徵新增至區段，也無法將區段資料傳送至目的地。 您可以將多個匯出標籤設定為新或現有的Cookie或URL目的地。
seo-title: 新增或編輯伺服器對伺服器目的地的區段
solution: Audience Manager
title: 新增或編輯伺服器對伺服器目的地的區段
feature: 目的地基本知識
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 8%

---

# 新增或編輯伺服器對伺服器目的地的區段 {#add-edit-segments}

您只能為伺服器對伺服器([!DNL S2S])目的地新增或編輯區段。 無法使用[[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md)建立[!DNL S2S]目標。 請連絡您的顧問以設定[!DNL S2S]目的地。 請依照下列指示，新增或編輯[!DNL S2S]目的地的區段。

<!-- destination-s2s-edit.xml -->

要為[!DNL S2S]目標添加或編輯段映射，請執行以下操作：

1. 前往&#x200B;**[!UICONTROL Audience Data > Destinations]**。 選擇&#x200B;**整合平台>基於設備的**&#x200B;並找到要使用的[!DNL S2S]目標。
2. 在[!UICONTROL Action]欄中，按一下鉛筆圖示以編輯目的地。
   * 在&#x200B;**[!UICONTROL Search and Add Segments]**&#x200B;方塊中，開始輸入區段名稱，或按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;瀏覽可用區段清單。
   * 找到您要使用的區段時，按一下&#x200B;**[!UICONTROL Add Selected Segments]**。 新增區段會開啟[!UICONTROL Edit Mapping]視窗。
   * 在 [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**:為此目的地使 [用的機碼](../../features/destinations/key-value-pairs.md) 值組設定值。
      * **[!UICONTROL Start Date]** 和 **[!UICONTROL End Date]**:選擇目的地的開始和結束日期。如果結束日期空白，目的地永不過期。
3. 按一下&#x200B;**[!UICONTROL Save]**，然後按一下&#x200B;**[!UICONTROL Done]**。
