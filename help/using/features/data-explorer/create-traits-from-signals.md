---
description: 從所有訊號（包括已在特徵中使用的訊號）建立新特徵，並擷取建立特徵後符合資格的未來對象。
seo-description: Create new traits from all signals, including those that are already used in traits, and capture future audiences that qualify after trait creation.
seo-title: Create Traits from Signals
title: 從訊號建立特徵
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# 從訊號建立特徵

從所有訊號（包括已在特徵中使用的訊號）建立新特徵，並擷取建立特徵後符合資格的未來對象。 觀看影片以快速展示，或閱讀詳細資訊：

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## 從Signal儀表板建立特徵 {#create-traits-from-signal-dashboard}

[!UICONTROL Signal Dashboard]可讓您從[!UICONTROL Top Unused Signals]、[!UICONTROL New Unused Signals]及您儲存的搜尋建立新特徵。

建立新特徵時，會根據訊號型別預先設定特徵型別：

* 即時訊號、可操作的記錄檔和&#x200B;**[!UICONTROL Rule-based]**&#x200B;訊號的[!DNL Adobe Analytics]特徵；

* 已上線訊號的&#x200B;**[!UICONTROL Onboarded]**&#x200B;特徵。

若要從&#x200B;**[!UICONTROL Signal Dashboard]**&#x200B;建立新特徵，請識別您要在特徵中使用的訊號，然後按一下對應的&#x200B;**[!UICONTROL Create Rule-Based Trait]**&#x200B;或&#x200B;**[!UICONTROL Create Onboarded Trait]**&#x200B;連結。

![](assets/signals-create-trait.png)

系統會將您重新導向至&#x200B;**[特徵產生器](../../features/traits/about-trait-builder.md)**，以建立您的新特徵。

## 從訊號搜尋建立特徵 {#create-traits-from-signal-search}

根據[!UICONTROL Signal Dashboard]中未顯示的已使用或未使用訊號建立特徵。

搜尋特定訊號，並根據結果建立規則型或已上線的特徵。 以下是其操作方式：

1. 移至&#x200B;**[!UICONTROL Audience Data > Signals > Search]**&#x200B;並根據您尋找的索引鍵值配對執行搜尋，或按一下&#x200B;**[!UICONTROL Search]**&#x200B;而不輸入任何索引鍵值配對以顯示所有結果。
2. 在結果清單中，識別您要在特徵中使用的訊號。
   * 若要從單一訊號建立特徵，請按一下對應的&#x200B;**[!UICONTROL Create Rule-Based Trait]**&#x200B;或&#x200B;**[!UICONTROL Create Onboarded Trait]**&#x200B;連結。
   * 若要從多個訊號建立特徵，請按一下每個訊號對應的核取方塊，然後按一下&#x200B;**[!UICONTROL Create Trait from Multiple Signals]**。

   >[!NOTE]
   >您只能從相同型別的訊號建立特徵。 您無法根據即時訊號和已上線的訊號的組合來建立特徵。
   >
   > ![](assets/signals-create-trait-search.png)
   >您也可以從已使用的訊號建立特徵。 已用於特徵的訊號具有顯示在&#x200B;**[!UICONTROL Included in Traits]**&#x200B;欄中的特徵數。 按一下箭頭可檢視包含訊號的特徵。
   >
   >![](assets/signals-used-traits.png)

3. 使用&#x200B;**[特徵產生器](../../features/traits/about-trait-builder.md)**&#x200B;建立您的新特徵。
