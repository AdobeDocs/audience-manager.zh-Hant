---
description: 將Open Ad Server設定為目標，並傳送Audience Manager資料至該平台。
seo-description: 將Open Ad Server設定為目標，並傳送Audience Manager資料至該平台。
seo-title: OAS 作為 Audience Manager 目的地
solution: Audience Manager
title: OAS 作為 Audience Manager 目的地
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: 協力廠商整合
exl-id: cf919c27-691f-424b-be83-040f03e34455
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 4%

---

# OAS 作為 Audience Manager 目的地 {#oas-as-an-audience-manager-destination}

將[!DNL Open Ad Server]設為目標，並傳送Audience Manager資料至該平台。

## OAS目標要求{#oas-requirements}

程式碼放置標準、支援的關鍵值格式、報告，以及傳送至[!DNL OAS]的區段資料類型。

<!-- aam-oas-requirements.xml -->

此目標類型需要：

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] 程式碼應部署在您的庫存中。[!UICONTROL DIL] 協助您免除撰寫資料收集、整合、讀取Cookie值和復原頁面資料的特殊程式碼。
* **`get_aamCookie`函式：** 擷取Audience Manager使用者ID和Cookie資料的程式碼。將[此程式碼](../../features/destinations/get-aam-cookie-code.md)置於頁面頂端或`<head>`程式碼鎖定內。
* **傳送傳送記錄檔至Audience Manager:** 如果您想要區段傳送報表（選用），請為Audience Manager提供包含印象層級傳送資料的每日記錄檔。資料可以是原始格式，但每個記錄必須包含Audience Manager[!UICONTROL UUID]。 Audience Manager可以通過[!DNL FTP]接收這些檔案。

### Cookie格式與金鑰值資料

Audience Manager可依下列方式傳送區段資料至瀏覽器Cookie:

* 單鍵(`x=1&x=2`);
* 多鍵(`x=1&x=2&y=3&y=4`);
* 序列化值(`x=1,2,3`);
* 用於分隔個別索引鍵值對的標準值分隔字元。

### 僅將限定的段發送到OAS

傳入至[!DNL OAS]的資料量取決於特定使用者符合的區段數。 例如，假設您設定了100個Audience Manager區段。 如果某位網站訪客符合其中5個區段的資格，則只有這5個區段會傳送至OAS（並非全部100個）。

>[!MORELIKETHIS]
>
>* [get_aamCookie 程式碼](../../features/destinations/get-aam-cookie-code.md)
>* [索引鍵值配對說明](../../reference/key-value-pairs-explained.md)


## 建立OAS目標{#oas-dest-setup}

在Audience Manager中為[!DNL OAS]建立以Cookie為基礎的目的地。

<!-- aam-oas-destination-setup.xml -->

在Audience Manager中，*目標*&#x200B;是任何其他系統（廣告伺服器、[!DNL DSP]廣告網路等） 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder] 提供可讓您建立和管理這些資料傳送程式的工具。Audience Manager目標功能位於&#x200B;*觀眾資料>目標*。 若要開始，請按一下&#x200B;**[!UICONTROL Add New Destination]**，然後遵循下列步驟。

### 步驟1:基本資訊

要完成[!UICONTROL Basic Information]部分：

1. 命名目標。
1. 從[!UICONTROL Type]下拉式清單中選取&#x200B;**[!UICONTROL "Cookie"]**。
1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;並移至[!UICONTROL Configuration]和[!UICONTROL Segment Mappings]部分。

### 步驟2:配置資訊

要完成[!UICONTROL Configuration]部分：

1. **Cookie名稱：** 為您的Cookie提供簡短、描述性的名稱。
1. **Cookie網域：** 留空可在使用者目前頁面的網域中設定Cookie。如果要指定域，請在名稱前加上此句點`.mydomain.com`。
1. 在[!UICONTROL Data Format]節中選擇一個鍵選項。
1. 如果您的索引鍵使用含序號值的資料，請選取&#x200B;**[!UICONTROL Serialize]**&#x200B;控制項並指定序號分隔字元（分隔序號值的字元）。
1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;並展開[!UICONTROL Segment Mappings]部分。

### 步驟3:區段對應

若要新增區段至Cookie目標：

1. **尋找區段：** 此區 [!UICONTROL Segment Mappings] 段提供兩種搜尋工具，以協助尋找區段。若要尋找區段：
   * 選項1:開始在搜尋欄位中輸入區段名稱。 欄位會根據文字自動更新。 找到要使用的區段後，按一下&#x200B;**[!UICONTROL Add]**。
   * 選項2:按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;以開啟一個視窗，讓您依名稱或儲存位置瀏覽區段。 完成後，按一下&#x200B;**[!UICONTROL Add Selected Segments]**。
1. **新增對應：** 在映射快顯視窗中，在映射欄位中輸入區段ID，然後按一下 **[!UICONTROL Save]**。
1. 按一下 **[!UICONTROL Done]**.

## OAS設定{#oas-code-setup}

修改[!DNL OAS]設定以處理Audience Manager段資料。

<!-- aam-oas-code.xml -->

若要設定[!DNL OAS]

* 在您的網站上安裝[!UICONTROL DIL]程式碼。
* 在Audience Manager中將OAS建立為Cookie目標。
* 將`get_aamCookie`函式置於頁面頂端，最好是置於`<head>`程式碼鎖定中。 `get_aamCookie`程式碼位於[這裡](../../features/destinations/get-aam-cookie-code.md)。
* 修改您的廣告標籤以呼叫`get_aamCookie`函式，並包含您在設定[!DNL OAS]目標時提供的Cookie名稱。 例如，如果您命名Cookie `test_cookie`，則廣告標籤應呼叫`get_aamCookie`並參考Cookie名稱。
* 您的廣告標籤看起來可能類似於下列範例。

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

請記得包含`u=`變數。 它包含廣告呼叫期間傳入的實際唯一使用者ID([!UICONTROL UUID])。
