---
description: Cookie目的地會傳回資料，並將資料寫入使用者瀏覽器中的Cookie。 Cookie包含可供其他平台讀取的資料，這些平台可存取頁面。 請依照下列指示，建立具有[!UICONTROL Destination Builder]的Cookie目的地。
seo-description: Cookie目的地會傳回資料，並將資料寫入使用者瀏覽器中的Cookie。 Cookie包含可供其他平台讀取的資料，這些平台可存取頁面。 請依照下列指示，建立具有[!UICONTROL Destination Builder]的Cookie目的地。
seo-title: 設定 Cookie 目的地
solution: Audience Manager
title: 設定 Cookie 目的地
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 3%

---


# 設定 Cookie 目的地 {#create-cookie-destination}

Cookie目的地會傳回資料，並將資料寫入使用者瀏覽器中的Cookie。 Cookie包含可供其他平台讀取的資料，這些平台可存取頁面。 請依照下列指示，建立具有[!UICONTROL Destination Builder]的Cookie目的地。

<!-- create-cookie-destination.xml -->

若要建立新的Cookie目標，請前往&#x200B;**[!UICONTROL Audience Data > Destinations > Create New Destination]**&#x200B;並依照下述說明完成章節。

## 基本資訊 {#basic-information}

此區段包含開始建立Cookie目標程式的欄位和選項。 要完成本節：

1. 按一下&#x200B;**[!UICONTROL Basic Information]**&#x200B;以公開控制項。
2. 命名目標。 避免縮寫和特殊字元。
3. *（可選）* 描述目標。簡明的描述是定義或提供目標更多資訊的有效方式。
4. 在&#x200B;**[!UICONTROL Category]**&#x200B;清單中，選擇&#x200B;**[!UICONTROL Custom]**。
5. 在&#x200B;**[!UICONTROL Environment]**&#x200B;清單中，選擇&#x200B;**[!UICONTROL Browser]**。 您無法為原生行動環境（例如Android或iOS應用程式）設定Cookie目標。
6. 在&#x200B;**[!UICONTROL Type]**&#x200B;清單中，按一下&#x200B;**[!UICONTROL Cookie]**。
7. *（可選）* 選取 **[!UICONTROL Auto-fill Destination Mapping]**。選項包括:
   * **[!UICONTROL Segment ID]**:自動新增區段ID並傳送至目標。
   * **[!UICONTROL Integration Code Value]**:自動新增區段整合代碼並傳送至目標對應。整合程式碼是客戶建立和使用的唯一識別碼。 最多限制為255個字元。
8. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;移至[!UICONTROL Configuration]設定，或按一下&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;將匯出控制項套用至目標。

## 資料導出標籤{#data-export-labels-cookies}

本節包含將[資料匯出控制](../../features/data-export-controls.md)套用至Cookie目的地的選項。 如果您不使用資料匯出控制，請略過此步驟。 要完成本節：

1. 按一下&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;以公開控制項。
2. 選擇與應用於目標的資料導出控制相對應的標籤（有關詳細資訊，請參閱[將導出標籤添加到目標](/help/using/features/destinations/add-data-export-labels.md)）。
3. 按一下 **[!UICONTROL Save]**.

## 設定 {#configuration}

此區段包含欄位和選項，可讓您設定目標的Cookie。

>[!NOTE]
>
>[!DNL Audience Manager] 對寫入目標Cookie的資料進行編碼。例如，空格編碼為`%20`，分號編碼為`%3B`。

要完成本節：

1. 按一下&#x200B;**[!UICONTROL Configuration]**&#x200B;以公開控制項
1. 命名Cookie。 避免縮寫和特殊字元。
1. 選擇資料格式選項。 這些選項可讓您為傳送區段資料至目的地的鍵值對選擇分隔字元和分隔字元。 格式選項包括：
   * **單鍵：** 可讓您在鍵值對中設定鍵。在下方的[!UICONTROL Segment Mappings]區段中選取區段後，您會設定值。
   * **多鍵：** 可讓您設定鍵值配對的鍵和值。在下方的「區段對應」區段中選取區段後，您將建立索引鍵值對。
如需這些資料元素的詳細資訊，請參閱[標準和串列金鑰值配對](../../features/destinations/key-value-pairs.md)。
1. 按一下 **[!UICONTROL Save]**.

所有其他設定都是選用的。 如需&#x200B;**[!UICONTROL Cookie Domain]**&#x200B;和&#x200B;**[!UICONTROL Publish data to]**&#x200B;設定的詳細資訊，請參閱[ Cookie目標的選用設定](/help/using/features/destinations/cookie-destination-options.md)。

## 區段映射{#segments-mapping}

此區段可讓您搜尋區段並新增至目標。 要完成本節：

1. 按一下&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;以公開控制項。
1. 在&#x200B;**[!UICONTROL Search and Add Segments]**&#x200B;方塊中，開始輸入區段的名稱，或按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;以瀏覽可用區段的清單。
1. 當您找到要使用的區段時，按一下&#x200B;**[!UICONTROL Add Selected Segments]**。 新增區段會開啟[!UICONTROL Edit Mapping]視窗。
1. 在[!UICONTROL Edit Mapping]對話方塊中：
   * **[!UICONTROL Mapping]** 可讓您為上述「設定」區段中指定的索引鍵設定值。
   * **[!UICONTROL Publish from]** 可讓您設定目標的開始和結束日期。如果結束日期空白，則目標不會過期。
1. 按一下 **[!UICONTROL Save]**.
1. 按一下 **[!UICONTROL Done]**.