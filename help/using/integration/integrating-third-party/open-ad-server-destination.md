---
description: 將Open Ad Server設定為目標，然後傳送Audience Manager資料至該平台。
seo-description: 將Open Ad Server設定為目標，然後傳送Audience Manager資料至該平台。
seo-title: 作為Audience Manager目標的OAS
solution: Audience Manager
title: 作為Audience Manager目標的OAS
uuid: 5891a 063-a4 b-4ea7-865f-b24 e17 ca735 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OAS as an Audience Manager Destination {#oas-as-an-audience-manager-destination}

Set up [!DNL Open Ad Server] as a destination and send Audience Manager data to that platform.

## OAS Destination Requirements {#oas-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OAS].

<!-- aam-oas-requirements.xml -->

此目的地類型需要下列項目：

* **[!UICONTROL DIL]：**[!UICONTROL Data Integration Library] 代碼應部署在您的庫存上。[!UICONTROL DIL] 協助免除編寫資料收集、整合、讀取Cookie值及恢復頁面資料的特殊程式碼。
* **`get_aamCookie`函數：** 擷取Audience Manager使用者ID和Cookie資料的程式碼。Place [this code](../../features/destinations/get-aam-cookie-code.md) on the top of the page or inside the `<head>` codeblock.
* **傳送傳送記錄至Audience Manager：** 如果您想要區段傳送報表(選用)，請提供Audience Manager使用包含曝光層級傳送資料的每日記錄檔。The data can be in a raw format, but each record must contain the Audience Manager [!UICONTROL UUID]. Audience Manager can pick up or receive these via [!DNL FTP].

### Cookie格式與索引鍵值資料

Audience Manager可將區段資料傳送至瀏覽器Cookie，如下所示：

* Single keys (`x=1&x=2`);
* Multiple keys (`x=1&x=2&y=3&y=4`);
* Serialized values (`x=1,2,3`);
* 用來分隔個別索引鍵值配對的標準值分隔字元。

### 只有合格區段才會傳送至OAS

The amount data passed in to [!DNL OAS] depends on how many segments a particular user qualifies for. 例如，假設您設定了100個「對象管理」區段。如果網站訪客符合其中五個條件，則只有這個區段會傳送至OAS(並非全部100)。

>[!MORE_贊_ this]
>
>* [get_ aamCookie Code](../../features/destinations/get-aam-cookie-code.md)
>* [索引鍵值對說明](../../reference/key-value-pairs-explained.md)


## Create an OAS Destination {#oas-dest-setup}

Create a cookie-based destination for [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) 您要與其共用資料。[!UICONTROL Destination Builder] 提供可讓您建立和管理這些資料傳送程序的工具。Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### 步驟1：基本資訊

To complete the [!UICONTROL Basic Information] section:

1. 命名目的地。
1. **[!UICONTROL "Cookie"]** 從 [!UICONTROL Type] 下拉式清單中選取。
1. Click **[!UICONTROL Save]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

### 步驟2：組態資訊

To complete the [!UICONTROL Configuration] section:

1. **Cookie名稱：** 為您的Cookie提供簡短、描述性的名稱。
1. **Cookie網域：** 保留空白，以在使用者目前頁面的網域中設定Cookie。If you want to specify a domain, prefix the name with a period like this, `.mydomain.com`.
1. Choose a key option in the [!UICONTROL Data Format] section.
1. If your keys use data with serialized values, select the **[!UICONTROL Serialize]** control and specify the serial delimiter (the character that separates the serialized values).
1. Click **[!UICONTROL Save]** and expand the [!UICONTROL Segment Mappings] section.

### 步驟3：區段映射

若要新增區段至Cookie目的地：

1. **尋找區段：**[!UICONTROL Segment Mappings] 此區段提供兩個搜尋工具以協助尋找區段。若要尋找區段：
   * 選項1：開始在搜尋欄位中鍵入區段名稱。欄位會根據文字自動更新。Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.
1. **新增對應：** 在對應彈出式視窗中，輸入映射欄位中的區段ID，然後按一下 **[!UICONTROL Save]**。
1. Click **[!UICONTROL Done]**.

## OAS Setup {#oas-code-setup}

Modify [!DNL OAS] settings to work with Audience Manager segment data.

<!-- aam-oas-code.xml -->

To set up [!DNL OAS]

* Install [!UICONTROL DIL] code across your site.
* 在Audience Manager中建立OAS作為Cookie目的地。
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. `get_aamCookie` 此處提供程式碼 [](../../features/destinations/get-aam-cookie-code.md)。
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OAS] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* 您的廣告標記看起來可能類似於下方範例。

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Remember to include the `u=` variable. It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.
