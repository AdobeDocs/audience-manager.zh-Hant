---
description: Cookie目的地會傳回並寫入使用者瀏覽器中的Cookie。Cookie包含可供存取頁面之其他平台讀取的資料。請依照下列指示來建立Cookie目的地：UICOHTROL目標產生器]。
seo-description: Cookie目的地會傳回並寫入使用者瀏覽器中的Cookie。Cookie包含可供存取頁面之其他平台讀取的資料。請依照下列指示來建立Cookie目的地：UICOHTROL目標產生器]。
seo-title: 設定Cookie目的地
solution: Audience Manager
title: 設定Cookie目的地
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# 設定Cookie目的地 {#create-cookie-destination}

Cookie目的地會傳回並寫入使用者瀏覽器中的Cookie。Cookie包含可供存取頁面之其他平台讀取的資料。請依照下列指示建立Cookie目的地。[!UICONTROL Destination Builder]

<!-- create-cookie-destination.xml -->

若要建立新的Cookie目的地，請前往 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 並完成章節，如下所述。

## 基本資訊 {#basic-information}

本節包含開始Cookie目的地建立程序的欄位和選項。若要完成本節：

1. 按一下 **[!UICONTROL Basic Information]** 以公開控制項。
2. 命名目的地。避免縮寫和特殊字元。
3. *(選擇性)* 說明目的地。簡明扼要的說明是定義或提供目標的更多資訊。
4. 在 **[!UICONTROL Category]** 清單中選擇 **[!UICONTROL Custom]**。
5. 在 **[!UICONTROL Environment]** 清單中選取 **[!UICONTROL Browser]**。您無法針對原生行動環境(例如Android或iOS應用程式)設定Cookie目的地。
6. 在 **[!UICONTROL Type]** 清單中，按 **[!UICONTROL Cookie]**&#x200B;一下。
7. *(選擇性)* 選擇 **[!UICONTROL Auto-fill Destination Mapping]**&#x200B;一個。選項包括:
   * **[!UICONTROL Segment ID]**：自動新增區段ID並傳送至目的地。
   * **[!UICONTROL Integration Code Value]**：自動新增區段整合代碼並傳送至目的地對應。整合代碼是客戶建立並使用的唯一識別碼。僅限255個字元上限。
8. 按一下 **[!UICONTROL Next]** 以前往 [!UICONTROL Configuration] 設定或按一下 **[!UICONTROL Data Export Labels]** ，將匯出控制套用至目的地。

## 資料匯出標籤 {#data-export-labels-cookies}

本節包含將 [資料匯出控制](../../features/data-export-controls.md) 套用至Cookie目的地的選項。如果您不使用資料匯出控制，請跳過此步驟。若要完成本節：

1. 按一下 **[!UICONTROL Data Export Labels]** 以公開控制項。
2. 選取與套用至目的地的資料匯出控制相對應的標籤(請參閱 [「將匯出標籤新增至目的地](/help/using/features/destinations/add-data-export-labels.md) 」)。
3. Click **[!UICONTROL Save]**.

## 設定 {#configuration}

本節包含可讓您設定目的地Cookie的欄位和選項。

>[!NOTE]
>
>[!DNL Audience Manager] 對寫入目的地Cookie的資料進行編碼。例如，空格編碼 `%20` 為與分號編碼 `%3B`。

若要完成本節：

1. 按一下 **[!UICONTROL Configuration]** 以公開控制項
1. 命名Cookie。避免縮寫和特殊字元。
1. 選擇資料格式選項。這些選項可讓您為將區段資料傳送至目的地的索引鍵值配對選擇分隔字元和分隔符號。格式選項包括：
   * **單一索引鍵：** 可讓您將索引鍵設定為索引鍵值配對。在下一 [!UICONTROL Segment Mappings] 節中選取區段後，您將會設定此值。
   * **多索引鍵：** 可讓您設定索引鍵值配對的索引鍵和值。在下方「區段對應」區段中選取區段後，您將建立索引鍵值配對。
如需這些資料元素的詳細資訊，請參閱 [標準和序列金鑰-值配對](../../features/destinations/key-value-pairs.md) 。
1. Click **[!UICONTROL Save]**.

所有其他設定皆為選用。如需有關和 **[!UICONTROL Cookie Domain]****[!UICONTROL Publish data to]** 設定的詳細資訊，請參閱 [「Cookie目的地的選擇性設定](/help/using/features/destinations/cookie-destination-options.md)」。

## 區段映射 {#segments-mapping}

此區段可讓您搜尋並新增區段至目的地。若要完成本節：

1. 按一下 **[!UICONTROL Segment Mappings]** 以公開控制項。
1. **[!UICONTROL Search and Add Segments]** 在方塊中，開始鍵入區段名稱，或按一下 **[!UICONTROL Browse All Segments]** 以瀏覽可用區段清單。
1. 當 **[!UICONTROL Add Selected Segments]** 您尋找要使用的區段時，按一下。新增區段會開啓 [!UICONTROL Edit Mapping] 視窗。
1. [!UICONTROL Edit Mapping] 在對話方塊中：
   * **[!UICONTROL Mapping]** 可讓您設定上方「設定」一節中指定之索引鍵的值。
   * **[!UICONTROL Publish from]** 可讓您設定目的地的開始和結束日期。如果結束日期空白，目的地永不過期。
1. Click **[!UICONTROL Save]**.
1. Click **[!UICONTROL Done]**.