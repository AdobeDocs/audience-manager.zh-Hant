---
description: 目的地產生器可讓您建立Cookie型或DNL URL目的地。 您無法使用Destination Builder建立伺服器對伺服器(S2S)目的地，但您可以管理其區段對應。 請聯絡您的顧問以設定S2S目的地。 目的地產生器位在對象資料>目的地中。
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: 目的地產生器
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# 目的地產生器 {#destination-builder}

[!UICONTROL Destination Builder]可讓您建立Cookie型或[!DNL URL]目的地。 您無法建立具有[!DNL S2S]的伺服器對伺服器([!UICONTROL Destination Builder])目的地，但您可以管理其區段對應。 請聯絡您的顧問以設定[!DNL S2S]目的地。 [!UICONTROL Destination Builder]位於&#x200B;**[!UICONTROL Audience Data > Destinations]**。

## 目的地產生器設定 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder]包含下列區段和設定：

| [!UICONTROL Destination Builder]節 | 用途 |
|--- |--- |
| 基本資訊 | 用來命名目的地、描述目的地，以及選取目的地型別（[!DNL URL]或[!DNL cookie]）和平台（全部、[!DNL Android]、瀏覽器或[!DNL iOS]）。 |
| 設定 | 包含<br/>的控制項<ul><li>傳遞機碼值資料至[!DNL URL]目的地。 您可以以個別或序列化索引鍵值配對的形式傳送資料。 如需詳細資訊，請參閱[目的地序列化](../../features/destinations/key-value-pairs.md#destination-serialized)和[標準和序列索引鍵值配對](../../features/destinations/key-value-pairs.md)。 </li><li>Cookie目的地的元素，例如Cookie名稱、網域、大小、過期時間間隔、資料格式等。</li></ul> |
| 區段對應 | 可讓您： <br/><ul><li>搜尋、新增及管理與所有目的地型別相關聯的區段。 </li><li>設定個別區段的傳遞優先順序（僅限以[!DNL cookie]為基礎的區段）。</li></ul> |

## 資料傳送方法 {#data-delivery-methods}

將資訊透過[!DNL URL]字串傳入、寫入瀏覽器[!DNL cookie]或透過離線伺服器對伺服器資料傳輸，以傳送資訊至目的地。

* 當使用者在頁面上執行動作時，[!DNL URL]和Cookie型目的地會同步傳輸資料。
* 伺服器對伺服器的資料傳輸為非同步傳輸，可在使用者離開頁面很久後發生。 您選取的傳送型別取決於您的業務需求，以及特定資料合作夥伴想要或可以接收資料的方式。

如需詳細資訊，請參閱[如何選擇目的地型別](../../features/destinations/destinations.md)。
