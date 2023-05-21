---
description: 您可以通過客戶端（瀏覽器端）整合或伺服器端整合將限定的段發送到Google廣告管理器。 如果選擇客戶端整合，則必須為Audience Manager中的Google發佈者標籤建立基於cookie的目標。
seo-description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: 建立 GPT 目的地
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 6%

---

# 建立 GPT 目的地 {#create-a-gpt-destination}

可將限定段發送到 [!DNL Google Ad Manager] 通過客戶端（瀏覽器端）整合或伺服器端整合。 如果選擇客戶端整合，則必須為 [!DNL Google Publisher Tags] Audience Manager。

## 目的地

在Audience Manager中，a *`destination`* 是其他系統（ad伺服器） [!DNL DSP]、ad網路等) 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder] 提供了用於建立和管理這些資料傳遞過程的工具。 Audience Manager目標功能位於 *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*。 要開始，請按一下 **[!UICONTROL Add New Destination]** 按照以下步驟操作。

## 基本資訊

完成 [!UICONTROL Basic Information] 部分：

1. 命名目標。
1. 選擇 **[!UICONTROL "Cookie"]** 從 [!UICONTROL Type] 的子菜單。
1. 按一下 **[!UICONTROL Next]** 繼續 [!UICONTROL Configuration] 和 [!UICONTROL Segment Mappings] 的下界。

## Cookie配置

提供以下內容以完成 [!UICONTROL Configuration] 部分（其他欄位為可選欄位）:

1. **Cookie名稱：** 為Cookie提供簡短的描述性名稱。
1. **資料格式：** 選擇 **[!UICONTROL "Single Key"]** 的雙曲餘切值。
1. **鍵：** 提供密鑰名稱。
1. **序列化：** 選擇 **[!UICONTROL Enable]** 複選框。
1. **序列分隔符：** 僅使用逗號。

## 段映射

要將段添加到Cookie目標：

1. 查找段：的 [!UICONTROL Segment Mappings] 部分提供了兩個搜索工具以幫助查找段。 要查找段，請執行以下操作：

   * 選項1:開始在搜索欄位中鍵入段名稱。 該欄位根據輸入的文本自動更新。 按一下 **[!UICONTROL Add]** 找到要使用的段後。
   * 選項2:按一下 **[!UICONTROL Browse All Segments]** 開啟一個窗口，以便按名稱或儲存位置瀏覽段。 按一下 **[!UICONTROL Add Selected Segments]** 完成。

1. **添加映射：** 在映射彈出窗口中，在映射欄位中輸入段ID，然後按一下 **[!UICONTROL Save]**。

1. 按一下 **[!UICONTROL Done]**.
