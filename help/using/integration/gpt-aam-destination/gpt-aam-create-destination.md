---
description: 您可以透過用戶端（瀏覽器端）整合或伺服器端整合，將合格區段傳送至Google Ad Manager。 如果您選擇用戶端整合，則必須為Audience Manager中的Google發佈商標籤建立Cookie型目的地。
seo-description: 您可以透過用戶端（瀏覽器端）整合或伺服器端整合，將合格區段傳送至Google Ad Manager。 如果您選擇用戶端整合，則必須為Audience Manager中的Google發佈商標籤建立Cookie型目的地。
seo-title: 建立 GPT 目的地
solution: Audience Manager
title: 建立 GPT 目的地
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: 協力廠商整合
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 7%

---

# 建立 GPT 目的地 {#create-a-gpt-destination}

您可以透過用戶端（瀏覽器端）整合或伺服器端整合，將合格區段傳送至[!DNL Google Ad Manager]。 如果您選擇用戶端整合，則必須為Audience Manager中的[!DNL Google Publisher Tags]建立Cookie型目的地。

## 目的地

在Audience Manager中，*`destination`*&#x200B;是任何其他系統（廣告伺服器、[!DNL DSP]、廣告網路等） 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder] 提供可讓您建立和管理這些資料傳送程式的工具。Audience Manager目標功能位於&#x200B;*[!UICONTROL Audience Data]>[!UICONTROL Destinations]*&#x200B;中。 若要開始使用，請按一下&#x200B;**[!UICONTROL Add New Destination]**&#x200B;並遵循下列步驟。

## 基本資訊

要完成[!UICONTROL Basic Information]部分：

1. 為目的地命名。
1. 從[!UICONTROL Type]下拉清單中選擇&#x200B;**[!UICONTROL "Cookie"]**。
1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;並移至[!UICONTROL Configuration]和[!UICONTROL Segment Mappings]區段。

## Cookie設定

提供下列項目以完成[!UICONTROL Configuration]區段（其他欄位為選用欄位）:

1. **Cookie名稱：** 為您的Cookie提供簡短的描述性名稱。
1. **資料格式：** 選取 **[!UICONTROL "Single Key"]** 選項。
1. **索引鍵：** 提供索引鍵名稱。
1. **序列化：** 選取核取 **[!UICONTROL Enable]** 方塊。
1. **串列分隔字元：** 僅使用逗號。

## 區段對應

若要新增區段至Cookie目的地：

1. 尋找區段：[!UICONTROL Segment Mappings]區段提供兩種搜尋工具，以協助找出區段。 若要尋找區段：

   * 選項1:開始在搜尋欄位中輸入區段名稱。 欄位會根據輸入的文字自動更新。 找到您要使用的區段後，按一下&#x200B;**[!UICONTROL Add]**。
   * 選項2:按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;以開啟一個視窗，讓您依名稱或儲存位置瀏覽區段。 完成後，按一下&#x200B;**[!UICONTROL Add Selected Segments]**。

1. **新增對應：** 在對應快顯視窗中，在對應欄位中輸入區段ID，然後按一下 **[!UICONTROL Save]**。

1. 按一下 **[!UICONTROL Done]**.
