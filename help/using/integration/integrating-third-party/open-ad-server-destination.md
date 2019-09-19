---
description: 將Open Ad server設定為目標，並傳送Audience manager資料至該平台。
seo-description: 將Open Ad server設定為目標，並傳送Audience manager資料至該平台。
seo-title: OAS作為Audience manager目標
solution: Audience Manager
title: OAS作為Audience manager目標
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
translation-type: tm+mt
source-git-commit: 78a0a0e461ea3a74d0dbb0370a841db274a6f9be

---


# OAS作為Audience manager目標 {#oas-as-an-audience-manager-destination}

設定為 [!DNL Open Ad Server] 目標，並傳送Audience manager資料至該平台。

## OAS目標要求 {#oas-requirements}

程式碼放置標準、支援的關鍵值格式、報表，以及傳送至的區段資料類型 [!DNL OAS]。

<!-- aam-oas-requirements.xml -->

此目標類型需要：

* **[!UICONTROL DIL]** :程 [!UICONTROL Data Integration Library] 式碼應部署在您的清單上。 [!UICONTROL DIL] 協助您免除撰寫資料收集、整合、讀取Cookie值和復原頁面資料的特殊程式碼。
* **`get_aamCookie`** 函式：擷取Audience manager使用者ID和Cookie資料的程式碼。 將 [此程式碼置於](../../features/destinations/get-aam-cookie-code.md) 頁面頂端或程式碼解 `<head>` 碼塊內。
* **** 傳送傳送記錄至Audience Manager:如果您想要區段傳送報表（可選），請為Audience manager提供包含曝光層級傳送資料的每日記錄。 資料可以是原始格式，但每個記錄都必須包含Audience Manager [!UICONTROL UUID]。 Audience manager可以透過取得或接收這些 [!DNL FTP]。

### Cookie格式與金鑰值資料

Audience manager可依下列方式將區段資料傳送至瀏覽器Cookie:

* 單鍵(`x=1&x=2`);
* 多鍵(`x=1&x=2&y=3&y=4`);
* 序號值(`x=1,2,3`);
* 用於分隔個別索引鍵值對的標準值分隔字元。

### 僅將限定的段發送到OAS

傳入的資料量取決於 [!DNL OAS] 特定使用者符合的區段數。 例如，假設您設定了100個Audience manager區段。 如果某位網站訪客符合其中5個區段的資格，則只有這5個區段會傳送至OAS（並非全部100個）。

>[!MORE_LIKE_THIS]
>
>* [get_aamCookie代碼](../../features/destinations/get-aam-cookie-code.md)
>* [說明的鍵值對](../../reference/key-value-pairs-explained.md)


## 建立OAS目標 {#oas-dest-setup}

在Audience manager中建立以Cookie為 [!DNL OAS] 基礎的目的地。

<!-- aam-oas-destination-setup.xml -->

在Audience Manager中，目 *的地是* 任何其他系統(廣告伺服器 [!DNL DSP]、廣告網路等)您想要與其共用資料。 [!UICONTROL Destination Builder] 提供可讓您建立和管理這些資料傳送程式的工具。 Audience manager目標功能位於「對象資 *料&gt;目標」中*。 若要開始，請按一 **[!UICONTROL Add New Destination]** 下並遵循下列步驟。

### 步驟1:基本資訊

要完成該部 [!UICONTROL Basic Information] 分：

1. 命名目標。
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. 單 **[!UICONTROL Save]** 擊並移至和 [!UICONTROL Configuration] 節 [!UICONTROL Segment Mappings] 。

### 步驟2:配置資訊

要完成該部 [!UICONTROL Configuration] 分：

1. **** Cookie名稱：為您的Cookie提供簡短的描述性名稱。
1. **** Cookie網域：留空可在使用者目前頁面的網域中設定Cookie。 如果要指定網域，請在名稱前加上類似的句號 `.mydomain.com`。
1. 在區段中選擇鍵選 [!UICONTROL Data Format] 項。
1. 如果您的索引鍵使用含序號值的資料，請選 **[!UICONTROL Serialize]** 取控制項並指定序號分隔字元（分隔序號值的字元）。
1. 按一 **[!UICONTROL Save]** 下並展開 [!UICONTROL Segment Mappings] 區段。

### 步驟3:區段對應

若要新增區段至Cookie目標：

1. **** 尋找區段：本節 [!UICONTROL Segment Mappings] 提供兩種搜尋工具，以協助尋找區段。 若要尋找區段：
   * 選項1:開始在搜尋欄位中輸入區段名稱。 欄位會根據文字自動更新。 在找 **[!UICONTROL Add]** 到要使用的區段後，按一下。
   * 選項2:按一 **[!UICONTROL Browse All Segments]** 下以開啟可讓您依名稱或儲存位置瀏覽區段的視窗。 Click **[!UICONTROL Add Selected Segments]** when done.
1. **** 添加映射：在映射彈出式視窗中，在映射欄位中輸入區段ID，然後按一下 **[!UICONTROL Save]**。
1. Click **[!UICONTROL Done]**.

## OAS設定 {#oas-code-setup}

修改 [!DNL OAS] 設定以搭配Audience manager區段資料使用。

<!-- aam-oas-code.xml -->

若要設定 [!DNL OAS]

* 在您 [!UICONTROL DIL] 的網站上安裝程式碼。
* 在Audience manager中建立OAS作為Cookie目的地。
* 將函 `get_aamCookie` 數置於頁面頂端，最好是位於程式碼鎖定 `<head>` 內。 此 `get_aamCookie` 處提供程 [式碼](../../features/destinations/get-aam-cookie-code.md)。
* 修改您的廣告標籤以呼叫 `get_aamCookie` 函式，並包含您在設定目標時提供的Cookie名 [!DNL OAS] 稱。 例如，如果您為Cookie命名， `test_cookie`則廣告標籤應呼叫並 `get_aamCookie` 參考Cookie名稱。
* 您的廣告標籤看起來可能類似於下列範例。

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

請記得加入變 `u=` 數。 它包含廣告呼叫期間傳[!UICONTROL UUID]入的實際唯一使用者ID()。
