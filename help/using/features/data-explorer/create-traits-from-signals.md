---
description: 從所有訊號中建立新特徵，包括已在特徵中使用的特徵，並擷取在特徵建立之後符合資格的未來受眾。
seo-description: 從所有訊號中建立新特徵，包括已在特徵中使用的特徵，並擷取在特徵建立之後符合資格的未來受眾。
seo-title: 從訊號建立特徵
title: 從訊號建立特徵
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# 從訊號建立特徵

從所有訊號中建立新特徵，包括已在特徵中使用的特徵，並擷取在特徵建立之後符合資格的未來受眾。觀看影片以進行快速展示或閱讀詳細資訊：

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12&captions=chi_hant)

## Create Traits from Signal Dashboard {#create-traits-from-signal-dashboard}

The [!UICONTROL Signal Dashboard] allows you to create new traits from the [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals], and your saved searches.

當您建立新特徵時，特徵類型會根據訊號類型進行預先設定：

* **[!UICONTROL Rule-based]** 即時訊號、可操作記錄檔和 [!DNL Adobe Analytics] 訊號的特性；

* **[!UICONTROL Onboarded]** 已登錄訊號的特徵。

To create new traits from the **[!UICONTROL Signal Dashboard]**, identify the signal that you want to use in the trait, then click the corresponding **[!UICONTROL Create Rule-Based Trait]** or **[!UICONTROL Create Onboarded Trait]** link.

![](assets/signals-create-trait.png)

You'll be redirected to the **[Trait Builder](../../features/traits/about-trait-builder.md)** to create your new trait(s).

## Create Traits from Signal Search {#create-traits-from-signal-search}

Create traits based on used or unused signals that are not shown in the [!UICONTROL Signal Dashboard].

搜尋特定訊號，並根據結果建立規則或已登錄的特性。以下是如何做到這一點：

1. Go to **[!UICONTROL Audience Data > Signals > Search]** and run a search based on the key-value pairs that you are looking for, or click **[!UICONTROL Search]** without entering any key-value pair to display all results.
2. 在結果清單中識別您要使用的訊號。
   * To create a trait from one signal, click the corresponding **[!UICONTROL Create Rule-Based Trait]** or **[!UICONTROL Create Onboarded Trait]** link.
   * To create a trait from multiple signals, click the corresponding check box of each signal, then click **[!UICONTROL Create Trait from Multiple Signals]**.
   >[!NOTE]
   >您只能從相同類型的訊號建立特徵。您無法根據即時訊號和已登錄的信號來建立特徵。
   >
   > ![](assets/signals-create-trait-search.png)
   >您也可以從使用的訊號建立特徵。Signals that are already used in traits have the number of traits displayed in the **[!UICONTROL Included in Traits]** column. 按一下箭頭以查看包含訊號的特徵。
   >
   >![](assets/signals-used-traits.png)

3. Use the **[Trait Builder](../../features/traits/about-trait-builder.md)** to create your new traits.
