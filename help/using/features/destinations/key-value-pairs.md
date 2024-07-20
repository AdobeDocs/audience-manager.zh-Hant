---
description: A [!DNL key-value pair] 包含 [!DNL related elements]。 索引鍵，是定義資料集的常數（例如，性別、顏色、價格），以及值，這是屬於該集的變數（例如，男性/女性、綠色、100）。 Destination Builder會傳送格式化為索引鍵值配對的資料。
solution: Audience Manager
title: 標準與序列 [!DNL Key-value pairs]
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Destination Basics
exl-id: b37c829b-66be-4c31-8198-bc032371279e
source-git-commit: 0dfe96a4644c61fb5bc22e4791bfd09c574dcf34
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# 標準和序列索引鍵值配對 {#standard-and-serial-key-value-pairs}

機碼 — 值組包含相關元素：機碼，是定義資料集的常數（例如：性別、顏色、價格），以及值，是屬於該集的變數（例如，男性/女性、綠色、100）。 [!UICONTROL Destination Builder]會傳送格式化為機碼值組的資料。

## 基本索引鍵值配對 {#basic-key-value-pairs}

格式完整，基本索引鍵/值組可能如下所示：

* `gender = male`
* `color = green`
* `price > 100`

## 標準和序列索引鍵值配對 {#standard-serial-key-value-pairs}

目的地接受&#x200B;*`standard`*&#x200B;或&#x200B;*`serialized`*&#x200B;格式的機碼值資料。

* **標準機碼值組：**&#x200B;將目的地資料格式化為個別的機碼值組。 每個鍵都會明確指出，即使再次用來定義不同的值。
* **序列化的機碼值組：**&#x200B;將多個值壓縮成單一機碼值組。 在序列化的索引鍵/值組中，特殊指示器會分隔索引鍵/值集中的值。

標準和序列化索引鍵值都可以包含單一或多個值。 下表提供標準和序列索引鍵值格式的範例。

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 格式化 </th>
   <th colname="col2" class="entry"> 單一鍵值組 </th>
   <th colname="col3" class="entry"> 多個鍵值組 </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>標準</b> </p> </td>
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td>
   <td colname="col3"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>已序列化</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## 分隔符號和分隔符號 {#delimiters-separators}

在索引鍵和值之間分隔值的字元稱為&#x200B;*`delimiters`*&#x200B;和&#x200B;*`separators`*。 當您以序列格式將區段傳送至目的地時，這些變得尤其重要。 序列化可讓您使用單一索引鍵傳遞多個值，並組合索引鍵/值組。 分隔符號和分隔符號的定義如下：

* **機碼值分隔符號：**&#x200B;分隔機碼值組中的機碼和值。
* **索引鍵值分隔符號：**&#x200B;分隔索引鍵值配對組。
* **序列分隔符號：**&#x200B;分隔序列化機碼值組內的多個值。

## 範例 {#examples}

透過[!UICONTROL Destination Builder]，您可以用數種不同的方式格式化機碼值資料。 讓我們來看看每種型別的一些範例。

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
   <td colname="col1"> <p> <b>標準單一金鑰</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>一組簡單的鍵值組。 此範例包含下列元素： </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">索引碼： X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">值： 1， 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">分隔符號： = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">索引鍵值分隔符號： &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>多個索引鍵值配對</b> （非序列） </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>一組多重機碼值組，會以個別的機碼值組傳入值。 此範例包含下列元素： </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">索引鍵： X， Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">值： 1、2、3、4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">分隔符號： = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">索引鍵值分隔符號： &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>序列單一金鑰</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>使用單一鍵傳入多個值的鍵值集。 因為此索引鍵有多個值，所以稱為序列化索引鍵值組。 此範例包含下列元素： </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">索引碼： X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">值： 1、2、3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">分隔符號： = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">序列分隔符號：分號 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>多個索引鍵值配對</b> （序列） </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>一組多重索引鍵/值組，可在個別索引鍵上傳入多個值。 此範例包含下列元素： </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">索引鍵： X， Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">值： 1、2、3、4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">分隔符號： = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">分隔符號： &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">序列分隔符號：分號 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 目的地序列化 {#destination-serialized}

序列化目的地會將多個特徵結合為單一字串，並將該資訊傳送至目的地。

<!-- c_dest_serialized.xml -->

序列化資料傳輸有助於提高效率，因為多個特徵會依序引發，而非並行引發。 如此可在回應其他要求之前，為目的地伺服器提供足夠的時間來接收、處理和傳回資料。

### 支援的目的地

在[!DNL Audience Manager]中，您可以將資料序列化並傳送至您想要使用的幾乎任何目的地。 不過，使用此功能之前，您必須知道目的地[!DNL URL]以及放置某些必要或選擇性巨集的位置。 從您的目的地合作夥伴取得有關巨集位置的資訊。 如需詳細資訊，請參閱[定義的巨集目的地](../../features/destinations/destination-macros.md#destination-macros-defined)。
