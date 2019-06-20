---
description: 索引鍵值對包含相關的元素A索引鍵，它是一個常數，用來定義資料集(例如性別、顏色、價格)和值，這是屬於該集的變數(例如男性/女性、綠色、100)。「目標產生器」將格式設定為索引鍵值配對。
seo-description: 索引鍵值對包含相關的元素A索引鍵，它是一個常數，用來定義資料集(例如性別、顏色、價格)和值，這是屬於該集的變數(例如男性/女性、綠色、100)。「目標產生器」將格式設定為索引鍵值配對。
seo-title: 標準和序列鍵值配對
solution: Audience Manager
title: 標準和序列鍵值配對
uuid: 43789419-5b3f-4e62-b2 e0-272240bdd41
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Standard and Serial Key-Value Pairs {#standard-and-serial-key-value-pairs}

關鍵值配對包含相關元素：索引鍵，它是一個常數，用來定義資料集(例如性別、顏色、價格)和值，這是屬於該組的變數(例如男性/女性、綠色、100)。[!UICONTROL Destination Builder] 將資料格式化為關鍵值配對。

## Basic Key-Value Pairs {#basic-key-value-pairs}

完整設定後，基本值組的基本組合可能如下所示：

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serial Key-Value Pairs {#standard-serial-key-value-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format.

* **標準索引鍵值配對：** 將目標資料格式化為個別的索引鍵值配對。每個索引鍵都明確表述，即使再次使用，也能定義不同的值。
* **序列化索引鍵值配對：** 將多個值壓縮為單一索引鍵值配對。在序列化索引鍵值配對中，特殊指標會分隔機碼值集內的值。

標準和序列化索引鍵值都可以包含單一或多個值。下表提供標準和串行鍵值格式的範例。

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 格式設定 </th>
   <th colname="col2" class="entry"> 單一索引鍵值配對 </th>
   <th colname="col3" class="entry"> 多個索引鍵值配對 </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>標準</b> </p> </td>
   <td colname="col2"> <p> <code> x=1&amp; x=2 </code> </p> </td>
   <td colname="col3"> <p> <code> x=1&amp; x=2&amp; y=3&amp; y=4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>序列化序列化</b> </p> </td> 
   <td colname="col2"> <p> <code> x=1；2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x=1；&amp; y=3；4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Delimiters and Separators {#delimiters-separators}

The characters that separate values within and between keys and values are known as *`delimiters`* and *`separators`*. 當您以序號格式傳送區段至目的地時，這些變得格外重要。序列化可讓您以單一索引鍵傳入多個值，並結合索引鍵值配對。分隔符號和分隔符號定義如下：

* **索引鍵值分隔符號：** 分隔索引鍵值對內的索引鍵和值。
* **索引鍵值分隔字元：** 分隔索引鍵值配對集。
* **串行分隔符號：** 分隔序列化索引鍵值配對集合內的多個值。

## 範例 {#examples}

With [!UICONTROL Destination Builder] you can format key-value data in several different ways. 讓我們來看看每種類型的一些範例。

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 索引鍵值配對範例 </th> 
   <th colname="col2" class="entry"> 範例 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>標準單鍵</b> </p> </td> 
   <td colname="col2"> <p> <code> X=1&amp; X=2 </code> </p> </td> 
   <td colname="col3"> <p>一組簡單的關鍵值配對。範例包含下列元素： </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">索引鍵：X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">值：1，2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">分隔符號：= </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">索引鍵值分隔字元：&amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>多個索引鍵值配對</b> (非序號) </p> </td> 
   <td colname="col2"> <p> <code> X=1&amp; X=2&amp; Y=3&amp; Y=4 </code> </p> </td> 
   <td colname="col3"> <p>一組多個索引鍵值配對，用以傳遞具有個別索引鍵值集的值。範例包含下列元素： </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">金鑰：X，Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">值：1，2，3，4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">分隔符號：= </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">索引鍵值分隔字元：&amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>序號單鍵</b> </p> </td> 
   <td colname="col2"> <p> <code> X=1；2；3 </code> </p> </td> 
   <td colname="col3"> <p>以單一索引鍵傳入多個值的機碼值集。因為此金鑰有多個值，所以稱為序列化索引鍵值配對。範例包含下列元素： </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">索引鍵：X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">值：1，2，3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">分隔符號：= </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">串行分隔符號：分號 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>多個索引鍵值配對</b> (序號) </p> </td> 
   <td colname="col2"> <p> <code> X=1；&amp; Y=3；4 </code> </p> </td> 
   <td colname="col3"> <p>在個別索引鍵上傳入多個值的一組索引鍵值配對。範例包含下列元素： </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">金鑰：X，Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">值：1，2，3，4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">分隔符號：= </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">分隔字元: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">串行分隔符號：分號 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Destination Serialization {#destination-serialized}

序列化目的地會將多個特性合併為單一字串，並將該資訊傳送至目的地。

<!-- c_dest_serialized.xml -->

序列化資料傳輸有助於提高效率，因為多個特性循序引發，而非並行引發。這為目標伺服器提供足夠的時間來接收、處理和傳回資料，再回應其他要求。

### 支援的目標

In [!DNL Audience Manager], you can serialize and send data to just about any destination you want to work with. However, before using this feature, you will need to know the destination [!DNL URL] and where to place some required or optional macros. 從目的地合作夥伴取得有關巨集位置的資訊。See [Destination Macros Defined](../../features/destinations/destination-macros.md#destination-macros-defined) for more information.