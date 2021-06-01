---
description: URL目的地會從頁面對目的地進行像素呼叫。 請依照下列指示，使用Destination Builder建立URL目的地。
seo-description: URL目的地會從頁面對目的地進行像素呼叫。 請依照下列指示，使用Destination Builder建立URL目的地。
seo-title: 設定 URL 目的地
solution: Audience Manager
title: 設定 URL 目的地
feature: 目的地基本知識
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 3%

---

# 配置[!DNL URL Destination] {#configure-url-destination}

[!DNL URL destination]會從頁面對您的[!DNL destination]進行像素呼叫。 請依照下列指示，使用[!UICONTROL Destination Builder]建立[!DNL URL] [!DNL destination]。

<!-- create-url-destination.xml -->

要建立新的[!DNL URL] [!DNL destination]，請轉至&#x200B;**[!UICONTROL Audience Data > Destinations > Create New Destination]**&#x200B;並按如下所述完成各節。

## 基本資訊 {#basic-info}

此部分包含啟動[!DNL URL destination]建立過程的欄位和選項。 要完成此部分：

1. 按一下&#x200B;**[!UICONTROL Basic Information]**&#x200B;以公開控制項。
2. 將[!DNL destination]命名為。 避免縮寫和特殊字元。
3. *（選用）* 說明 [!DNL destination]。簡潔的說明是定義或提供[!DNL destination]更多資訊的有效方式。
4. 在&#x200B;**[!UICONTROL Category]**&#x200B;清單中，選擇&#x200B;**[!UICONTROL Custom]**。
5. 在&#x200B;**[!UICONTROL Environment]**&#x200B;清單中，選取要觸發[!DNL URL destination]的環境。
6. 在&#x200B;**[!UICONTROL Type]**&#x200B;清單中，按一下&#x200B;**[!UICONTROL URL]**。
7. *（選用）* 選取 **[!UICONTROL Auto-fill Destination Mapping]**。選項包括:
   * **[!UICONTROL Segment ID]**:自動新增區段ID並傳送至 [!DNL destination]。
   * **[!UICONTROL Integration Code Value]**:自動新增區段整合代碼，並將其傳送至目的地對應。整合代碼是客戶建立和使用的唯一識別碼。 上限為255個字元，上限為。
8. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;前往[!UICONTROL Configuration]設定，或按一下&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;將匯出控制套用至[!DNL destination]。

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

本節包含將[資料導出控制項](../../features/data-export-controls.md)應用到[!DNL URL]目標的選項。 如果您不使用資料匯出控制，請略過此步驟。 要完成此部分：

1. 按一下&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;以公開控制項。
2. 選取與套用至目的地的資料匯出控制相對應的標籤（如需詳細資訊，請參閱[將匯出標籤新增至目的地](/help/using/features/destinations/add-data-export-labels.md)）。
3. 按一下 **[!UICONTROL Save]**.

## 設定 {#configure-base-data}

本節包含的選項可讓您設定基[!DNL URL]以及由[!DNL URL]字串傳入的資料分隔字元。 此區段為選填。 要完成此部分：

1. 按一下&#x200B;**[!UICONTROL Configuration]**&#x200B;以公開控制項。
1. *（選用）* 選取核 **[!UICONTROL Serialize]** 取方塊。這可讓您依序傳送區段至[!DNL destination]，而非對每個區段進行個別呼叫。 序列化有助於提高資料傳輸的效率。 選取此核取方塊會顯示URL和分隔字元欄位。 如需詳細資訊，請參閱[標準和串列索引鍵值配對](../../features/destinations/key-value-pairs.md)。
1. 如果您選取&#x200B;**[!UICONTROL Serialize]**，則還必須配置下述的URL和分隔字元欄位。

| 欄位 | 說明 |
|--- |--- |
| [!UICONTROL Base URL] | 未更改的標準`HTTP` [!DNL URL]的基部。 此外，您還需要將`%ALIAS%` [預留位置宏](../../features/destinations/destination-macros.md#destination-macros-defined)放置在基本URL中。 範例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | 未更改的安全`HTTPS` [!DNL URL]的基部。 此外，您需要將`%ALIAS%`   基本URL中的[預留宏](../../features/destinations/destination-macros.md#destination-macros-defined)。 範例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | 分隔[!DNL URL]字串中段變數的符號。 這通常是逗號或分號。 從目的地合作夥伴處獲取此資訊。 |

## [!UICONTROL Segment Mappings] {#segment-mappings}

此區段可讓您搜尋區段並新增至[!UICONTROL destination]。 要完成此部分：

1. 按一下&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;以公開控制項。
1. 在&#x200B;**[!UICONTROL Search and Add Segments]**&#x200B;方塊中，開始輸入區段名稱，或按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;瀏覽可用區段清單。
1. 找到您要使用的區段時，按一下&#x200B;**[!UICONTROL Add Selected Segments]**。 新增區段會開啟[!UICONTROL Edit Mapping]視窗。
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**:提供區段使用的機碼值組。
   * **[!UICONTROL Start Date]** 和 **[!UICONTROL End Date]**:選擇的開始和結束日期 [!DNL destination]。如果結束日期空白，[!DNL destination]永不過期。
1. 按一下 **[!UICONTROL Done]**.
