---
description: Cookie目的地會傳回資料，並將資料寫入使用者瀏覽器中的Cookie。 Cookie包含可由具有頁面存取許可權的其他平台讀取的資料。 請依照這些指示，使用[!UICONTROL Destination Builder]建立Cookie目的地。
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: 設定Cookie目的地
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 1%

---

# 設定Cookie目的地 {#create-cookie-destination}

Cookie目的地會傳回資料，並將資料寫入使用者瀏覽器中的Cookie。 Cookie包含可由具有頁面存取許可權的其他平台讀取的資料。 請依照這些指示，使用[!UICONTROL Destination Builder]建立Cookie目的地。

<!-- create-cookie-destination.xml -->

若要建立新的Cookie目的地，請移至&#x200B;**[!UICONTROL Audience Data > Destinations > Create New Destination]**&#x200B;並完成以下所述的區段。

## 基本資訊 {#basic-information}

本節包含啟動Cookie目的地建立程式的欄位和選項。 若要完成本節：

1. 按一下&#x200B;**[!UICONTROL Basic Information]**&#x200B;以公開控制項。
2. 為目的地命名。 避免使用縮寫和特殊字元。
3. *（選擇性）*&#x200B;說明目的地。 簡潔的說明是定義或提供更多目的地相關資訊的有效方式。
4. 在&#x200B;**[!UICONTROL Category]**&#x200B;清單中選擇&#x200B;**[!UICONTROL Custom]**。
5. 在&#x200B;**[!UICONTROL Environment]**&#x200B;清單中，選取&#x200B;**[!UICONTROL Browser]**。 您無法為原生行動環境(例如Android或iOS應用程式)設定Cookie目的地。
6. 在&#x200B;**[!UICONTROL Type]**&#x200B;清單中，按一下&#x200B;**[!UICONTROL Cookie]**。
7. *（選擇性）*&#x200B;選取&#x200B;**[!UICONTROL Auto-fill Destination Mapping]**。 選項包括:
   * **[!UICONTROL Segment ID]**：自動新增區段ID並傳送至目的地。
   * **[!UICONTROL Integration Code Value]**：自動新增區段整合代碼，並將其傳送到目的地對應。 整合代碼是客戶建立及使用的唯一識別碼。 上限為255個字元。
8. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;以移至[!UICONTROL Configuration]設定，或按一下&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;以套用匯出控制項至目的地。

## 資料匯出標籤 {#data-export-labels-cookies}

此區段包含將[資料匯出控制項](../../features/data-export-controls.md)套用至Cookie目的地的選項。 如果您不使用資料匯出控制項，請略過此步驟。 若要完成本節：

1. 按一下&#x200B;**[!UICONTROL Data Export Labels]**&#x200B;以公開控制項。
2. 選取與套用至目的地的資料匯出控制對應的標籤（如需詳細資訊，請參閱[新增匯出標籤至目的地](/help/using/features/destinations/add-data-export-labels.md)）。
3. 按一下 **[!UICONTROL Save]**。

## 設定 {#configuration}

本節包含可讓您為目的地設定Cookie的欄位和選項。

>[!NOTE]
>
>[!DNL Audience Manager]會對寫入目的地Cookie的資料進行編碼。 例如，空格會編碼為`%20`，分號會編碼為`%3B`。

若要完成本節：

1. 按一下&#x200B;**[!UICONTROL Configuration]**&#x200B;以公開控制項
1. 為Cookie命名。 避免使用縮寫和特殊字元。
1. 選擇資料格式選項。 這些選項可讓您為將區段資料傳送至目的地的機碼值組選擇分隔符號和分隔符號。 格式選項包括：
   * **單一索引鍵：**&#x200B;可讓您在索引鍵/值配對中設定索引鍵。 在下方的[!UICONTROL Segment Mappings]區段中選取區段後，您將設定值。
   * **多重索引鍵：**&#x200B;可讓您設定索引鍵/值組的索引鍵和值。 在下面的「區段對應」區段中選取區段後，您會建立索引鍵/值組。
如需這些資料元素的詳細資訊，請參閱[標準和序列索引鍵值配對](../../features/destinations/key-value-pairs.md)。
1. 按一下 **[!UICONTROL Save]**。

所有其他設定都是選用的。 如需&#x200B;**[!UICONTROL Cookie Domain]**&#x200B;和&#x200B;**[!UICONTROL Publish data to]**&#x200B;設定的詳細資訊，請參閱[Cookie目的地的選用設定](/help/using/features/destinations/cookie-destination-options.md)。

## 區段對應 {#segments-mapping}

本節可讓您搜尋區段，並將其新增至您的目的地。 若要完成本節：

1. 按一下&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;以公開控制項。
1. 在&#x200B;**[!UICONTROL Search and Add Segments]**&#x200B;方塊中，開始輸入區段名稱，或按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;瀏覽可用區段清單。
1. 當您找到要使用的區段時，請按一下&#x200B;**[!UICONTROL Add Selected Segments]**。 新增區段會開啟[!UICONTROL Edit Mapping]視窗。
1. 在[!UICONTROL Edit Mapping]對話方塊：
   * **[!UICONTROL Mapping]**&#x200B;可讓您設定以上[設定]區段中指定之金鑰的值。
   * **[!UICONTROL Publish from]**&#x200B;可讓您設定目的地的開始和結束日期。 如果結束日期為空白，目的地永遠不會過期。
1. 按一下 **[!UICONTROL Save]**。
1. 按一下 **[!UICONTROL Done]**。
