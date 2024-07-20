---
description: 將Open Ad Server設定為目的地，並將Audience Manager資料傳送至該平台。
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS作為Audience Manager目的地
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 2%

---

# OAS作為Audience Manager目的地 {#oas-as-an-audience-manager-destination}

將[!DNL Open Ad Server]設定為目的地，並將Audience Manager資料傳送至該平台。

## OAS目的地需求 {#oas-requirements}

程式碼放置的標準、支援的鍵值格式、報表，以及傳送給[!DNL OAS]的區段資料型別。

<!-- aam-oas-requirements.xml -->

此目的地型別需要下列專案：

* **[!UICONTROL DIL]：** [!UICONTROL Data Integration Library]程式碼應部署在您的詳細目錄上。 [!UICONTROL DIL]可協助您免除撰寫特殊程式碼以進行資料收集、整合、讀取Cookie值以及復原頁面資料等作業。
* **`get_aamCookie`函式：**&#x200B;擷取Audience Manager使用者ID和Cookie資料的程式碼。 將[此程式碼](../../features/destinations/get-aam-cookie-code.md)放在頁面頂端或`<head>`程式碼區塊內。
* **傳送傳遞記錄給Audience Manager：**&#x200B;如果您想要區段傳遞報告（選擇性），請為Audience Manager提供包含曝光層級傳遞資料的每日記錄。 資料可以是原始格式，但每個記錄都必須包含Audience Manager[!UICONTROL UUID]。 Audience Manager可以透過[!DNL FTP]收取或接收這些專案。

### Cookie格式和索引鍵值資料

Audience Manager可將區段資料傳送至瀏覽器Cookie，如下所示：

* 單一金鑰(`x=1&x=2`)；
* 多個金鑰(`x=1&x=2&y=3&y=4`)；
* 序列化值(`x=1,2,3`)；
* 用來分隔個別索引鍵/值組的標準值分隔字元。

### 只有合格的區段才會傳送至OAS

傳入[!DNL OAS]的資料量取決於特定使用者符合的區段數。 例如，假設您設定100個Audience Manager區段。 如果網站訪客符合其中五個區段的資格，則只會將這五個區段傳送至OAS （並非全部100個區段）。

>[!MORELIKETHIS]
>
>* [get_aamCookie 程式碼](../../features/destinations/get-aam-cookie-code.md)
>* [索引鍵值配對說明](../../reference/key-value-pairs-explained.md)

## 建立OAS目的地 {#oas-dest-setup}

在Audience Manager中為[!DNL OAS]建立Cookie型目的地。

<!-- aam-oas-destination-setup.xml -->

在Audience Manager中，*目的地*&#x200B;是任何其他系統（廣告伺服器、[!DNL DSP]、廣告網路等） 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder]提供可讓您建立和管理這些資料傳遞程式的工具。 Audience Manager目的地功能位於&#x200B;*對象資料>目的地*。 若要開始使用，請按一下&#x200B;**[!UICONTROL Add New Destination]**&#x200B;並遵循下列步驟。

### 步驟1：基本資訊

若要完成[!UICONTROL Basic Information]區段：

1. 為目的地命名。
1. 從[!UICONTROL Type]下拉式清單中選取&#x200B;**[!UICONTROL "Cookie"]**。
1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;並移至[!UICONTROL Configuration]與[!UICONTROL Segment Mappings]區段。

### 步驟2：設定資訊

若要完成[!UICONTROL Configuration]區段：

1. **Cookie名稱：**&#x200B;為您的Cookie提供簡短描述性名稱。
1. **Cookie網域：**&#x200B;留空可在使用者目前頁面的網域中設定Cookie。 如果您要指定網域，請在名稱前面加上句點，如`.mydomain.com`。
1. 在[!UICONTROL Data Format]區段中選擇索引鍵選項。
1. 如果您的金鑰使用具有序列化值的資料，請選取&#x200B;**[!UICONTROL Serialize]**&#x200B;控制項並指定序列分隔符號（分隔序列化值的字元）。
1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;並展開[!UICONTROL Segment Mappings]區段。

### 步驟3：區段對應

若要將區段新增至Cookie目的地：

1. **尋找區段：** [!UICONTROL Segment Mappings]區段提供兩種搜尋工具來協助尋找區段。 若要搜尋區段，請執行下列步驟：
   * 選項1：開始在搜尋欄位中輸入區段名稱。 欄位會根據文字自動更新。 找到要使用的區段後，請按一下&#x200B;**[!UICONTROL Add]**。
   * 選項2：按一下&#x200B;**[!UICONTROL Browse All Segments]**&#x200B;開啟視窗，讓您依名稱或儲存位置瀏覽區段。 完成時，按一下&#x200B;**[!UICONTROL Add Selected Segments]**。
1. **新增對應：**&#x200B;在對應快顯視窗中，在對應欄位中輸入區段ID，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 按一下 **[!UICONTROL Done]**。

## OAS設定 {#oas-code-setup}

修改[!DNL OAS]設定以使用Audience Manager區段資料。

<!-- aam-oas-code.xml -->

若要設定[!DNL OAS]

* 在您的網站上安裝[!UICONTROL DIL]程式碼。
* 將OAS建立為Audience Manager中的Cookie目的地。
* 將`get_aamCookie`函式放置在頁面頂端，最好放在`<head>`程式碼區塊中。 `get_aamCookie`程式碼可在[這裡](../../features/destinations/get-aam-cookie-code.md)取得。
* 修改您的廣告標籤以呼叫`get_aamCookie`函式，並加入您在設定[!DNL OAS]目的地時提供的Cookie名稱。 例如，如果您為Cookie `test_cookie`命名，則廣告標籤應呼叫`get_aamCookie`並參考Cookie名稱。
* 您的廣告標籤看起來可能類似於以下範例。

  ```js
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

請記得加入`u=`變數。 它保留在廣告呼叫期間傳入的實際不重複使用者識別碼([!UICONTROL UUID])。
