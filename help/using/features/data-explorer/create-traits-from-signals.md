---
description: 從所有訊號建立新特徵，包括已用於特徵的訊號，並擷取在建立特徵後符合資格的未來對象。
seo-description: 從所有訊號建立新特徵，包括已用於特徵的訊號，並擷取在建立特徵後符合資格的未來對象。
seo-title: 從訊號建立特徵
title: 從訊號建立特徵
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---

# 從訊號建立特徵

從所有訊號建立新特徵，包括已用於特徵的訊號，並擷取在建立特徵後符合資格的未來對象。 觀看影片以快速示範或閱讀以取得詳細資訊：

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## 從訊號控制面板{#create-traits-from-signal-dashboard}建立特徵

[!UICONTROL Signal Dashboard]可讓您從[!UICONTROL Top Unused Signals]、[!UICONTROL New Unused Signals]和您儲存的搜尋建立新特徵。

建立新特徵時，特徵類型會根據訊號類型預先設定：

* **[!UICONTROL Rule-based]** 即時訊號、可操作的記錄檔及訊 [!DNL Adobe Analytics] 號；

* **[!UICONTROL Onboarded]** 已上線訊號的特徵。

若要從&#x200B;**[!UICONTROL Signal Dashboard]**&#x200B;建立新特徵，請識別您要用於特徵中的訊號，然後按一下對應的&#x200B;**[!UICONTROL Create Rule-Based Trait]**&#x200B;或&#x200B;**[!UICONTROL Create Onboarded Trait]**&#x200B;連結。

![](assets/signals-create-trait.png)

系統會將您重新導向至&#x200B;**[特徵產生器](../../features/traits/about-trait-builder.md)**，以建立您的新特徵。

## 從訊號搜尋{#create-traits-from-signal-search}建立特徵

根據未顯示於[!UICONTROL Signal Dashboard]的已使用或未使用訊號建立特徵。

搜尋特定訊號，並根據結果建立規則型或已上線的特徵。 以下是操作方法：

1. 前往&#x200B;**[!UICONTROL Audience Data > Signals > Search]**&#x200B;並根據要查找的鍵值對運行搜索，或按一下&#x200B;**[!UICONTROL Search]**&#x200B;而不輸入任何鍵值對以顯示所有結果。
2. 在結果清單中識別您要用於特徵中的訊號。
   * 若要從一個訊號建立特徵，請按一下對應的&#x200B;**[!UICONTROL Create Rule-Based Trait]**&#x200B;或&#x200B;**[!UICONTROL Create Onboarded Trait]**&#x200B;連結。
   * 若要從多個訊號建立特徵，請按一下每個訊號的對應核取方塊，然後按一下&#x200B;**[!UICONTROL Create Trait from Multiple Signals]**。

   >[!NOTE]
   >您只能從相同類型的訊號建立特徵。 您無法根據即時訊號和已上線訊號的組合來建立特徵。
   >
   > ![](assets/signals-create-trait-search.png)
   >您也可以從使用的訊號建立特徵。 已用於特徵中的訊號有顯示在&#x200B;**[!UICONTROL Included in Traits]**&#x200B;欄中的特徵數。 按一下箭頭以查看包含訊號的特徵。
   >
   >![](assets/signals-used-traits.png)

3. 使用&#x200B;**[特徵產生器](../../features/traits/about-trait-builder.md)**&#x200B;建立新特徵。
