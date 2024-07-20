---
description: 您可以透過使用者端（瀏覽器端）整合或伺服器端整合，將合格的區段傳送至Google Ad Manager。 如果您選擇使用者端整合，則必須在Audience Manager中為Google發佈商廣告代碼建立Cookie型目的地。
seo-description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: 建立GPT目的地
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 3%

---

# 建立GPT目的地 {#create-a-gpt-destination}

您可以透過使用者端（瀏覽器端）整合或伺服器端整合，將合格的區段傳送至[!DNL Google Ad Manager]。 如果您選擇使用者端整合，則必須在Audience Manager中為[!DNL Google Publisher Tags]建立Cookie型目的地。

## 目的地

在Audience Manager中，*`destination`*&#x200B;是任何其他系統（廣告伺服器、[!DNL DSP]、廣告網路等） 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder]提供可讓您建立和管理這些資料傳遞程式的工具。 Audience Manager目的地功能位於&#x200B;*[!UICONTROL Audience Data]>[!UICONTROL Destinations]*。 若要開始使用，請按一下&#x200B;**[!UICONTROL Add New Destination]**&#x200B;並遵循下列步驟。

## 基本資訊

若要完成[!UICONTROL Basic Information]區段：

1. 為目的地命名。
1. 從[!UICONTROL Type]下拉式清單中選取&#x200B;**[!UICONTROL "Cookie"]**。
1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;並移至[!UICONTROL Configuration]與[!UICONTROL Segment Mappings]區段。

## Cookie設定

提供下列專案以完成[!UICONTROL Configuration]區段（其他欄位為選用）：

1. **Cookie名稱：**&#x200B;為您的Cookie提供簡短描述性名稱。
1. **資料格式：**&#x200B;選取&#x200B;**[!UICONTROL "Single Key"]**&#x200B;選項。
1. **金鑰：**&#x200B;提供金鑰名稱。
1. **序列化：**&#x200B;選取&#x200B;**[!UICONTROL Enable]**&#x200B;核取方塊。
1. **序列分隔符號：**&#x200B;僅使用逗號。

## 區段對應

若要將區段新增至Cookie目的地：

1. 尋找區段： [!UICONTROL Segment Mappings]區段提供兩種搜尋工具來協助尋找區段。 若要搜尋區段，請執行下列步驟：

   * 選項1：開始在搜尋欄位中輸入區段名稱。 欄位會根據輸入的文字自動更新。 找到要使用的區段後，請按一下&#x200B;**[!UICONTROL Add]**。
   * 選項2：按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;開啟視窗，讓您依名稱或儲存位置瀏覽區段。 完成時，按一下&#x200B;**[!UICONTROL Add Selected Segments]**。

1. **新增對應：**&#x200B;在對應快顯視窗中，在對應欄位中輸入區段ID，然後按一下&#x200B;**[!UICONTROL Save]**。

1. 按一下 **[!UICONTROL Done]**。
