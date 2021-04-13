---
description: 將OpenX設為目標，並傳送Audience Manager區段資料至該平台。
seo-description: 將OpenX設為目標，並傳送Audience Manager區段資料至該平台。
seo-title: OpenX 作為 Audience Manager 目的地
solution: Audience Manager
title: OpenX 作為 Audience Manager 目的地
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: 協力廠商整合
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 3%

---

# OpenX 作為 Audience Manager 目的地{#openx-as-an-audience-manager-destination}

將[!DNL OpenX]設為目標，並傳送Audience Manager區段資料至該平台。

>[!NOTE]
>
>僅限Onsite廣告伺服器定位。

## OpenX目標要求{#openx-requirements}

程式碼放置標準、支援的關鍵值格式、報告，以及傳送至[!DNL OpenX]的區段資料類型。

<!-- aam-openx-requirements.xml -->

在將[!DNL OpenX]設為Audience Manager目的地之前，請先閱讀以下內容：

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] 程式碼應部署在您的網站上。[!UICONTROL DIL] 協助您免除撰寫資料收集、整合、讀取Cookie值和復原頁面資料的特殊程式碼。
* **`get_aamCookie`函式：** 擷取Audience Manager使用者ID和Cookie資料的程式碼。將[此程式碼](../../features/destinations/get-aam-cookie-code.md)置於頁面頂端或`<head>`程式碼鎖定內。
* **傳送傳送記錄檔至Audience Manager:** 如果您想要區段傳送報表（選用），請為Audience Manager提供包含印象層級傳送資料的每日記錄檔。資料可以是原始格式，但每個記錄必須包含Audience Manager`UUID`。 Audience Manager可以通過[!DNL FTP]接收這些檔案。

### 關鍵值資料：格式要求

Audience Manager以鍵值對的形式發送資料。 根據下列規格建立索引鍵值配對：

* 帶有`c.`（例如`c.color`或`c.price`）的前言鍵。
* 使用逗號（例如`c.color = red, green, blue`）分隔附加至單鍵的序號值。
* 使用&amp;符號（例如`c.color=red & c.price = 100 & c.condition = new`）分隔多個鍵值對。
* 鍵名不應包含特殊字元，例如重音、標點符號或其他符號。

### 只有合格區段會傳送至OpenX

傳入至[!DNL OpenX]的資料量取決於特定使用者符合的區段數。 例如，假設您設定了100個Audience Manager區段。 如果某位網站訪客符合其中5個區段的資格，則只有這5個區段會傳送至[!DNL OpenX]（並非全部100）。

## 建立OpenX目標{#openx-destination}

建立Audience Manager中[!DNL OpenX]的Cookie目標。

<!-- aam-openx-destination.xml -->

在Audience Manager中，*目標*&#x200B;是任何其他系統（廣告伺服器、[!DNL DSP]廣告網路等） 任何其他系統 (廣告伺服器、DSP、廣告網路等)。[!UICONTROL Destination Builder] 提供可讓您建立和管理這些資料傳送程式的工具。Audience Manager目標功能位於&#x200B;*觀眾資料>目標*。 若要開始，請按一下&#x200B;**[!UICONTROL Add New Destination]**，然後遵循下列步驟。

### 步驟1:基本資訊

要完成[!UICONTROL Basic Information]部分：

1. 命名目標。
1. 從[!UICONTROL Type]下拉式清單中選取&#x200B;**[!UICONTROL "Cookie"]**。
1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;並移至[!UICONTROL Configuration]和[!UICONTROL Segment Mappings]部分。

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

## OpenX Setup {#openx-code-setup}

修改[!DNL OpenX]設定以處理Audience Manager段資料。

<!-- aam-openx-code.xml -->

要設定[!DNL OpenX]:

* 在您的網站上安裝[!UICONTROL DIL]程式碼。
* 建立[!DNL OpenX]作為Audience Manager中的Cookie目的地。
* 將`get_aamCookie`函式置於頁面頂端，最好是置於`<head>`程式碼鎖定中。 `get_aamCookie`程式碼位於[這裡](../../features/destinations/get-aam-cookie-code.md)。
* 修改您的廣告標籤以呼叫`get_aamCookie`函式，並包含您在設定[!DNL OpenX]目標時提供的Cookie名稱。 例如，如果您命名Cookie `test_cookie`，則廣告標籤應呼叫`get_aamCookie`並參考Cookie名稱。
* 您的廣告標籤看起來可能類似於下列範例。

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

請記得包含`xid=`。 它包含廣告呼叫期間傳入的實際唯一使用者ID([!UICONTROL UUID])。

完整格式的廣告呼叫看起來可能類似：

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
