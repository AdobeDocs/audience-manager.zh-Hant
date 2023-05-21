---
description: 從所有信號中創造新特徵，包括那些已經用於特徵的信號，並捕獲在特徵創造後合格的未來受眾。
seo-description: Create new traits from all signals, including those that are already used in traits, and capture future audiences that qualify after trait creation.
seo-title: Create Traits from Signals
title: 從訊號建立特徵
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 2%

---

# 從訊號建立特徵

從所有信號中創造新特徵，包括那些已經用於特徵的信號，並捕獲在特徵創造後合格的未來受眾。 觀看視頻以快速演示或閱讀以獲取詳細資訊：

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## 從信號儀表板建立特徵 {#create-traits-from-signal-dashboard}

的 [!UICONTROL Signal Dashboard] 允許您通過 [!UICONTROL Top Unused Signals]。 [!UICONTROL New Unused Signals]，以及您保存的搜索。

建立新特徵時，特徵類型是基於信號類型預先設定的：

* **[!UICONTROL Rule-based]** 即時信號、可操作日誌檔案和 [!DNL Adobe Analytics] 信號；

* **[!UICONTROL Onboarded]** 寄生信號的特徵。

從 **[!UICONTROL Signal Dashboard]**，標識要在特徵中使用的信號，然後按一下 **[!UICONTROL Create Rule-Based Trait]** 或 **[!UICONTROL Create Onboarded Trait]** 的子菜單。

![](assets/signals-create-trait.png)

您將被重定向到 **[特性生成器](../../features/traits/about-trait-builder.md)** 來創造你的新特徵。

## 通過信號搜索建立特徵 {#create-traits-from-signal-search}

根據未在中顯示的已用或未使用信號建立特徵 [!UICONTROL Signal Dashboard]。

搜索特定信號，並基於結果建立基於規則或連接的特徵。 下面是如何做到的：

1. 轉到 **[!UICONTROL Audience Data > Signals > Search]** 並根據您要查找的鍵值對運行搜索，或者按一下 **[!UICONTROL Search]** 不輸入任何鍵值對來顯示所有結果。
2. 在結果清單中確定要在特性中使用的信號。
   * 要從一個信號建立特徵，請按一下相應的 **[!UICONTROL Create Rule-Based Trait]** 或 **[!UICONTROL Create Onboarded Trait]** 的子菜單。
   * 要從多個信號中建立特徵，請按一下每個信號的相應複選框，然後按一下 **[!UICONTROL Create Trait from Multiple Signals]**。

   >[!NOTE]
   >只能從同一類型的信號中建立特徵。 你不能根據即時信號和掛接信號的組合來創造一個特性。
   >
   > ![](assets/signals-create-trait-search.png)
   >你也可以從使用的信號中創造特徵。 已在特徵中使用的信號具有在中顯示的特徵數 **[!UICONTROL Included in Traits]** 的雙曲餘切值。 按一下箭頭查看包含該信號的特徵。
   >
   >![](assets/signals-used-traits.png)

3. 使用 **[特性生成器](../../features/traits/about-trait-builder.md)** 來創造你的新特徵。
