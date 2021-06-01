---
description: 在目的地產生器中，設定區段包含Cookie網域和將資料發佈至欄位。 這可讓您建立規則，以判斷目的地是設定Cookie還是傳回Cookie。 Cookie網域和發佈資料以彼此獨立運作，且為選用。 您可以建立Cookie目的地，而不需使用其中一個。
seo-description: 在目的地產生器中，設定區段包含Cookie網域和將資料發佈至欄位。 這可讓您建立規則，以判斷目的地是設定Cookie還是傳回Cookie。 Cookie網域和發佈資料以彼此獨立運作，且為選用。 您可以建立Cookie目的地，而不需使用其中一個。
seo-title: Cookie 目的地的選用設定
solution: Audience Manager
title: Cookie 目的地的選用設定
feature: 目的地基本知識
exl-id: b44f386e-4d43-41c3-b8ce-88b83d5d83c2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 7%

---

# Cookie 目的地的選用設定 {#optional-settings-cookies}

在[!UICONTROL Destination Builder]中，[!UICONTROL Configuration section]包含[!UICONTROL Cookie Domain]和[!UICONTROL Publish Data To]欄位。 這可讓您建立規則，以判斷目的地是設定Cookie還是傳回Cookie。 [!UICONTROL Cookie Domain] 和 [!UICONTROL Publish Data To] 彼此獨立工作，是可選的。您可以建立Cookie目的地，而不需使用其中一個。

## Cookie網域：語法和範例{#cookie-domain-syntax}

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
   <td colname="col2"> <p><span class="wintitle"> Cookie網域</span>欄位接受簡單的文字字串，該字串可讓您在指定網域或所有網域上設定Cookie。 使用此功能時： </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">為每個Cookie目的地僅設定一個網域。 請勿在「<span class="wintitle"> Cookie網域</span>」欄位中輸入多個網域。 請改為建立另一個<span class="wintitle">目標</span>。 </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">請勿使用萬用字元。 </li> 
     </ul> </p> <p> 將「<span class="wintitle"> Cookie網域</span>」欄位留空，以便在所有網域上設定Cookie。 這是預設設定。 </p> <p>若要在特定網域和子網域上設定Cookie: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">在<span class="wintitle"> Cookie網域</span>欄位中輸入網域的名稱。 </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">以句號啟動域名。 例如, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0"><code> https://www</code>前置詞不是必要項。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>範例</b> </p> </td> 
   <td colname="col2"> <p>舉個簡單的例子，假設我們有一個名為sports.com的虛構網站。 Sports.com有高爾夫球、棒球和足球的網域。 若要在所有體育網域中設定Cookie，您可以在<span class="wintitle"> Cookie網域</span>方塊中輸入，如下所示： </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>這會告訴<span class="keyword">Audience Manager</span>在任何包含模式<code><i>something</i></code>.sports.com的網域中設定Cookie。 如需更複雜的範例集，請參閱下方。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 複雜Cookie網域範例

這些範例顯示，如果[!DNL Audience Manager]要根據[!UICONTROL Cookie Domain]選項的設定方式來設定Cookie，便會如此。

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 網站 </th> 
   <th colname="col2" class="entry">Cookie網域：.sports.com <p>Cookie集 </p> </th> 
   <th colname="col3" class="entry">Cookie網域：.golf.sports.com <p>Cookie集 </p> </th> 
   <th colname="col4" class="entry">Cookie網域：空白 <p>Cookie集 </p> </th> 
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
   <td colname="col1"> <p> <b>basball.sports.com</b> </p> </td> 
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

## 將資料發佈到{#publish-data-to}

如果網域符合您選取的選項所設定的條件，[!UICONTROL Publish Data To]設定會傳回Cookie。 選項包括:

* **[!UICONTROL All of our domains]**:（預設）傳回任 [!DNL cookie] 何網域的。
* **[!UICONTROL Only the selected domains]**:僅針對在網域清單中選取的網域傳回Cookie。
* **[!UICONTROL All of our domains except the selected domains]**:阻止選定域接 [!DNL cookie]收。其他所有網域皆可接收[!DNL cookie]。

>[!MORELIKETHIS]
>
>* [建立Cookie目的地](../../features/destinations/create-cookie-destination.md)

