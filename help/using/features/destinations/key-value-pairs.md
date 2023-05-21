---
description: A [!DNL key-value pair] 由 [!DNL related elements]。 一個鍵，它是定義資料集（例如性別、顏色、價格）的常數和一個值，它是屬於該集的變數（例如，男/女，綠色，100）。 目標生成器發送格式化為鍵值對的資料。
solution: Audience Manager
title: 標準和串列 [!DNL Key-value pairs]
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Destination Basics
exl-id: b37c829b-66be-4c31-8198-bc032371279e
source-git-commit: 0dfe96a4644c61fb5bc22e4791bfd09c574dcf34
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 2%

---

# 標準和序列索引鍵值配對 {#standard-and-serial-key-value-pairs}

鍵值對由相關元素組成：鍵，它是定義資料集的常數(例如：性別、顏色、價格)和值，該值是屬於該集的變數（例如，男/女，綠色，100）。 [!UICONTROL Destination Builder] 發送格式化為鍵值對的資料。

## 基本鍵值對 {#basic-key-value-pairs}

完全成形後，基本的鍵值對集可能如下所示：

* `gender = male`
* `color = green`
* `price > 100`

## 標準和序列索引鍵值配對 {#standard-serial-key-value-pairs}

目標接受中的鍵值資料 *`standard`* 或 *`serialized`* 的子菜單。

* **標準鍵值對：** 將目標資料格式化為單獨的鍵值對。 每個鍵都被顯式地表示，即使再次用於定義不同的值時也是如此。
* **序列化鍵值對：** 將多個值縮聚到單個鍵值對中。 在序列化鍵值對中，特殊指示符分隔鍵值集內的值。

標準鍵值和序列化鍵值都可以包含單個或多個值。 下表提供了標準和串列鍵值格式的示例。

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 格式 </th>
   <th colname="col2" class="entry"> 單鍵值對 </th>
   <th colname="col3" class="entry"> 多個鍵值對 </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>標準</b> </p> </td>
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td>
   <td colname="col3"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>序列化</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## 分隔符和分隔符 {#delimiters-separators}

在鍵和值之間以及鍵和值之間分隔值的字元稱為 *`delimiters`* 和 *`separators`*。 當您以串列格式將段發送到目標時，這些內容變得尤為重要。 序列化允許您使用單個鍵傳遞多個值並組合鍵值對。 分隔符和分隔符的定義如下：

* **鍵值分隔符：** 將鍵值對中的鍵和值分開。
* **鍵值分隔符：** 分離鍵值對的集。
* **序列分隔符：** 在序列化鍵值對的集中分離多個值。

## 範例 {#examples}

與 [!UICONTROL Destination Builder] 可以以多種不同的方式格式化鍵值資料。 讓我們看一下每種類型的一些示例。

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 鍵值對示例 </th> 
   <th colname="col2" class="entry"> 範例 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>標準單鍵</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>一組簡單的鍵值對。 該示例包含以下元素： </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">鍵：X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">值：1、2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">分隔符：= </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">鍵值分隔符：&amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>多個鍵值對</b> （非串列） </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>一組多個鍵值對，這些鍵值對與單獨的鍵值集傳遞。 該示例包含以下元素： </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">鍵：X、Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">值：1、2、3、4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">分隔符：= </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">鍵值分隔符：&amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>串列單鍵</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>一個鍵值集，用一個鍵傳遞多個值。 由於此鍵具有多個值，因此它稱為序列化鍵值對。 該示例包含以下元素： </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">鍵：X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">值：1、2、3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">分隔符：= </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">序列分隔符：分號 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>多個鍵值對</b> （串列） </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>一組多鍵值對，這些對在單獨的鍵上傳遞多個值。 該示例包含以下元素： </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">鍵：X、Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">值：1、2、3、4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">分隔符：= </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">分隔字元: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">序列分隔符：分號 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 目標序列化 {#destination-serialized}

序列化目標將多個特徵合併為單個字串，並將該資訊發送到目標。

<!-- c_dest_serialized.xml -->

串列化資料傳輸有助於提高效率，因為多個特性會依次觸發，而不是並行觸發。 這為目標伺服器提供了足夠的時間來接收、處理和返回資料，然後再響應其他請求。

### 支援的目標

在 [!DNL Audience Manager]，您可以序列化資料並將資料發送到任何要處理的目標。 但是，在使用此功能之前，您需要瞭解目標 [!DNL URL] 以及放置某些必需或可選宏的位置。 從目標合作夥伴獲取有關宏放置的資訊。 請參閱 [定義的目標宏](../../features/destinations/destination-macros.md#destination-macros-defined) 的子菜單。
