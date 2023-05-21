---
description: 目標生成器用於建立基於cookie或DNL URL的目標。 不能使用目標生成器建立伺服器到伺服器(S2S)目標，但可以管理其段映射。 請與顧問聯繫以設定S2S目標。 目標生成器位於「受眾資料」>「目標」中。
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: 目的地產生器
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 4%

---

# 目的地產生器 {#destination-builder}

[!UICONTROL Destination Builder] 允許您建立基於cookie或 [!DNL URL] 目標。 無法建立伺服器到伺服器([!DNL S2S])目標 [!UICONTROL Destination Builder]，但可以管理其段映射。 與顧問聯繫以設定 [!DNL S2S] 目標。 [!UICONTROL Destination Builder] 位於 **[!UICONTROL Audience Data > Destinations]**。

## 目標生成器設定 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 包括以下部分和設定：

| [!UICONTROL Destination Builder] 區域 | 用途 |
|--- |--- |
| 基本資訊 | 用於命名目標、描述它並選擇目標類型([!DNL URL] 或 [!DNL cookie])和平台(全部， [!DNL Android]，瀏覽器，或 [!DNL iOS])。 |
| 設定 | 包括下列控制項： <br/><ul><li>將鍵值資料傳遞到 [!DNL URL] 目標。 可以將資料作為單個或序列化的鍵值對發送。 有關詳細資訊，請參閱 [目標序列化](../../features/destinations/key-value-pairs.md#destination-serialized) 和 [標準和序列鍵值對](../../features/destinations/key-value-pairs.md)。 </li><li>Cookie目標的元素，如Cookie名稱、域、大小、過期間隔、資料格式等。</li></ul> |
| 段映射 | 可讓您: <br/><ul><li>搜索、添加和管理與所有目標類型關聯的段。 </li><li>設定各個段的交付優先順序(用於 [!DNL cookie]僅基於段)。</li></ul> |

## 資料傳遞方法 {#data-delivery-methods}

將資訊通過 [!DNL URL] 字串，通過寫入瀏覽器 [!DNL cookie]或通過離線伺服器到伺服器的資料傳輸。

* [!DNL URL] 當用戶在頁面上執行操作時，基於cookie的目的地同步傳輸資料。
* 伺服器到伺服器的資料傳輸是非同步的，並且在用戶離開頁面後很長時間內會發生。 您選擇的交付類型取決於您的業務需求以及特定資料合作夥伴希望或能夠接收資料的方式。

請參閱 [如何選擇目標類型](../../features/destinations/destinations.md) 的子菜單。
