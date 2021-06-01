---
description: 目的地產生器可讓您建立Cookie型或DNL URL目的地。 您無法使用目的地產生器建立伺服器對伺服器(S2S)目的地，但您可以管理其區段對應。 請連絡您的顧問以設定S2S目的地。 目的地產生器位於「對象資料>目的地」。
seo-description: 目的地產生器可讓您建立Cookie型或DNL URL目的地。 您無法使用目的地產生器建立伺服器對伺服器(S2S)目的地，但您可以管理其區段對應。 請連絡您的顧問以設定S2S目的地。 目的地產生器位於「對象資料>目的地」。
seo-title: 目的地產生器
solution: Audience Manager
title: 目的地產生器
feature: 目的地基本知識
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# 目的地產生器 {#destination-builder}

[!UICONTROL Destination Builder] 可讓您建立Cookie型或目 [!DNL URL] 的地。您無法使用[!UICONTROL Destination Builder]建立伺服器對伺服器([!DNL S2S])目的地，但您可以管理其區段對應。 請連絡您的顧問以設定[!DNL S2S]目的地。 [!UICONTROL Destination Builder] 位於中 **[!UICONTROL Audience Data > Destinations]**。

## 目的地產生器設定{#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 包含下列區段和設定：

| [!UICONTROL Destination Builder] 區域 | 用途 |
|--- |--- |
| 基本資訊 | 用來命名目的地、加以說明，並選取目的地類型（[!DNL URL]或[!DNL cookie]）和平台（所有、[!DNL Android]、瀏覽器或[!DNL iOS]）。 |
| 設定 | 包含下列項目的控制項：<br/><ul><li>將機碼值資料傳遞至[!DNL URL]目的地。 您可以以個別或序列化索引鍵值配對的形式傳送資料。 有關詳細資訊，請參閱[目標序列化](../../features/destinations/key-value-pairs.md#destination-serialized)和[標準和串列鍵值配對](../../features/destinations/key-value-pairs.md)。 </li><li>Cookie目的地的元素，例如Cookie名稱、網域、大小、到期間隔、資料格式等。</li></ul> |
| 區段對應 | 可讓您: <br/><ul><li>搜尋、新增及管理與所有目的地類型相關聯的區段。 </li><li>在個別區段上設定傳送優先順序（僅限[!DNL cookie]型區段）。</li></ul> |

## 資料傳送方法{#data-delivery-methods}

透過[!DNL URL]字串、寫入至瀏覽器[!DNL cookie]或透過離線伺服器對伺服器的資料傳輸，將資訊傳送至目的地。

* [!DNL URL] 當使用者在頁面上執行動作時，和以cookie為基礎的目的地會同步傳輸資料。
* 伺服器對伺服器的資料傳輸是非同步的，並且可能在用戶離開頁面後很久才會發生。 您選取的傳送類型取決於您的業務需求，以及特定資料合作夥伴想要或可以如何接收資料。

如需詳細資訊，請參閱[如何選擇目的地類型](../../features/destinations/destinations.md) 。
