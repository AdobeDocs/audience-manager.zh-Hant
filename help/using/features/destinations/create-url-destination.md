---
description: URL目的地會從頁面對您的目的地進行畫素呼叫。 請依照這些指示，使用Destination Builder建立URL目的地。
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: 設定URL目的地
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 1%

---

# 設定[!DNL URL Destination] {#configure-url-destination}

[!DNL URL destination]從頁面對您的[!DNL destination]進行畫素呼叫。 請依照這些指示，使用[!UICONTROL Destination Builder]建立[!DNL URL] [!DNL destination]。

<!-- create-url-destination.xml -->

若要建立新的[!DNL URL] [!DNL destination]，請移至&#x200B;**[!UICONTROL Audience Data > Destinations > Create New Destination]**&#x200B;並完成以下所述的區段。

## 基本資訊 {#basic-info}

此區段包含啟動[!DNL URL destination]建立程式的欄位和選項。 若要完成本節：

1. 按一下&#x200B;**[!UICONTROL Basic Information]**&#x200B;以公開控制項。
2. 為[!DNL destination]命名。 避免使用縮寫和特殊字元。
3. *（選擇性）*&#x200B;說明[!DNL destination]。 簡潔的說明是定義或提供有關[!DNL destination]的更多資訊的有效方式。
4. 在&#x200B;**[!UICONTROL Category]**&#x200B;清單中選擇&#x200B;**[!UICONTROL Custom]**。
5. 在&#x200B;**[!UICONTROL Environment]**&#x200B;清單中，選取要觸發[!DNL URL destination]的環境。
6. 在&#x200B;**[!UICONTROL Type]**&#x200B;清單中，按一下&#x200B;**[!UICONTROL URL]**。
7. *（選擇性）*&#x200B;選取&#x200B;**[!UICONTROL Auto-fill Destination Mapping]**。 選項包括:
   * **[!UICONTROL Segment ID]**：自動新增區段ID並傳送至[!DNL destination]。
   * **[!UICONTROL Integration Code Value]**：自動新增區段整合代碼，並將其傳送到目的地對應。 整合代碼是客戶建立及使用的唯一識別碼。 上限為255個字元。
8. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;以移至[!UICONTROL Configuration]設定，或按一下&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;以套用匯出控制至[!DNL destination]。

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

此區段包含將[資料匯出控制項](../../features/data-export-controls.md)套用至[!DNL URL]目的地的選項。 如果您不使用資料匯出控制項，請略過此步驟。 若要完成本節：

1. 按一下&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;以公開控制項。
2. 選取與套用至目的地的資料匯出控制對應的標籤（如需詳細資訊，請參閱[新增匯出標籤至目的地](/help/using/features/destinations/add-data-export-labels.md)）。
3. 按一下 **[!UICONTROL Save]**。

## 設定 {#configure-base-data}

此區段包含可讓您設定基底[!DNL URL]和由[!DNL URL]字串傳入的資料分隔符號的選項。 本節為選用。 若要完成本節：

1. 按一下&#x200B;**[!UICONTROL Configuration]**&#x200B;以公開控制項。
1. *（選擇性）*&#x200B;選取&#x200B;**[!UICONTROL Serialize]**核取方塊。
這可讓您依序將區段傳送至[!DNL destination]，而非針對每個區段分別發出呼叫。 序列化有助於提高資料傳輸效率。 選取此核取方塊會顯示URL和分隔符號欄位。 如需詳細資訊，請參閱[標準和序列索引鍵值配對](../../features/destinations/key-value-pairs.md)。
1. 若您選取&#x200B;**[!UICONTROL Serialize]**，則必須設定URL和分隔字元欄位，如下所述。

| 欄位 | 說明 |
|--- |--- |
| [!UICONTROL Base URL] | 標準`HTTP` [!DNL URL]的基底部分不會變更。 此外，您需要在基底URL中放置`%ALIAS%` [預留位置巨集](../../features/destinations/destination-macros.md#destination-macros-defined)。 範例： `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | 不會變更的安全`HTTPS` [!DNL URL]的基底部分。 此外，您必須放置`%ALIAS%`   基礎URL中的[預留位置巨集](../../features/destinations/destination-macros.md#destination-macros-defined)。 範例： `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | 區分[!DNL URL]字串中區段變數的符號。 這通常是逗號或分號。 從您的目的地合作夥伴取得此資訊。 |

## [!UICONTROL Segment Mappings] {#segment-mappings}

此區段可讓您搜尋區段並新增至[!UICONTROL destination]。 若要完成本節：

1. 按一下&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;以公開控制項。
1. 在&#x200B;**[!UICONTROL Search and Add Segments]**&#x200B;方塊中，開始輸入區段名稱，或按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;瀏覽可用區段清單。
1. 當您找到要使用的區段時，請按一下&#x200B;**[!UICONTROL Add Selected Segments]**。 新增區段會開啟[!UICONTROL Edit Mapping]視窗。
1. 在[!UICONTROL Edit Mapping]：
   * **[!UICONTROL Mappings]**：提供區段使用的機碼值組。
   * **[!UICONTROL Start Date]**&#x200B;與&#x200B;**[!UICONTROL End Date]**：選擇[!DNL destination]的開始與結束日期。 如果結束日期為空白，[!DNL destination]永遠不會過期。
1. 按一下 **[!UICONTROL Done]**。
