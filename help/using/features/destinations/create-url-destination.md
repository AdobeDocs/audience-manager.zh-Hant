---
description: URL目的地會從頁面對目的地進行像素呼叫。 請依照下列指示，使用「目標產生器」建立URL目標。
seo-description: URL目的地會從頁面對目的地進行像素呼叫。 請依照下列指示，使用「目標產生器」建立URL目標。
seo-title: 設定 URL 目的地
solution: Audience Manager
title: 設定 URL 目的地
translation-type: tm+mt
source-git-commit: d83b07a542dd337773d287f4eba0960c6e258504
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 3%

---



# 設定 [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] 會從頁面對您進行像素呼叫 [!DNL destination]。 請依照下列指示，建立 [!DNL URL] 具 [!DNL destination] 體 [!UICONTROL Destination Builder]。

<!-- create-url-destination.xml -->

若要建立新 [!DNL URL] 的 [!DNL destination]內容，請 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 前往並完成下列章節。

## 基本資訊 {#basic-info}

本節包含開始建立程式的欄位 [!DNL URL destination] 和選項。 要完成本節：

1. 按一 **[!UICONTROL Basic Information]** 下以顯示控制項。
2. 命名 [!DNL destination]。 避免縮寫和特殊字元。
3. *（可選）* ，請說明 [!DNL destination]。 簡明的描述是定義或提供更多有關資訊的有效方式 [!DNL destination]。
4. 在清單 **[!UICONTROL Category]** 中，選擇 **[!UICONTROL Custom]**。
5. 在列 **[!UICONTROL Environment]** 表中，選擇要觸發的環境 [!DNL URL destination]。
6. 在清單 **[!UICONTROL Type]** 中，按一下 **[!UICONTROL URL]**。
7. *（可選）* ，選取 **[!UICONTROL Auto-fill Destination Mapping]**。 選項包括:
   * **[!UICONTROL Segment ID]**: 自動新增區段ID並傳送至 [!DNL destination]。
   * **[!UICONTROL Integration Code Value]**: 自動新增區段整合代碼並傳送至目標對應。 整合程式碼是客戶建立和使用的唯一識別碼。 最多限制為255個字元。
8. 按一 **[!UICONTROL Next]** 下以前往設定， [!UICONTROL Configuration] 或按一下 **[!UICONTROL Data Export Labels]** 以套用匯出控制項至 [!DNL destination]。

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

本節包含將資料匯出控 [制套用至目標](../../features/data-export-controls.md) 的 [!DNL URL] 選項。 如果您不使用資料匯出控制，請略過此步驟。 要完成本節：

1. 按一 **[!UICONTROL Data Export Labels]** 下以顯示控制項。
2. 選取與套用至目標的資料匯出控制相對應的標籤(如需詳細資訊，請 [參閱「將匯出標籤新增至目標](/help/using/features/destinations/add-data-export-labels.md) 」)。
3. 按一下 **[!UICONTROL Save]**.

## 設定 {#configure-base-data}

本節包含可讓您設定字串傳入之基 [!DNL URL] 本和資料分隔字元的 [!DNL URL] 選項。 此部分是可選的。 要完成本節：

1. 按一 **[!UICONTROL Configuration]** 下以顯示控制項。
1. *（可選）* ，選取核取 **[!UICONTROL Serialize]** 方塊。
這可讓您依序傳送區段至 [!DNL destination] 區段，而不是對每個區段進行個別呼叫。 序列化有助於提高資料傳輸的效率。 選取此核取方塊會顯示URL和分隔字元欄位。 如需詳細資訊，請 [參閱標準和序號鍵值配對](../../features/destinations/key-value-pairs.md)。
1. 如果您選 **[!UICONTROL Serialize]**&#x200B;取，則您也必須設定下述的URL和分隔字元欄位。

| 欄位 | 說明 |
|--- |--- |
| [!UICONTROL Base URL] | 不變的標準的 `HTTP` 基 [!DNL URL] 礎部分。 此外，您還需要將預留 `%ALIAS%` 位 [置宏](../../features/destinations/destination-macros.md#destination-macros-defined) 置於基本URL中。 範例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | 不變的安全保 `HTTPS` 險的 [!DNL URL] 基本部分。 此外，您還需要將預留 `%ALIAS%` 位 [置宏](../../features/destinations/destination-macros.md#destination-macros-defined) 置於基本URL中。 範例: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | 分隔字串中區段變數的符 [!DNL URL] 號。 這通常是逗號或分號。 從目的地合作夥伴取得這些資訊。 |

## [!UICONTROL Segment Mappings] {#segment-mappings}

此區段可讓您搜尋並新增區段至 [!UICONTROL destination]。 要完成本節：

1. 按一 **[!UICONTROL Segment Mappings]** 下以顯示控制項。
1. 在方塊 **[!UICONTROL Search and Add Segments]** 中，開始輸入區段名稱，或按一下 **[!UICONTROL Browse All Segments]** 瀏覽可用區段的清單。
1. 當您 **[!UICONTROL Add Selected Segments]** 找到要使用的區段時，按一下。 新增區段會開啟視 [!UICONTROL Edit Mapping] 窗。
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: 提供區段使用的索引鍵值配對。
   * **[!UICONTROL Start Date]** 和 **[!UICONTROL End Date]**: 選擇開始日期和結束日期 [!DNL destination]。 如果結束日期空白，則永 [!DNL destination] 不過期。
1. 按一下 **[!UICONTROL Done]**.