---
description: 將Open Ad Server設為目的地，並傳送Audience Manager資料至該平台。
seo-description: 將Open Ad Server設為目的地，並傳送Audience Manager資料至該平台。
seo-title: OAS 作為 Audience Manager 目的地
solution: Audience Manager
title: OAS 作為 Audience Manager 目的地
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: 協力廠商整合
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 4%

---

# OAS 作為 Audience Manager 目的地 {#oas-as-an-audience-manager-destination}

將[!DNL Open Ad Server]設為目的地，並傳送Audience Manager資料至該平台。

## OAS目標要求{#oas-requirements}

程式碼放置、支援的鍵值格式、報表，以及傳送至[!DNL OAS]的區段資料類型的標準。

<!-- aam-oas-requirements.xml -->

此目的地類型需要下列項目：

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] 程式碼應部署在詳細目錄中。[!UICONTROL DIL] 有助於避免編寫特殊程式碼以用於資料收集、整合、讀取cookie值及恢復頁面資料的需求。
* **`get_aamCookie`函式：** 擷取Audience Manager使用者ID和Cookie資料的程式碼。將[此代碼](../../features/destinations/get-aam-cookie-code.md)放置在頁面頂端或`<head>`程式碼塊內。
* **傳送傳送記錄檔至Audience Manager:** 如果您想要區段傳送報表（選用），請為Audience Manager提供包含曝光層級傳送資料的每日記錄檔。資料可以是原始格式，但每個記錄必須包含Audience Manager[!UICONTROL UUID]。 Audience Manager可以透過[!DNL FTP]接收這些檔案。

### Cookie格式和索引鍵值資料

Audience Manager可依下列方式傳送區段資料至瀏覽器Cookie:

* 單鍵(`x=1&x=2`);
* 多鍵(`x=1&x=2&y=3&y=4`);
* 序列化值(`x=1,2,3`);
* 用來分隔個別索引鍵值配對的標準值分隔字元。

### 只有合格的段才會發送到OAS

傳遞至[!DNL OAS]的資料量取決於特定使用者符合的區段數。 例如，假設您設定100個Audience Manager區段。 如果網站訪客符合其中5個的資格，則只有這5個區段會傳送至OAS（並非全部100個）。

>[!MORELIKETHIS]
>
>* [get_aamCookie 程式碼](../../features/destinations/get-aam-cookie-code.md)
* [索引鍵值配對說明](../../reference/key-value-pairs-explained.md)


## 建立OAS目標{#oas-dest-setup}

在Audience Manager中為[!DNL OAS]建立Cookie型目的地。

<!-- aam-oas-destination-setup.xml -->

在Audience Manager中，*destination*&#x200B;是任何其他系統（廣告伺服器、[!DNL DSP]、廣告網路等） 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder] 提供可讓您建立和管理這些資料傳送程式的工具。Audience Manager目的地功能位於&#x200B;*受眾資料>目的地*&#x200B;中。 若要開始使用，請按一下&#x200B;**[!UICONTROL Add New Destination]**&#x200B;並遵循下列步驟。

### 步驟1:基本資訊

要完成[!UICONTROL Basic Information]部分：

1. 為目的地命名。
1. 從[!UICONTROL Type]下拉清單中選擇&#x200B;**[!UICONTROL "Cookie"]**。
1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;並移至[!UICONTROL Configuration]和[!UICONTROL Segment Mappings]區段。

### 步驟2:配置資訊

要完成[!UICONTROL Configuration]部分：

1. **Cookie名稱：** 為您的Cookie提供簡短的描述性名稱。
1. **Cookie網域：** 留空可在使用者目前頁面的網域中設定Cookie。如果要指定域，請在名稱前加上類似`.mydomain.com`的句號。
1. 在[!UICONTROL Data Format]區段中選擇鍵選項。
1. 如果您的鍵使用具有序列化值的資料，請選擇&#x200B;**[!UICONTROL Serialize]**&#x200B;控制項並指定序列分隔符（分隔序列化值的字元）。
1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;並展開[!UICONTROL Segment Mappings]區段。

### 步驟3:區段對應

若要新增區段至Cookie目的地：

1. **尋找區段：** 區段提 [!UICONTROL Segment Mappings] 供兩種搜尋工具，以協助找出區段。若要尋找區段：
   * 選項1:開始在搜尋欄位中輸入區段名稱。 欄位會根據文字自動更新。 找到您要使用的區段後，按一下&#x200B;**[!UICONTROL Add]**。
   * 選項2:按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;以開啟一個視窗，讓您依名稱或儲存位置瀏覽區段。 完成後，按一下&#x200B;**[!UICONTROL Add Selected Segments]**。
1. **新增對應：** 在對應快顯視窗中，在對應欄位中輸入區段ID，然後按一下 **[!UICONTROL Save]**。
1. 按一下 **[!UICONTROL Done]**.

## OAS設定{#oas-code-setup}

修改[!DNL OAS]設定以使用Audience Manager區段資料。

<!-- aam-oas-code.xml -->

設定[!DNL OAS]

* 在您的網站上安裝[!UICONTROL DIL]程式碼。
* 將OAS建立為Audience Manager中的Cookie目的地。
* 將`get_aamCookie`函式放置在頁面頂端，理想地放在`<head>`程式碼鎖中。 `get_aamCookie`代碼可用於[此處](../../features/destinations/get-aam-cookie-code.md)。
* 修改您的廣告標籤以呼叫`get_aamCookie`函式，並納入您在設定[!DNL OAS]目的地時提供的Cookie名稱。 例如，如果您將Cookie命名為`test_cookie`，則廣告標籤應呼叫`get_aamCookie`並參考Cookie名稱。
* 您的廣告標籤看起來可能類似於下列範例。

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

請記得加入`u=`變數。 它保有廣告呼叫期間傳入的實際唯一使用者ID([!UICONTROL UUID])。
