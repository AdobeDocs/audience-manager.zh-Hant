---
description: URL目的地會從頁面對目的地進行像素呼叫。 請依照下列指示，使用「目標產生器」建立URL目標。
seo-description: URL目的地會從頁面對目的地進行像素呼叫。 請依照下列指示，使用「目標產生器」建立URL目標。
seo-title: 設定 URL 目的地
solution: Audience Manager
title: 設定 URL 目的地
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 3%

---



# 配置[!DNL URL Destination] {#configure-url-destination}

[!DNL URL destination]會從頁面對您的[!DNL destination]進行像素呼叫。 請依照下列指示，建立[!DNL URL] [!DNL destination]及[!UICONTROL Destination Builder]。

<!-- create-url-destination.xml -->

若要建立新的[!DNL URL] [!DNL destination]，請前往&#x200B;**[!UICONTROL Audience Data > Destinations > Create New Destination]**&#x200B;並依照下列說明完成章節。

## 基本資訊 {#basic-info}

本節包含啟動[!DNL URL destination]建立過程的欄位和選項。 要完成本節：

1. 按一下&#x200B;**[!UICONTROL Basic Information]**&#x200B;以公開控制項。
2. 命名[!DNL destination]。 避免縮寫和特殊字元。
3. *（可選）* 說明 [!DNL destination]。簡明說明是定義或提供更多[!DNL destination]相關資訊的有效方式。
4. 在&#x200B;**[!UICONTROL Category]**&#x200B;清單中，選擇&#x200B;**[!UICONTROL Custom]**。
5. 在&#x200B;**[!UICONTROL Environment]**&#x200B;清單中，選擇要觸發[!DNL URL destination]的環境。
6. 在&#x200B;**[!UICONTROL Type]**&#x200B;清單中，按一下&#x200B;**[!UICONTROL URL]**。
7. *（可選）* 選取 **[!UICONTROL Auto-fill Destination Mapping]**。選項包括:
   * **[!UICONTROL Segment ID]**:自動新增區段ID並傳送至 [!DNL destination]。
   * **[!UICONTROL Integration Code Value]**:自動新增區段整合代碼並傳送至目標對應。整合程式碼是客戶建立和使用的唯一識別碼。 最多限制為255個字元。
8. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;移至[!UICONTROL Configuration]設定，或按一下&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;將匯出控制套用至[!DNL destination]。

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

本節包含將[資料導出控制](../../features/data-export-controls.md)應用到[!DNL URL]目標的選項。 如果您不使用資料匯出控制，請略過此步驟。 要完成本節：

1. 按一下&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;以公開控制項。
2. 選擇與應用於目標的資料導出控制相對應的標籤（有關詳細資訊，請參閱[將導出標籤添加到目標](/help/using/features/destinations/add-data-export-labels.md)）。
3. 按一下 **[!UICONTROL Save]**.

## 設定 {#configure-base-data}

本節包含一些選項，可讓您設定由[!DNL URL]字串傳入的基本[!DNL URL]和資料分隔字元。 此部分是可選的。 要完成本節：

1. 按一下&#x200B;**[!UICONTROL Configuration]**&#x200B;以公開控制項。
1. *（可選）選* 取核取 **[!UICONTROL Serialize]** 方塊。這可讓您依序傳送區段至[!DNL destination]，而不是對每個區段進行個別呼叫。 序列化有助於提高資料傳輸的效率。 選取此核取方塊會顯示URL和分隔字元欄位。 如需詳細資訊，請參閱[標準與串列金鑰值配對](../../features/destinations/key-value-pairs.md)。
1. 如果您選取&#x200B;**[!UICONTROL Serialize]**，則您也必須設定下述的URL和分隔字元欄位。

| 欄位 | 說明 |
|--- |--- |
| [!UICONTROL Base URL] | 不變的標準`HTTP` [!DNL URL]的基本部分。 此外，您還需要將`%ALIAS%` [預留位置宏](../../features/destinations/destination-macros.md#destination-macros-defined)放置在基本URL中。 範例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | 未更改的安全`HTTPS` [!DNL URL]的基本部分。 此外，您還需要將`%ALIAS%`   [基本URL中的預留位置宏](../../features/destinations/destination-macros.md#destination-macros-defined)。 範例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | 分隔[!DNL URL]字串中區段變數的符號。 這通常是逗號或分號。 從目的地合作夥伴取得這些資訊。 |

## [!UICONTROL Segment Mappings] {#segment-mappings}

此區段可讓您搜尋並新增區段至[!UICONTROL destination]。 要完成本節：

1. 按一下&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;以公開控制項。
1. 在&#x200B;**[!UICONTROL Search and Add Segments]**&#x200B;方塊中，開始輸入區段的名稱，或按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;瀏覽可用區段的清單。
1. 當您找到要使用的區段時，按一下&#x200B;**[!UICONTROL Add Selected Segments]**。 新增區段會開啟[!UICONTROL Edit Mapping]視窗。
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**:提供區段使用的索引鍵值配對。
   * **[!UICONTROL Start Date]** 和 **[!UICONTROL End Date]**:選擇開始日期和結束日期 [!DNL destination]。如果結束日期空白，[!DNL destination]將不會過期。
1. 按一下 **[!UICONTROL Done]**.