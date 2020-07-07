---
description: 您可以透過用戶端（瀏覽器端）整合或伺服器端整合，將合格的區段傳送至Google Ad Manager。 如果您選擇用戶端整合，您必須在Audience Manager中為Google Publisher標籤建立Cookie型目標。
seo-description: 您可以透過用戶端（瀏覽器端）整合或伺服器端整合，將合格的區段傳送至Google Ad Manager。 如果您選擇用戶端整合，您必須在Audience Manager中為Google Publisher標籤建立Cookie型目標。
seo-title: 建立 GPT 目的地
solution: Audience Manager
title: 建立 GPT 目的地
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 7%

---


# 建立 GPT 目的地 {#create-a-gpt-destination}

您可以透過用戶端(瀏 [!DNL Google Ad Manager] 覽器端)整合或伺服器端整合，將合格的區段傳送至。 如果您選擇用戶端整合，則必須在Audience Manager中建立以Cookie為基礎的 [!DNL Google Publisher Tags] 目標。

## 目的地

在Audience Manager中， *`destination`* 是任何其他系統(廣告伺服 [!DNL DSP]器、廣告網路等) 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder] 提供可讓您建立和管理這些資料傳送程式的工具。 Audience Manager目標功能位於 *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*。 若要開始，請按一&#x200B;**[!UICONTROL Add New Destination]**下並遵循下列步驟。

## 基本資訊

要完成該部 [!UICONTROL Basic Information] 分：

1. 命名目標。
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. 單 **[!UICONTROL Next]** 擊並移至和 [!UICONTROL Configuration] 節 [!UICONTROL Segment Mappings] 。

## Cookie設定

請提供以下內容以完成 [!UICONTROL Configuration] 章節（其他欄位為選填欄位）:

1. **Cookie名稱：** 為您的Cookie提供簡短的描述性名稱。
1. **資料格式：** 選擇選 **[!UICONTROL "Single Key"]** 項。
1. **索引鍵：** 提供密鑰名稱。
1. **序列化：** 選中復 **[!UICONTROL Enable]** 選框。
1. **串列分隔字元：** 僅使用逗號。

## 區段對應

若要新增區段至Cookie目標：

1. 尋找區段： 本節 [!UICONTROL Segment Mappings] 提供兩種搜尋工具，以協助尋找區段。 若要尋找區段：

   * 選項1: 開始在搜尋欄位中輸入區段名稱。 欄位會根據輸入的文字自動更新。 在找 **[!UICONTROL Add]** 到要使用的區段後，按一下。
   * 選項2: 按一 **[!UICONTROL Browse All Segments]** 下以開啟可讓您依名稱或儲存位置瀏覽區段的視窗。 完成時 **[!UICONTROL Add Selected Segments]** 按一下。

1. **添加映射：** 在映射彈出式視窗中，在映射欄位中輸入區段ID，然後按一下 **[!UICONTROL Save]**。

1. 按一下 **[!UICONTROL Done]**.