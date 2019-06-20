---
description: 目的地登陸頁面會列出您的所有URL、Cookie和伺服器對伺服器目的地。它提供可讓您建立、編輯、搜尋和報告目的地的功能。著陸頁面位於「對象資料>目標」中。
seo-description: 目的地登陸頁面會列出您的所有URL、Cookie和伺服器對伺服器目的地。它提供可讓您建立、編輯、搜尋和報告目的地的功能。著陸頁面位於「對象資料>目標」中。
seo-title: 管理目標
solution: Audience Manager
title: 管理目標
uuid: 6b66ff42-0075-49a7-a58 f-7f8 ea2295 fdc
translation-type: tm+mt
source-git-commit: 1d516c49a16c38adcc22827dc254da1ebada0734

---


# Manage Destinations {#manage-destinations}

[!UICONTROL Destination] 登陸頁面會列出您的所有 [!DNL URL]、Cookie和伺服器對伺服器目的地。它提供可讓您建立、編輯、搜尋和報告目的地的功能。The landing page is located in **[!UICONTROL Audience Data > Destinations]**.

## Default Landing Page {#default-landing-page}

<!-- destinations-home.xml -->

預設登陸頁面會根據類型列出目的地。您可以使用四個可用標籤來篩選目的地：

* **** 全部：顯示所有目的地類型。
* **Adobe Experience Cloud**：顯示將資料傳送至其他Adobe Experience Cloud解決方案的目標。目前唯一支援的選項是Adobe Analytics。See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **整合平台**：顯示以人員為主的裝置目的地(也稱為伺服器對伺服器目的地)。請注意，以人員為基礎的目的地目前僅適用於特定客戶。
* **自訂**：顯示Cookie和URL目的地。


![](assets/destinations-landing.png)

## Addressable Audiences Landing Page {#audiences-landing-page}

To see audience data and match rates for your server-to-server destination, select **[!UICONTROL Integrated Platforms > Device-Based]**.

For more information about the displayed information, see [Addressable Audiences Interface](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## Destination Builder {#destination-builder}

[!UICONTROL Destination Builder] 可讓您建立Cookie或 [!DNL URL] 目的地。You cannot create server-to-server ([!DNL S2S]) destinations with [!UICONTROL Destination Builder], but you can manage their segment mappings. Contact your consultant to set up a [!DNL S2S] destination. [!UICONTROL Destination Builder]**[!UICONTROL Audience Data > Destinations]** 位於中。

### Destination Builder Settings {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 包含下列區段和設定：

| [!UICONTROL Destination Builder] 區域 | 用途 |
|--- |--- |
| 基本資訊 | Used to name the destination, describe it, and select destination type ([!DNL URL] or [!DNL cookie]), and platform (all, [!DNL Android], browser, or [!DNL iOS]). |
| 設定 | Includes controls for: <br/><ul><li>Passing in key-value data to [!DNL URL] destinations. 您可以將資料傳送為個別或序列化索引鍵值配對。For details see, [Destination Serialization](../../features/destinations/key-value-pairs.md#destination-serialized) and [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md). </li><li>Cookie目的地的元素，例如Cookie名稱、網域、大小、有效期間隔、資料格式等。</li></ul> |
| 區段映射 | 可讓您: <br/><ul><li>搜尋、新增和管理與所有目的地類型關聯的區段。 </li><li>Set delivery priorities on individual segments (for [!DNL cookie]-based segments only).</li></ul> |

### Data Delivery Methods {#data-delivery-methods}

Send information to a destination by passing it in through a [!DNL URL] string, by writing to a browser [!DNL cookie], or through offline server-to-server data transfers.

* [!DNL URL] 和基於Cookie的目的地會同步傳輸資料，使用者會在頁面上採取動作。
* 伺服器對伺服器資料傳輸是非同步的，在使用者離開頁面後可能會發生。您選取的傳送類型取決於您的業務需求，以及特定資料合作夥伴要如何接收資料。

See [How to Choose a Destination Type](../../features/destinations/destinations.md) for more information.

>[!MORE_贊_ this]
>
>* [建立Cookie目的地](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [建立URL目的地](../../features/destinations/manage-destinations.md#configure-url-destination)


## Configure a Cookie Destination {#create-cookie-destination}

Cookie目的地會傳回並寫入使用者瀏覽器中的Cookie。Cookie包含可供存取頁面之其他平台讀取的資料。Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

To create a new cookie destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

### 基本資訊 {#basic-information}

本節包含開始Cookie目的地建立程序的欄位和選項。若要完成本節：

1. Click **[!UICONTROL Basic Information]** to expose the controls.
2. 命名目的地。避免縮寫和特殊字元。
3. *(選擇性)* 說明目的地。簡明扼要的說明是定義或提供目標的更多資訊。
4. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
5. In the **[!UICONTROL Environment]** list, select **[!UICONTROL Browser]**. 您無法針對原生行動環境(例如Android或iOS應用程式)設定Cookie目的地。
6. In the **[!UICONTROL Type]** list, click **[!UICONTROL Cookie]**.
7. *(選擇性)* 選擇 **[!UICONTROL Auto-fill Destination Mapping]** 一個。選項包括:
   * **[!UICONTROL Segment ID]**：自動新增區段ID並傳送至目的地。
   * **[!UICONTROL Integration Code Value]**：自動新增區段整合代碼並傳送至目的地對應。整合代碼是客戶建立並使用的唯一識別碼。僅限255個字元上限。
8. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

### Data Export Labels {#data-export-labels-cookies}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a cookie destination. 如果您不使用資料匯出控制，請跳過此步驟。若要完成本節：

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. Click **[!UICONTROL Save]**.

### 設定 {#configuration}

本節包含可讓您設定目的地Cookie的欄位和選項。

>[!NOTE]
>
>[!DNL Audience Manager] 對寫入目的地Cookie的資料進行編碼。For example, spaces are encoded as `%20` and semicolons are encoded as `%3B`.

若要完成本節：

1. Click **[!UICONTROL Configuration]** to expose the controls
1. 命名Cookie。避免縮寫和特殊字元。
1. 選擇資料格式選項。這些選項可讓您為將區段資料傳送至目的地的索引鍵值配對選擇分隔字元和分隔符號。格式選項包括：
   * **單一索引鍵：** 可讓您將索引鍵設定為索引鍵值配對。You&#39;ll set the value after you select a segment in the [!UICONTROL Segment Mappings] section below.
   * **多索引鍵：** 可讓您設定索引鍵值配對的索引鍵和值。在下方「區段對應」區段中選取區段後，您將建立索引鍵值配對。
See [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md) for more information about these data elements.
1. Click **[!UICONTROL Save]**.

所有其他設定皆為選用。For more information about the **[!UICONTROL Cookie Domain]** and **[!UICONTROL Publish data to]** settings, see [Optional Settings for Cookie Destinations](../../features/destinations/manage-destinations.md#optional-settings-cookies).

### Segment Mappings {#segments-mapping}

此區段可讓您搜尋並新增區段至目的地。若要完成本節：

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. **[!UICONTROL Search and Add Segments]** 在方塊中，開始鍵入區段名稱，或按一下 **[!UICONTROL Browse All Segments]** 以瀏覽可用區段清單。
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. [!UICONTROL Edit Mapping] 在對話方塊中：
   * **[!UICONTROL Mapping]** 可讓您設定上方「設定」一節中指定之索引鍵的值。
   * **[!UICONTROL Publish from]** 可讓您設定目的地的開始和結束日期。如果結束日期空白，目的地永不過期。
1. Click **[!UICONTROL Save]**.
1. Click **[!UICONTROL Done]**.

## Configure a URL Destination {#configure-url-destination}

[!DNL URL] 目的地會從頁面發出像素呼叫至目的地。Follow these instructions to create a [!DNL URL] destination with [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

To create a new [!DNL URL] destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

### 基本資訊 {#basic-info}

本節包含開始URL目的地建立程序的欄位和選項。若要完成本節：

1. Click **[!UICONTROL Basic Information]** to expose the controls.
1. 命名目的地。避免縮寫和特殊字元。
1. *(選擇性)* 說明目的地。簡明扼要的說明是定義或提供目標的更多資訊。
1. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
1. In the **[!UICONTROL Environment]** list, select the environment in which to trigger the URL destination.
1. In the **[!UICONTROL Type]** list, click **[!UICONTROL URL]**.
1. *(選擇性)* 選擇 **[!UICONTROL Auto-fill Destination Mapping]** 一個。選項包括:
   * **[!UICONTROL Segment ID]**：自動新增區段ID並傳送至目的地。
   * **[!UICONTROL Integration Code Value]**：自動新增區段整合代碼並傳送至目的地對應。整合代碼是客戶建立並使用的唯一識別碼。僅限255個字元上限。
1. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

### Data Export Labels {#data-export-labels-dest}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a [!DNL URL] destination. 如果您不使用資料匯出控制，請跳過此步驟。若要完成本節：

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. Click **[!UICONTROL Save]**.

### 設定 {#configure-base-data}

This section contains options that let you set a base [!DNL URL] and data delimiters passed in by the [!DNL URL] string. 此區域為選用。若要完成本節：

1. Click **[!UICONTROL Configuration]** to expose the controls.
1. *(選擇性)* 選取 **[!UICONTROL Serialize]** 核取方塊。
這可讓您依序傳送區段至目的地，而非對每個區段進行個別呼叫。序列化有助於提高資料傳輸效率。選取此核取方塊會顯示URL和分隔字元欄位。For more information, see [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md).
1. If you select **[!UICONTROL Serialize]**, then you must also configure the URL and delimiter fields described below.

| 欄位 | 說明 |
|--- |--- |
| 基礎 URL | The base part of a standard `HTTP` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`  [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. 範例: `https://www.myCompany.com/%alias%...` |
| 安全URL | The base part of a secure `HTTPS` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`   [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. 範例: `https://www.myCompany.com/%alias%...` |
| 分隔字元 | The symbol that separates the segment variables in the [!DNL URL] string. 這通常是逗號或分號。從您的目的地合作夥伴取得此資訊。 |

### Segment Mappings {#segment-mappings}

此區段可讓您搜尋並新增區段至目的地。若要完成本節：

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. **[!UICONTROL Search and Add Segments]** 在方塊中，開始鍵入區段名稱，或按一下 **[!UICONTROL Browse All Segments]** 可瀏覽可用區段清單。
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**：提供區段使用的索引鍵值配對。
   * **[!UICONTROL Start Date]** and **[!UICONTROL End Date]**：選擇目的地的開始和結束日期。如果結束日期空白，目的地永不過期。
1. Click **[!UICONTROL Done]**.

### Optional Settings for Cookie Destinations {#optional-settings-cookies}

In [!UICONTROL Destination Builder], the [!UICONTROL Configuration section] contains the [!UICONTROL Cookie Domain] and [!UICONTROL Publish Data To] fields. 這可讓您建立規則以判斷目的地是否設定Cookie或傳回Cookie。[!UICONTROL Cookie Domain] 並可獨立 [!UICONTROL Publish Data To] 作業，而且可選購。您可以建立Cookie目的地，而不需使用其中任一個目的地。

## Cookie Domain: Syntax and Examples {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cookie 網域 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>語法</b> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 「Cookie網域</span> 」欄位接受簡單的文字字串，可讓您在指定網域或所有網域上設定Cookie。使用此功能時： </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">每個Cookie目的地僅設定一個網域。Do not type multiple domains in the <span class="wintitle"> Cookie Domain</span> field. Create another <span class="wintitle"> Destination</span> instead. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">請勿使用萬用字元。 </li> 
     </ul> </p> <p> Leave the <span class="wintitle"> Cookie Domain</span> field blank to set a cookie on all domains. 這是預設設定。 </p> <p>若要在特定網域和子網域上設定Cookie： </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Type the name of the domain in the <span class="wintitle"> Cookie Domain</span> field. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">使用句點開始網域名稱。For example, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>範例</b> </p> </td> 
   <td colname="col2"> <p>簡單來說，假設我們有一個虛構網站叫做ports. com。Sports.com有高爾夫球、棒球和足球網域。To set a cookie in all the sports domains, you would type that in the <span class="wintitle"> Cookie Domain</span> box as shown below: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>This tells <span class="keyword"> Audience Manager</span> to set a cookie in any domain that contains the pattern <code><i>something</i></code>.sports.com. 請參閱下方以取得更複雜的範例集。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 複雜Cookie網域範例

These examples show you if [!DNL Audience Manager] will set a cookie based on how the [!UICONTROL Cookie Domain] option is configured.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 網站 </th> 
   <th colname="col2" class="entry">Cookie網域：.sports.com <p>Cookie設定 </p> </th> 
   <th colname="col3" class="entry">Cookie網域：.golf.sports.com <p>Cookie設定 </p> </th> 
   <th colname="col4" class="entry">Cookie網域：Blank <p>Cookie設定 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> 有 </td> 
   <td colname="col3"> 否 </td> 
   <td colname="col4"> 是 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sports.com</b> </p> </td> 
   <td colname="col2"> 是 </td> 
   <td colname="col3"> 是 </td> 
   <td colname="col4"> 是 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sports.com</b> </p> </td> 
   <td colname="col2"> 有 </td> 
   <td colname="col3"> 否 </td> 
   <td colname="col4"> 是 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> 否 </td> 
   <td colname="col3"> 否 </td> 
   <td colname="col4"> 是 </td> 
  </tr> 
 </tbody> 
</table>

## Publish Data To {#publish-data-to}

[!UICONTROL Publish Data To] 如果網域符合您選擇的選項設定的標準，則設定會傳回Cookie。選項包括:

* **[!UICONTROL All of our domains]**：(預設)傳回任何網域 [!DNL cookie] 的網域。
* **[!UICONTROL Only the selected domains]**：只傳回網域清單中所選網域的Cookie。
* **[!UICONTROL All of our domains except the selected domains]**：防止選取的網域接收 [!DNL cookie]。All other domains can receive a [!DNL cookie].

>[!MORE_贊_ this]
>
>* [建立Cookie目的地](../../features/destinations/manage-destinations.md#create-cookie-destination)


## Add or Edit Segments for Server-to-Server Destinations {#add-edit-segments}

You can only add or edit segments for a server-to-server ([!DNL S2S]) destination. You cannot create [!DNL S2S] destinations with [!UICONTROL Destination Builder]. Contact your consultant to set up [!DNL S2S] destinations. Follow these instructions to add or edit segments for an [!DNL S2S] destination.

<!-- destination-s2s-edit.xml -->

To add or edit segment mappings for an [!DNL S2S] destination:

1. **[!UICONTROL Audience Data > Destinations]** 前往。Select **Integrated Platforms &gt; Device-Based** and find the [!DNL S2S] destination you want to work with.
1. [!UICONTROL Action] 在欄中，按一下鉛筆圖示以編輯目的地。
   * **[!UICONTROL Search and Add Segments]** 在方塊中，開始鍵入區段名稱，或按一下 **[!UICONTROL Browse All Segments]** 可瀏覽可用區段清單。
   * Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
   * 在 [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**：為此目的地使用 [的索引鍵值配對](../../features/destinations/key-value-pairs.md) 設定值。
      * **[!UICONTROL Start Date]** and **[!UICONTROL End Date]**：選擇目的地的開始和結束日期。如果結束日期空白，目的地永不過期。
1. Click **[!UICONTROL Save]** and then click **[!UICONTROL Done]**.

## Add Data Export Labels to a Destination {#add-data-export-labels}

[!DNL Data Export Labels] 與 [!DNL Export Controls] 您在資料來源上設定的作業相同。[!DNL Data Export Labels] 防止您將受限制的特性新增至區段，以及將區段資料傳送至目的地。You can set multiple export labels to a new or existing [!DNL cookie] or [!DNL URL] destination.

>[!NOTE]
>
>To add an export label, you need administrator permissions *or* sufficient privileges to create or edit a destination.

<!-- t_export_labels.xml -->

若要將匯出標籤新增至目的地：

1. Click **[!UICONTROL Audience Data]**:
   * For new destinations: Click **[!UICONTROL Create New Destination]**. Complete the [!UICONTROL Basic Information] section before you select a data export label. See [Create a Cookie Destination](../../features/destinations/manage-destinations.md#create-cookie-destination) or [Create a URL Destination](../../features/destinations/manage-destinations.md#configure-url-destination) for information.
   * For existing destinations: Use the [!DNL Search] box to find your destination or scroll through the list and click on the destination name to open it.
1. 選擇 [!DNL Data Export Label]. 如果您不想設定任何匯出限制，請將核取方塊保留空白。匯出標籤包含下列選項：
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Export restrictions will not work unless you set a [matching export control](../../features/data-export-controls.md) on a data source.
1. Click **[!UICONTROL Save]**.

>[!MORE_贊_ this]
>
>* [建立資料來源](../../features/manage-datasources.md#create-data-source)

