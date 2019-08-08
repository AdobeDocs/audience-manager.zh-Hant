---
description: 在「目標產生器」中，「設定」區段包含「Cookie網域」和「發佈資料至」欄位。這可讓您建立規則以判斷目的地是否設定Cookie或傳回Cookie。Cookie網域和發佈資料可獨立運作，且為選擇性。您可以建立Cookie目的地，而不需使用其中任一個目的地。
seo-description: 在「目標產生器」中，「設定」區段包含「Cookie網域」和「發佈資料至」欄位。這可讓您建立規則以判斷目的地是否設定Cookie或傳回Cookie。Cookie網域和發佈資料可獨立運作，且為選擇性。您可以建立Cookie目的地，而不需使用其中任一個目的地。
seo-title: Cookie目的地的選擇性設定
solution: Audience Manager
title: Cookie目的地的選擇性設定
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Cookie目的地的選擇性設定 {#optional-settings-cookies}

In [!UICONTROL Destination Builder]，the [!UICONTROL Configuration section] contains the [!UICONTROL Cookie Domain] and [!UICONTROL Publish Data To] fields.這可讓您建立規則以判斷目的地是否設定Cookie或傳回Cookie。[!UICONTROL Cookie Domain] 並可獨立 [!UICONTROL Publish Data To] 作業，而且可選購。您可以建立Cookie目的地，而不需使用其中任一個目的地。

## Cookie網域：語法和範例 {#cookie-domain-syntax}

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
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">每個Cookie目的地僅設定一個網域。請勿在 <span class="wintitle"> 「Cookie網域</span> 」欄位中輸入多個網域。請改用其他 <span class="wintitle"> 目的地</span> 。 </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">請勿使用萬用字元。 </li> 
     </ul> </p> <p> 將 <span class="wintitle"> 「Cookie網域</span> 」欄位留空，以在所有網域上設定Cookie。這是預設設定。 </p> <p>若要在特定網域和子網域上設定Cookie： </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">在 <span class="wintitle"> 「Cookie網域</span> 」欄位中鍵入網域名稱。 </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">使用句點開始網域名稱。例如 <code> .somedomain.com</code>。 </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>範例</b> </p> </td> 
   <td colname="col2"> <p>簡單來說，假設我們有一個虛構網站叫做ports. com。Sports.com有高爾夫球、棒球和足球網域。若要在所有運動網域中設定Cookie，您可以在 <span class="wintitle"> 「Cookie網域</span> 」方塊中鍵入該Cookie，如下所示： </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>這會告訴 <span class="keyword"> Audience Manager</span> 在任何包含pattern <code><i>.</i></code>sports. com模式的網域中設定Cookie。請參閱下方以取得更複雜的範例集。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 複雜Cookie網域範例

這些範例顯示 [!DNL Audience Manager] 是否將根據設定的 [!UICONTROL Cookie Domain] 選項設定Cookie。

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

## 將資料發佈至 {#publish-data-to}

[!UICONTROL Publish Data To] 如果網域符合您選擇的選項設定的標準，則設定會傳回Cookie。選項包括:

* **[!UICONTROL All of our domains]**：(預設)傳回任何網域 [!DNL cookie] 的網域。
* **[!UICONTROL Only the selected domains]**：只傳回網域清單中所選網域的Cookie。
* **[!UICONTROL All of our domains except the selected domains]**：防止選取的網域接收 [!DNL cookie]。所有其他網域都會收到 [!DNL cookie]。

>[!MORE_贊_ this]
>
>* [建立Cookie目的地](../../features/destinations/create-cookie-destination.md)