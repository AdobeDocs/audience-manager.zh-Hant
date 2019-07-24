---
description: 您可以透過用戶端(瀏覽器端)整合或伺服器端整合，將合格的區段傳送至DFP。如果您選擇用戶端整合，您必須在Audience Manager中建立Google Publisher標記的Cookie目的地。
seo-description: 您可以透過用戶端(瀏覽器端)整合或伺服器端整合，將合格的區段傳送至DFP。如果您選擇用戶端整合，您必須在Audience Manager中建立Google Publisher標記的Cookie目的地。
seo-title: 建立GPT目的地
solution: Audience Manager
title: 建立GPT目的地
uuid: e3bbf327-a7 e0-48da-bc84-8f531 b7 f6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Create a GPT Destination {#create-a-gpt-destination}

You can send qualified segments to [!DNL DFP] through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for [!DNL Google Publisher Tags] in Audience Manager.

## 目的地

In Audience Manager, a *`destination`* is any other system (ad server, [!DNL DSP], ad network, etc.) 您要與其共用資料。[!UICONTROL Destination Builder] 提供可讓您建立和管理這些資料傳送程序的工具。Audience Manager destination features are located in *[!UICONTROL Audience Data]&gt;[!UICONTROL Destinations]*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

## 基本資訊

To complete the [!UICONTROL Basic Information] section:

1. 命名目的地。
1. **[!UICONTROL "Cookie"]** 從 [!UICONTROL Type] 下拉式清單中選取。
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

## Cookie設定

Provide the following to complete the [!UICONTROL Configuration] section (other fields are optional):

1. **Cookie名稱：** 為您的Cookie提供簡短、描述性的名稱。
1. **資料格式：** 選擇 **[!UICONTROL "Single Key"]** 選項。
1. **索引鍵：** 提供關鍵名稱。
1. **序列化：** 選取 **[!UICONTROL Enable]** 核取方塊。
1. **序號分隔字元：** 僅使用逗號。

## 區段映射

若要新增區段至Cookie目的地：

1. Find segments: The [!UICONTROL Segment Mappings] section provides two search tools to help locate segments. 若要尋找區段：

   * 選項1：開始在搜尋欄位中鍵入區段名稱。欄位會根據輸入的文字自動更新。Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.

1. **新增對應：** 在對應彈出式視窗中，輸入映射欄位中的區段ID，然後按一下 **[!UICONTROL Save]**。

1. Click **[!UICONTROL Done]**.