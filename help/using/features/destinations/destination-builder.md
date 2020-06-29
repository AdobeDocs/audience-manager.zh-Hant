---
description: 「目標產生器」可讓您建立以Cookie為基礎的或DNL URL目標。 您無法使用「目標產生器」建立伺服器對伺服器(S2S)目標，但您可以管理其區段對應。 請連絡您的顧問以設定S2S目標。 「目標產生器」位於「對象資料>目標」中。
seo-description: 「目標產生器」可讓您建立以Cookie為基礎的或DNL URL目標。 您無法使用「目標產生器」建立伺服器對伺服器(S2S)目標，但您可以管理其區段對應。 請連絡您的顧問以設定S2S目標。 「目標產生器」位於「對象資料>目標」中。
seo-title: 目的地產生器
solution: Audience Manager
title: 目的地產生器
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 4%

---


# 目的地產生器 {#destination-builder}

[!UICONTROL Destination Builder] 可讓您建立Cookie或目 [!DNL URL] 標。 您不能使用建立伺服器對伺服器([!DNL S2S])目的地 [!UICONTROL Destination Builder]，但可以管理其區段對應。 請連絡您的顧問以設定 [!DNL S2S] 目的地。 [!UICONTROL Destination Builder] 的子菜單 **[!UICONTROL Audience Data > Destinations]**。

## 目標產生器設定 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 包含下列章節和設定：

| [!UICONTROL Destination Builder] 區域 | 用途 |
|--- |--- |
| 基本資訊 | 用來命名目標、加以說明，並選取目標類型([!DNL URL] 或 [!DNL cookie])和平台(所有、 [!DNL Android]瀏覽器或 [!DNL iOS])。 |
| 設定 | 包含下列控制項： <br/><ul><li>將關鍵值資料傳入目 [!DNL URL] 標。 您可以以個別或序列化的金鑰值配對傳送資料。 如需詳細資訊，請 [參閱「目標序列化](../../features/destinations/key-value-pairs.md#destination-serialized) 」 [和「標準與序號金鑰值配對」](../../features/destinations/key-value-pairs.md)。 </li><li>Cookie目標的元素，例如Cookie名稱、網域、大小、到期間隔、資料格式等。</li></ul> |
| 區段對應 | 可讓您: <br/><ul><li>搜尋、新增及管理與所有目標類型相關聯的區段。 </li><li>設定個別區段的傳送優先順序(僅 [!DNL cookie]適用於基於區段)。</li></ul> |

## 資料傳送方法 {#data-delivery-methods}

透過字串傳入資訊至目的地、寫入至瀏 [!DNL URL] 覽器或透過離線伺服器 [!DNL cookie]到伺服器的資料傳輸，將資訊傳送至目的地。

* [!DNL URL] 以及以Cookie為基礎的目的地在使用者對頁面採取動作時同步傳送資料。
* 伺服器對伺服器的資料傳輸是非同步的，而且在使用者離開頁面後可能會發生很長時間。 您選擇的傳送類型取決於您的業務需求，以及特定資料合作夥伴想要或能夠接收資料的方式。

如需 [詳細資訊，請參閱如何選擇目標類型](../../features/destinations/destinations.md) 。