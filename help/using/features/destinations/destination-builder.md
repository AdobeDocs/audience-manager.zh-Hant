---
description: 目標產生器可讓您建立Cookie或DNL URL目的地。您無法使用「目標產生器」建立伺服器對伺服器(S2S)目的地，但您可以管理其區段對應。請連絡您的顧問以設定S2S目的地。「目標產生器」位於「對象資料>目標」中。
seo-description: 目標產生器可讓您建立Cookie或DNL URL目的地。您無法使用「目標產生器」建立伺服器對伺服器(S2S)目的地，但您可以管理其區段對應。請連絡您的顧問以設定S2S目的地。「目標產生器」位於「對象資料>目標」中。
seo-title: 目的地產生器
solution: Audience Manager
title: 目的地產生器
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---


# 目的地產生器 {#destination-builder}

[!UICONTROL Destination Builder] 可讓您建立Cookie或 [!DNL URL] 目的地。您無法建立伺服器對伺服器([!DNL S2S])目的地 [!UICONTROL Destination Builder]，但可以管理其區段對應。請連絡您的顧問以設定 [!DNL S2S] 目的地。[!UICONTROL Destination Builder]**[!UICONTROL Audience Data > Destinations]**&#x200B;位於中。

## 目標產生器設定 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 包含下列區段和設定：

| [!UICONTROL Destination Builder] 區域 | 用途 |
|--- |--- |
| 基本資訊 | 用來命名目的地、加以說明，並選取目的地類型([!DNL URL] 或 [!DNL cookie])，以及平台(全部、 [!DNL Android]瀏覽器或 [!DNL iOS])。 |
| 設定 | 包括下列控制項： <br/><ul><li>將關鍵值資料傳遞至 [!DNL URL] 目的地。您可以將資料傳送為個別或序列化索引鍵值配對。如需詳細資訊，請參閱 [「目標序列化](../../features/destinations/key-value-pairs.md#destination-serialized) 」、「 [標準序列化」和「序列索引鍵-值」配對](../../features/destinations/key-value-pairs.md)。 </li><li>Cookie目的地的元素，例如Cookie名稱、網域、大小、有效期間隔、資料格式等。</li></ul> |
| 區段映射 | 可讓您: <br/><ul><li>搜尋、新增和管理與所有目的地類型關聯的區段。 </li><li>在個別區段上設定傳送優先順序(僅適用於 [!DNL cookie]型區段)。</li></ul> |

## 資料傳送方法 {#data-delivery-methods}

透過字串傳遞資訊、 [!DNL URL] 透過字串寫入， [!DNL cookie]或透過離線伺服器對伺服器資料傳輸，將資訊傳送至目的地。

* [!DNL URL] 和基於Cookie的目的地會同步傳輸資料，使用者會在頁面上採取動作。
* 伺服器對伺服器資料傳輸是非同步的，在使用者離開頁面後可能會發生。您選取的傳送類型取決於您的業務需求，以及特定資料合作夥伴要如何接收資料。

如需詳細資訊，請參閱 [如何選擇目標類型](../../features/destinations/destinations.md) 。