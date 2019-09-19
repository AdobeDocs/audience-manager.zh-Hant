---
description: 您可以透過用戶端（瀏覽器端）整合或伺服器端整合，將合格的區段傳送至DFP。 如果您選擇用戶端整合，您必須在Audience manager中為Google Publisher標籤建立Cookie型目標。
seo-description: 您可以透過用戶端（瀏覽器端）整合或伺服器端整合，將合格的區段傳送至DFP。 如果您選擇用戶端整合，您必須在Audience manager中為Google Publisher標籤建立Cookie型目標。
seo-title: 建立GPT目標
solution: Audience Manager
title: 建立GPT目標
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# 建立GPT目標 {#create-a-gpt-destination}

您可以透過用戶端(瀏 [!DNL DFP] 覽器端)整合或伺服器端整合，將合格的區段傳送至。 如果您選擇用戶端整合，則必須在Audience manager中建立以Cookie為基礎的 [!DNL Google Publisher Tags] 目標。

## 目的地

在Audience manager中， *`destination`* 是任何其他系統(廣告伺服 [!DNL DSP]器、廣告網路等)您想要與其共用資料。 [!UICONTROL Destination Builder] 提供可讓您建立和管理這些資料傳送程式的工具。 Audience manager目標功能位於 *[!UICONTROL Audience Data]&gt;[!UICONTROL Destinations]*。 若要開始，請按一 **[!UICONTROL Add New Destination]** 下並遵循下列步驟。

## 基本資訊

要完成該部 [!UICONTROL Basic Information] 分：

1. 命名目標。
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. 單 **[!UICONTROL Next]** 擊並移至和 [!UICONTROL Configuration] 節 [!UICONTROL Segment Mappings] 。

## Cookie設定

請提供以下內容以完成 [!UICONTROL Configuration] 章節（其他欄位為選填欄位）:

1. **** Cookie名稱：為您的Cookie提供簡短的描述性名稱。
1. **** 資料格式：選擇選 **[!UICONTROL "Single Key"]** 項。
1. **** 索引鍵：提供密鑰名稱。
1. **** 序列化：選中復 **[!UICONTROL Enable]** 選框。
1. **** 串列分隔字元：僅使用逗號。

## 區段對應

若要新增區段至Cookie目標：

1. 尋找區段：本節 [!UICONTROL Segment Mappings] 提供兩種搜尋工具，以協助尋找區段。 若要尋找區段：

   * 選項1:開始在搜尋欄位中輸入區段名稱。 欄位會根據輸入的文字自動更新。 在找 **[!UICONTROL Add]** 到要使用的區段後，按一下。
   * 選項2:按一 **[!UICONTROL Browse All Segments]** 下以開啟可讓您依名稱或儲存位置瀏覽區段的視窗。 Click **[!UICONTROL Add Selected Segments]** when done.

1. **** 添加映射：在映射彈出式視窗中，在映射欄位中輸入區段ID，然後按一下 **[!UICONTROL Save]**。

1. Click **[!UICONTROL Done]**.