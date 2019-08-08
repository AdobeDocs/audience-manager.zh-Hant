---
description: URL目的地會從頁面發出像素呼叫至目的地。請依照下列指示，使用「目標產生器」建立URL目的地。
seo-description: URL目的地會從頁面發出像素呼叫至目的地。請依照下列指示，使用「目標產生器」建立URL目的地。
seo-title: 設定URL目的地
solution: Audience Manager
title: 設定URL目的地
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# 設定URL目的地 {#configure-url-destination}

[!DNL URL] 目的地會從頁面發出像素呼叫至目的地。請依照下列指示來建立 [!DNL URL] 目的地。[!UICONTROL Destination Builder]

<!-- create-url-destination.xml -->

若要建立 [!DNL URL] 新的目的地，請前往 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 並完成章節，如下所述。

## 基本資訊 {#basic-info}

本節包含開始URL目的地建立程序的欄位和選項。若要完成本節：

1. 按一下 **[!UICONTROL Basic Information]** 以公開控制項。
2. 命名目的地。避免縮寫和特殊字元。
3. *(選擇性)* 說明目的地。簡明扼要的說明是定義或提供目標的更多資訊。
4. 在 **[!UICONTROL Category]** 清單中選擇 **[!UICONTROL Custom]**。
5. 在 **[!UICONTROL Environment]** 清單中，選取要觸發URL目的地的環境。
6. 在 **[!UICONTROL Type]** 清單中，按 **[!UICONTROL URL]**&#x200B;一下。
7. *(選擇性)* 選擇 **[!UICONTROL Auto-fill Destination Mapping]**&#x200B;一個。選項包括:
   * **[!UICONTROL Segment ID]**：自動新增區段ID並傳送至目的地。
   * **[!UICONTROL Integration Code Value]**：自動新增區段整合代碼並傳送至目的地對應。整合代碼是客戶建立並使用的唯一識別碼。僅限255個字元上限。
8. 按一下 **[!UICONTROL Next]** 以前往 [!UICONTROL Configuration] 設定或按一下 **[!UICONTROL Data Export Labels]** ，將匯出控制套用至目的地。

## 資料匯出標籤 {#data-export-labels-dest}

本節包含將 [資料匯出控制](../../features/data-export-controls.md) 套用 [!DNL URL] 至目的地的選項。如果您不使用資料匯出控制，請跳過此步驟。若要完成本節：

1. 按一下 **[!UICONTROL Data Export Labels]** 以公開控制項。
2. 選取對應至目的地之資料匯出控制的標籤(請參閱 [「將匯出標籤新增至目的地](/help/using/features/destinations/add-data-export-labels.md) 」以取得詳細資訊)。
3. Click **[!UICONTROL Save]**.

## 設定 {#configure-base-data}

本節包含可讓您設定字串傳入之基底 [!DNL URL] 和資料分隔字元的選項 [!DNL URL] 。此區域為選用。若要完成本節：

1. 按一下 **[!UICONTROL Configuration]** 以公開控制項。
1. *(選擇性)* 選取 **[!UICONTROL Serialize]** 核取方塊。
這可讓您依序傳送區段至目的地，而非對每個區段進行個別呼叫。序列化有助於提高資料傳輸效率。選取此核取方塊會顯示URL和分隔字元欄位。如需詳細資訊，請參閱 [標準和序列金鑰-值配對](../../features/destinations/key-value-pairs.md)。
1. 如果您選取 **[!UICONTROL Serialize]**，則您也必須設定下面所述的URL和分隔字元欄位。

| 欄位 | 說明 |
|--- |--- |
| 基礎 URL | 基本部分不 `HTTP`[!DNL URL] 會變更。此外，您還需要將 `%ALIAS%`[預留位置巨集](../../features/destinations/destination-macros.md#destination-macros-defined) 置於基本URL中。範例: `https://www.myCompany.com/%alias%...` |
| 安全URL | The base part of a secure `HTTPS`[!DNL URL] that does not change.此外，您還需要將 `%ALIAS%`[預留位置巨集](../../features/destinations/destination-macros.md#destination-macros-defined) 置於基本URL中。範例: `https://www.myCompany.com/%alias%...` |
| 分隔字元 | 分隔 [!DNL URL] 字串中區段變數的符號。這通常是逗號或分號。從您的目的地合作夥伴取得此資訊。 |

## 區段映射 {#segment-mappings}

此區段可讓您搜尋並新增區段至目的地。若要完成本節：

1. 按一下 **[!UICONTROL Segment Mappings]** 以公開控制項。
1. **[!UICONTROL Search and Add Segments]** 在方塊中，開始鍵入區段名稱，或按一下 **[!UICONTROL Browse All Segments]** 可瀏覽可用區段清單。
1. 當 **[!UICONTROL Add Selected Segments]** 您尋找要使用的區段時，按一下。新增區段會開啓 [!UICONTROL Edit Mapping] 視窗。
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**：提供區段使用的索引鍵值配對。
   * **[!UICONTROL Start Date]** and **[!UICONTROL End Date]**：選擇目的地的開始和結束日期。如果結束日期空白，目的地永不過期。
1. Click **[!UICONTROL Done]**.