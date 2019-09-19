---
description: 從所有訊號（包括已用於特徵的訊號）建立新特徵，並擷取在建立特徵後符合未來受眾資格的受眾。
seo-description: 從所有訊號（包括已用於特徵的訊號）建立新特徵，並擷取在建立特徵後符合未來受眾資格的受眾。
seo-title: 從訊號建立特徵
title: 從訊號建立特徵
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# 從訊號建立特徵

從所有訊號（包括已用於特徵的訊號）建立新特徵，並擷取在建立特徵後符合未來受眾資格的受眾。 觀看影片以快速展示或閱讀以取得詳細資訊：

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12&captions=chi_hant)

## 從Signal Dashboard建立特徵 {#create-traits-from-signal-dashboard}

它 [!UICONTROL Signal Dashboard] 可讓您從儲存的搜尋和 [!UICONTROL Top Unused Signals]搜 [!UICONTROL New Unused Signals]尋建立新特徵。

當您建立新特徵時，特徵類型會根據訊號類型預先設定：

* **[!UICONTROL Rule-based]** 即時信號、可操作日誌檔案和信號的特 [!DNL Adobe Analytics] 徵；

* **[!UICONTROL Onboarded]** 已登錄信號的特徵。

若要從中建立新特 **[!UICONTROL Signal Dashboard]**&#x200B;徵，請識別您要在特徵中使用的信號，然後按一下對應 **[!UICONTROL Create Rule-Based Trait]** 的或 **[!UICONTROL Create Onboarded Trait]** 連結。

![](assets/signals-create-trait.png)

系統會將您重新導向至「 **[特徵產生器](../../features/traits/about-trait-builder.md)** 」，以建立您的新特徵。

## 從Signal Search建立特徵 {#create-traits-from-signal-search}

根據未在中顯示的已用或未使用信號建立特徵 [!UICONTROL Signal Dashboard]。

搜尋特定訊號並根據結果建立規則型或已登入的特徵。 以下是如何做到的：

1. 前往並 **[!UICONTROL Audience Data > Signals > Search]** 根據您要尋找的索引鍵值配對執行搜尋，或按一下而不輸入任何索引鍵值配 **[!UICONTROL Search]** 對，以顯示所有結果。
2. 在結果清單中識別您要用於特徵的信號。
   * 若要從一個訊號建立特徵，請按一下對應的 **[!UICONTROL Create Rule-Based Trait]** 或連 **[!UICONTROL Create Onboarded Trait]** 結。
   * 若要從多個訊號建立特徵，請按一下每個訊號的對應核取方塊，然後按一下 **[!UICONTROL Create Trait from Multiple Signals]**。
   >[!NOTE]
   >您只能從相同類型的信號建立特徵。 您無法根據即時訊號和已登入訊號的組合來建立特徵。
   >
   > ![](assets/signals-create-trait-search.png)
   >您也可以從使用的信號中建立特徵。 已用於特徵的信號具有列中顯示的特徵數 **[!UICONTROL Included in Traits]** 量。 按一下箭頭，查看包含此訊號的特性。
   >
   >![](assets/signals-used-traits.png)

3. 使用「 **[特徵產生器](../../features/traits/about-trait-builder.md)** 」建立新特徵。
