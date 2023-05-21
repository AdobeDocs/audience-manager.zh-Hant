---
description: 在目標生成器中，「配置」部分包含Cookie域和「將資料發佈到」欄位。 這些規則允許您建立規則來確定目標是設定cookie還是返回cookie。 Cookie域和發佈資料可彼此獨立工作，是可選的。 您可以建立Cookie目標，而不使用其中任何一個。
seo-description: In Destination Builder, the Configuration section contains the Cookie Domain and Publish Data To fields. These let you create rules to determine if a destination sets a cookie or returns a cookie. Cookie Domain and Publish Data To work independently of each other and are optional. You can create a cookie destination without using either of them.
seo-title: Optional Settings for Cookie Destinations
solution: Audience Manager
title: Cookie 目的地的選用設定
feature: Destination Basics
exl-id: b44f386e-4d43-41c3-b8ce-88b83d5d83c2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 7%

---

# Cookie 目的地的選用設定 {#optional-settings-cookies}

在 [!UICONTROL Destination Builder]，也請參見Wiki頁。 [!UICONTROL Configuration section] 包含 [!UICONTROL Cookie Domain] 和 [!UICONTROL Publish Data To] 的子菜單。 這些規則允許您建立規則來確定目標是設定cookie還是返回cookie。 [!UICONTROL Cookie Domain] 和 [!UICONTROL Publish Data To] 彼此獨立工作，是可選的。 您可以建立Cookie目標，而不使用其中任何一個。

## Cookie域：語法和示例 {#cookie-domain-syntax}

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
   <td colname="col2"> <p>的 <span class="wintitle"> Cookie域</span> 欄位接受一個簡單文本字串，該字串允許您在指定域或所有域上設定cookie。 使用此功能時： </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">為每個Cookie目標僅設定一個域。 請勿在 <span class="wintitle"> Cookie域</span> 的子菜單。 建立其他 <span class="wintitle"> 目標</span> 的雙曲餘切值。 </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">不要使用通配符。 </li> 
     </ul> </p> <p> 離開 <span class="wintitle"> Cookie域</span> 欄位為空，以在所有域上設定cookie。 這是預設設定。 </p> <p>要在特定域和子域上設定Cookie: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">在 <span class="wintitle"> Cookie域</span> 的子菜單。 </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">使用句點啟動域名。 例如, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">的 <code> https://www</code> 不需要前置詞。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>範例</b> </p> </td> 
   <td colname="col2"> <p>舉個簡單的例子，假設我們有一個虛擬的網站叫做sports.com。 Sports.com有高爾夫、棒球和足球等領域。 要在所有體育域中設定Cookie，請在 <span class="wintitle"> Cookie域</span> 框，如下所示： </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>這說明 <span class="keyword"> Audience Manager</span> 在包含模式的任何域中設定cookie <code><i>something</i></code>.sports.com。 有關更複雜的示例集，請參見下文。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 複雜Cookie域示例

這些示例顯示 [!DNL Audience Manager] 將根據 [!UICONTROL Cookie Domain] 的子菜單。

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 網站 </th> 
   <th colname="col2" class="entry">Cookie域：.sports.com <p>Cookie集 </p> </th> 
   <th colname="col3" class="entry">Cookie域：.golf.sports.com <p>Cookie集 </p> </th> 
   <th colname="col4" class="entry">Cookie域：空白 <p>Cookie集 </p> </th> 
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
   <td colname="col1"> <p> <b>棒球.sports.com</b> </p> </td> 
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

## 將資料發佈到 {#publish-data-to}

的 [!UICONTROL Publish Data To] 如果域符合您選擇的選項設定的條件，則設定將返回cookie。 選項包括:

* **[!UICONTROL All of our domains]**:（預設）返回 [!DNL cookie] 的下界。
* **[!UICONTROL Only the selected domains]**:僅為在域清單中選擇的域返回Cookie。
* **[!UICONTROL All of our domains except the selected domains]**:阻止選定域接收 [!DNL cookie]。 所有其他域都可以接收 [!DNL cookie]。

>[!MORELIKETHIS]
>
>* [建立Cookie目標](../../features/destinations/create-cookie-destination.md)

