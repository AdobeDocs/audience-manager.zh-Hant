---
description: 目的地登陸頁面會列出您的所有URL、Cookie和伺服器對伺服器目的地。它提供可讓您建立、編輯、搜尋和報告目的地的功能。著陸頁面位於「對象資料>目標」中。
seo-description: 目的地登陸頁面會列出您的所有URL、Cookie和伺服器對伺服器目的地。它提供可讓您建立、編輯、搜尋和報告目的地的功能。著陸頁面位於「對象資料>目標」中。
seo-title: 管理目標
solution: Audience Manager
title: 管理目標
uuid: 6b66ff42-0075-49a7-a58 f-7f8 ea2295 fdc
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# 管理目標 {#manage-destinations}

[!UICONTROL Destination] 登陸頁面會列出您的所有 [!DNL URL]、Cookie和伺服器對伺服器目的地。它提供可讓您建立、編輯、搜尋和報告目的地的功能。著陸頁面 **[!UICONTROL Audience Data > Destinations]**&#x200B;位於。

## 預設登陸頁面 {#default-landing-page}

<!-- destinations-home.xml -->

預設登陸頁面會根據類型列出目的地。您可以使用四個可用標籤來篩選目的地：

* ****&#x200B;全部：顯示所有目的地類型。
* **Adobe Experience Cloud**：顯示將資料傳送至其他Adobe Experience Cloud解決方案的目標。目前唯一支援的選項是Adobe Analytics。See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **整合平台**：顯示以人員為主的裝置目的地(也稱為伺服器對伺服器目的地)。請注意，以人員為基礎的目的地目前僅適用於特定客戶。
* **自訂**：顯示Cookie和URL目的地。


![](assets/destinations-landing.png)

## 可定址對象著陸頁面 {#audiences-landing-page}

若要查看伺服器對伺服器目的地的讀者資料和匹配率，請選取 **[!UICONTROL Integrated Platforms > Device-Based]**。

如需顯示資訊的詳細資訊，請參閱 [「可定址對象介面](/help/using/features/addressable-audiences.md#addressable-audience-interface)」。

![](/help/using/features/assets/addressable-audiences-landing.png)

## 設定URL目的地 {#configure-url-destination}

[!DNL URL] 目的地會從頁面發出像素呼叫至目的地。請依照下列指示來建立 [!DNL URL] 目的地。[!UICONTROL Destination Builder]

<!-- create-url-destination.xml -->

若要建立 [!DNL URL] 新的目的地，請前往 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 並完成章節，如下所述。

### 基本資訊 {#basic-info}

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

### 資料匯出標籤 {#data-export-labels-dest}

本節包含將 [資料匯出控制](../../features/data-export-controls.md) 套用 [!DNL URL] 至目的地的選項。如果您不使用資料匯出控制，請跳過此步驟。若要完成本節：

1. 按一下 **[!UICONTROL Data Export Labels]** 以公開控制項。
2. 選取對應至目的地之資料匯出控制的標籤(請參閱 [「將匯出標籤新增至目的地](../../features/destinations/manage-destinations.md#add-data-export-labels) 」以取得詳細資訊)。
3. Click **[!UICONTROL Save]**.

### 設定 {#configure-base-data}

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

### 區段映射 {#segment-mappings}

此區段可讓您搜尋並新增區段至目的地。若要完成本節：

1. 按一下 **[!UICONTROL Segment Mappings]** 以公開控制項。
1. **[!UICONTROL Search and Add Segments]** 在方塊中，開始鍵入區段名稱，或按一下 **[!UICONTROL Browse All Segments]** 可瀏覽可用區段清單。
1. 當 **[!UICONTROL Add Selected Segments]** 您尋找要使用的區段時，按一下。新增區段會開啓 [!UICONTROL Edit Mapping] 視窗。
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**：提供區段使用的索引鍵值配對。
   * **[!UICONTROL Start Date]** and **[!UICONTROL End Date]**：選擇目的地的開始和結束日期。如果結束日期空白，目的地永不過期。
1. Click **[!UICONTROL Done]**.

## 新增或編輯伺服器至伺服器目的地的區段 {#add-edit-segments}

您只能新增或編輯伺服器至伺服器([!DNL S2S])目的地的區段。您無法建立 [!DNL S2S][!UICONTROL Destination Builder]目標。請連絡您的顧問以設定 [!DNL S2S] 目的地。請依照下列指示，新增或編輯 [!DNL S2S] 目的地的區段。

<!-- destination-s2s-edit.xml -->

若要新增或編輯 [!DNL S2S] 目的地的區段映射：

1. **[!UICONTROL Audience Data > Destinations]**&#x200B;前往。選取 **「整合平台&gt;裝置型** 」並尋找您想要使用的 [!DNL S2S] 目標。
2. [!UICONTROL Action] 在欄中，按一下鉛筆圖示以編輯目的地。
   * **[!UICONTROL Search and Add Segments]** 在方塊中，開始鍵入區段名稱，或按一下 **[!UICONTROL Browse All Segments]** 可瀏覽可用區段清單。
   * 當 **[!UICONTROL Add Selected Segments]** 您尋找要使用的區段時，按一下。新增區段會開啓 [!UICONTROL Edit Mapping] 視窗。
   * 在 [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**：為此目的地使用 [的索引鍵值配對](../../features/destinations/key-value-pairs.md) 設定值。
      * **[!UICONTROL Start Date]** and **[!UICONTROL End Date]**：選擇目的地的開始和結束日期。如果結束日期空白，目的地永不過期。
3. 按一下 **[!UICONTROL Save]** 然後按 **[!UICONTROL Done]**&#x200B;一下。

## 將資料匯出標籤新增至目的地 {#add-data-export-labels}

[!DNL Data Export Labels] 與 [!DNL Export Controls] 您在資料來源上設定的作業相同。[!DNL Data Export Labels] 防止您將受限制的特性新增至區段，以及將區段資料傳送至目的地。您可以將多個匯出標籤設定為新或現有 [!DNL cookie][!DNL URL] 或目的地。

>[!NOTE]
>
>若要新增匯出標籤，您需要管理員權限 *或* 足夠權限來建立或編輯目的地。

<!-- t_export_labels.xml -->

若要將匯出標籤新增至目的地：

1. Click **[!UICONTROL Audience Data]**:
   * 對於新目的地：按一 **[!UICONTROL Create New Destination]**&#x200B;下。請先完成 [!UICONTROL Basic Information] 區段，然後再選擇資料匯出標籤。如需詳細資訊，請參閱 [建立Cookie目的地](../../features/destinations/manage-destinations.md#create-cookie-destination) 或 [建立URL目的地](../../features/destinations/manage-destinations.md#configure-url-destination) 。
   * 對於現有目的地：使用 [!DNL Search] 方塊尋找目的地或捲動清單，然後按一下目的地名稱以開啓它。
1. 選擇 [!DNL Data Export Label]. 如果您不想設定任何匯出限制，請將核取方塊保留空白。匯出標籤包含下列選項：
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >除非您對資料來源設定 [相符的匯出控制](../../features/data-export-controls.md) ，否則匯出限制將無法運作。
1. Click **[!UICONTROL Save]**.

>[!MORE_贊_ this]
>
>* [建立資料來源](../../features/manage-datasources.md#create-data-source)

