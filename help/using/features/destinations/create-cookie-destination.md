---
description: Cookie目的地會傳回資料，並將資料寫入使用者瀏覽器中的Cookie。 Cookie包含可供存取頁面之其他平台讀取的資料。 請依照下列指示，使用[!UICONTROL Destination Builder]建立Cookie目的地。
seo-description: Cookie目的地會傳回資料，並將資料寫入使用者瀏覽器中的Cookie。 Cookie包含可供存取頁面之其他平台讀取的資料。 請依照下列指示，使用[!UICONTROL Destination Builder]建立Cookie目的地。
seo-title: 設定 Cookie 目的地
solution: Audience Manager
title: 設定 Cookie 目的地
feature: 目的地基本知識
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 3%

---

# 設定 Cookie 目的地 {#create-cookie-destination}

Cookie目的地會傳回資料，並將資料寫入使用者瀏覽器中的Cookie。 Cookie包含可供存取頁面之其他平台讀取的資料。 請依照下列指示，使用[!UICONTROL Destination Builder]建立Cookie目的地。

<!-- create-cookie-destination.xml -->

若要建立新的Cookie目的地，請前往&#x200B;**[!UICONTROL Audience Data > Destinations > Create New Destination]**&#x200B;並完成以下所述的區段。

## 基本資訊 {#basic-information}

本節包含啟動Cookie目的地建立程式的欄位和選項。 要完成此部分：

1. 按一下&#x200B;**[!UICONTROL Basic Information]**&#x200B;以公開控制項。
2. 為目的地命名。 避免縮寫和特殊字元。
3. *（選用）* 說明目的地。簡潔的說明是定義或提供目的地詳細資訊的有效方式。
4. 在&#x200B;**[!UICONTROL Category]**&#x200B;清單中，選擇&#x200B;**[!UICONTROL Custom]**。
5. 在&#x200B;**[!UICONTROL Environment]**&#x200B;清單中，選擇&#x200B;**[!UICONTROL Browser]**。 您無法為原生行動環境（例如Android或iOS應用程式）設定Cookie目的地。
6. 在&#x200B;**[!UICONTROL Type]**&#x200B;清單中，按一下&#x200B;**[!UICONTROL Cookie]**。
7. *（選用）* 選取 **[!UICONTROL Auto-fill Destination Mapping]**。選項包括:
   * **[!UICONTROL Segment ID]**:自動新增區段ID並傳送至目的地。
   * **[!UICONTROL Integration Code Value]**:自動新增區段整合代碼，並將其傳送至目的地對應。整合代碼是客戶建立和使用的唯一識別碼。 上限為255個字元，上限為。
8. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;前往[!UICONTROL Configuration]設定，或按一下&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;將匯出控制套用至目的地。

## 資料導出標籤{#data-export-labels-cookies}

本節包含將[資料匯出控制項](../../features/data-export-controls.md)套用至Cookie目的地的選項。 如果您不使用資料匯出控制，請略過此步驟。 要完成此部分：

1. 按一下&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;以公開控制項。
2. 選取與套用至目的地的資料匯出控制相對應的標籤（如需詳細資訊，請參閱[將匯出標籤新增至目的地](/help/using/features/destinations/add-data-export-labels.md)）。
3. 按一下 **[!UICONTROL Save]**.

## 設定 {#configuration}

此區段包含可讓您設定目的地Cookie的欄位和選項。

>[!NOTE]
>
>[!DNL Audience Manager] 對寫入目的地cookie的資料進行編碼。例如，空格會編碼為`%20`，分號會編碼為`%3B`。

要完成此部分：

1. 按一下&#x200B;**[!UICONTROL Configuration]**&#x200B;以公開控制項
1. 為Cookie命名。 避免縮寫和特殊字元。
1. 選擇資料格式選項。 這些選項可讓您為將區段資料傳送至目的地的鍵值值組選擇分隔字元和分隔符號。 格式選項包括：
   * **單一索引鍵：** 可讓您以索引鍵值組設定索引鍵。在下方的[!UICONTROL Segment Mappings]區段中選取區段後，即可設定值。
   * **多索引鍵：** 可讓您設定索引鍵值組的索引鍵和值。在下方的「區段對應」區段中選取區段後，您將建立索引鍵值組。
如需這些資料元素的詳細資訊，請參閱[標準和串列索引鍵值配對](../../features/destinations/key-value-pairs.md) 。
1. 按一下 **[!UICONTROL Save]**.

所有其他設定均為選用。 如需&#x200B;**[!UICONTROL Cookie Domain]**&#x200B;和&#x200B;**[!UICONTROL Publish data to]**&#x200B;設定的詳細資訊，請參閱Cookie目的地的[選用設定](/help/using/features/destinations/cookie-destination-options.md)。

## 區段對應{#segments-mapping}

本節可讓您搜尋區段並新增至目的地。 要完成此部分：

1. 按一下&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;以公開控制項。
1. 在&#x200B;**[!UICONTROL Search and Add Segments]**&#x200B;方塊中，開始輸入區段名稱，或按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;以瀏覽可用區段的清單。
1. 找到您要使用的區段時，按一下&#x200B;**[!UICONTROL Add Selected Segments]**。 新增區段會開啟[!UICONTROL Edit Mapping]視窗。
1. 在[!UICONTROL Edit Mapping]對話方塊中：
   * **[!UICONTROL Mapping]** 可讓您為上述「設定」區段中指定的金鑰設定值。
   * **[!UICONTROL Publish from]** 可讓您設定目的地的開始和結束日期。如果結束日期空白，目的地永不過期。
1. 按一下 **[!UICONTROL Save]**.
1. 按一下 **[!UICONTROL Done]**.
