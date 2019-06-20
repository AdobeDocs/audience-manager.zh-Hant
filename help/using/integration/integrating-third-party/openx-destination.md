---
description: 設定OpenX作為目的地，然後傳送Audience Manager區段資料至該平台。
seo-description: 設定OpenX作為目的地，然後傳送Audience Manager區段資料至該平台。
seo-title: OpenX做為Audience Manager目的地
solution: Audience Manager
title: OpenX做為Audience Manager目的地
uuid: 5e86ba73-281c-403b-af06-64a1 d427526 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OpenX as an Audience Manager Destination{#openx-as-an-audience-manager-destination}

Set up [!DNL OpenX] as a destination and send Audience Manager segment data to that platform.

>[!NOTE]
>
>僅適用於Onsite廣告伺服器定位。

## OpenX Destination Requirements {#openx-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Review the following before setting up [!DNL OpenX] as an Audience Manager destination:

* **[!UICONTROL DIL]：**[!UICONTROL Data Integration Library] 代碼應部署在您的網站上。[!UICONTROL DIL] 協助免除編寫資料收集、整合、讀取Cookie值及恢復頁面資料的特殊程式碼。
* **`get_aamCookie`函數：** 擷取Audience Manager使用者ID和Cookie資料的程式碼。Place [this code](../../features/destinations/get-aam-cookie-code.md) on the top of the page or inside the `<head>` codeblock.
* **傳送傳送記錄至Audience Manager：** 如果您想要區段傳送報表(選用)，請提供Audience Manager使用包含曝光層級傳送資料的每日記錄檔。The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### 關鍵價值資料：格式需求

Audience Manager會以關鍵值配對的形式傳送資料。根據下列規格建立索引鍵值配對：

* Preface keys with `c.` (e.g., `c.color` or `c.price`).
* Separate serialized values attached to a single key with a comma (e.g., `c.color = red, green, blue`).
* Separate multiple key-value pairs with an ampersand (e.g., `c.color=red & c.price = 100 & c.condition = new`).
* 金鑰名稱不應包含特殊字元，例如符號、標點符號或其他符號。

### 只有合格區段才會傳送至OpenX

The amount data passed in to [!DNL OpenX] depends on how many segments a particular user qualifies for. 例如，假設您設定了100個「對象管理」區段。If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL OpenX] (not all 100).

## Create an OpenX Destination {#openx-destination}

Create a cookie destination for [!DNL OpenX] in Audience Management.

<!-- aam-openx-destination.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) 您要與其共用資料。[!UICONTROL Destination Builder] 提供可讓您建立和管理這些資料傳送程序的工具。Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### 步驟1：基本資訊

To complete the [!UICONTROL Basic Information] section:

1. 命名目的地。
1. **[!UICONTROL "Cookie"]** 從 [!UICONTROL Type] 下拉式清單中選取。
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

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

## OpenX Setup {#openx-code-setup}

Modify [!DNL OpenX] settings to work with Audience Manager segment data.

<!-- aam-openx-code.xml -->

To set up [!DNL OpenX]:

* Install [!UICONTROL DIL] code across your site.
* Create [!DNL OpenX] as a cookie destination in Audience Manager.
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. `get_aamCookie` 此處提供程式碼 [](../../features/destinations/get-aam-cookie-code.md)。
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OpenX] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* 您的廣告標記看起來可能類似於下方範例。

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Remember to include `xid=` . It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.

完全格式化的廣告呼叫看起來類似於：

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
