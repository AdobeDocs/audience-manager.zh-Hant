---
description: 鍵值對由相關元素A鍵組成，該鍵是定義資料集（例如性別、顏色、價格）的常數和值，該值是屬於該集的變數（例如，男／女、綠色、100）。 目標產生器會傳送格式化為金鑰值配對的資料。
seo-description: 鍵值對由相關元素A鍵組成，該鍵是定義資料集（例如性別、顏色、價格）的常數和值，該值是屬於該集的變數（例如，男／女、綠色、100）。 目標產生器會傳送格式化為金鑰值配對的資料。
seo-title: 標準和序列索引鍵值配對
solution: Audience Manager
title: 標準和序列索引鍵值配對
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 4%

---


# 標準和序列索引鍵值配對 {#standard-and-serial-key-value-pairs}

鍵值對由相關元素組成： 一個鍵，它是定義資料集（例如性別、顏色、價格）的常數，一個值，它是屬於該集的變數（例如，男／女、綠色、100）。 [!UICONTROL Destination Builder] 發送格式化為鍵值對的資料。

## 基本鍵值對 {#basic-key-value-pairs}

完全形式化後，基本的鍵值對組可能如下所示：

* `gender = male`
* `color = green`
* `price > 100`

## 標準和序列索引鍵值配對 {#standard-serial-key-value-pairs}

目標接受或格式的鍵 *`standard`* 值 *`serialized`* 資料。

* **標準鍵值配對：** 將目標資料格式化為單獨的鍵值對。 每個鍵都被明確指定，即使再次用於定義不同的值。
* **序列化鍵值配對：** 將多個值縮合成單一鍵值對。 在序列化的鍵值對中，特殊指示符分隔鍵值集內的值。

標準和序號的索引鍵值皆可包含單一或多個值。 下表提供標準和序號鍵值格式的範例。

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 格式 </th>
   <th colname="col2" class="entry"> 單鍵值對 </th>
   <th colname="col3" class="entry"> 多鍵值對 </th>
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

## 分隔字元和分隔符號 {#delimiters-separators}

在鍵和值內和之間分隔值的字元稱為和 *`delimiters`* 和 *`separators`*。 當您以序列格式將區段傳送至目的地時，這些變得尤其重要。 序列化可讓您使用單一鍵傳入多個值，並結合鍵值配對。 分隔字元和分隔符的定義如下：

* **鍵值分隔符號：** 分隔鍵值對中的鍵和值。
* **金鑰值分隔字元：** 分隔鍵值對集。
* **序號分隔符號：** 在一組序列化的鍵值對中分隔多個值。

## 範例 {#examples}

有了 [!UICONTROL Destination Builder] 您，可以以多種不同的方式格式化索引鍵值資料。 讓我們來看一下每種類型的一些示例。

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
   <td colname="col3"> <p>一組簡單的鍵值對。 範例包含下列元素： </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">索引鍵： X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">值： 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">分隔符號： = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">金鑰值分隔字元： &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>多對鍵值配對</b> （非串列） </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>一組多個鍵值對，用單獨的鍵值集傳遞值。 範例包含下列元素： </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">鍵： X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">值： 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">分隔符號： = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">金鑰值分隔字元： &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>串列單鍵</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>一個鍵值集，用一個鍵傳遞多個值。 由於此索引鍵有多個值，因此稱為序列化索引鍵值對。 範例包含下列元素： </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">索引鍵： X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">值： 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">分隔符號： = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">序號分隔符號： 分號 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>多對鍵值配對</b> （串列） </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>一組多個鍵值對，會在個別鍵上傳入多個值。 範例包含下列元素： </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">鍵： X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">值： 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">分隔符號： = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">分隔字元: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">序號分隔符號： 分號 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 目標序列化 {#destination-serialized}

序列化的目的地將多個特性結合為單一字串，並將該資訊傳送至目的地。

<!-- c_dest_serialized.xml -->

串列化資料傳輸有助於提高效率，因為多個特性會依序觸發，而非並行觸發。 這可讓目標伺服器在回應其他要求之前，有足夠的時間接收、處理和傳回資料。

### 支援的目標

在中 [!DNL Audience Manager]，您可以序列化資料，並將資料傳送至任何您想要使用的目的地。 不過，在使用此功能之前，您必須先知道目標，以 [!DNL URL] 及放置某些必要或可選宏的位置。 從您的目的地合作夥伴取得有關巨集放置的資訊。 如需詳 [細資訊，請參閱](../../features/destinations/destination-macros.md#destination-macros-defined) 「定義的目標巨集」。