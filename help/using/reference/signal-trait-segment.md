---
description: 說明Audience manager區段的元件、用來設定觀眾資格標準的運算式，以及在事件呼叫中如何傳送資料。
seo-description: 說明Audience manager區段的元件、用來設定觀眾資格標準的運算式，以及在事件呼叫中如何傳送資料。
seo-title: 信號、特徵和區段
solution: Audience Manager
title: 信號、特徵和區段
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 信號、特徵和區段{#signals-traits-and-segments}

說明Audience manager區段的元件、用來設定觀眾資格標準的運算式，以及在事件呼叫中如何傳送資料。

<!-- 

c_signal_trait_segment.xml

 -->

**構圖與用途**

[!DNL Audience Manager] 資料包含訊號、特徵、區段和相關的資格規則。 資料元素和規則會結合以建立區段。 區段會將網站訪客組織成相關群組。 下表定義了段中的三個主要 [!DNL Audience Manager] 元件。

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 由 </th> 
   <th colname="col3" class="entry"> 範例 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>訊號</b> </td> 
   <td colname="col2"> <p>訊號是 <span class="keyword"> Audience Manager中最小的資料單位</span> ，並以鍵 <a href="../reference/key-value-pairs-explained.md"> 值配對表示</a>。 </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">索引鍵是定義資料集（例如性別、顏色、價格）的常數。 </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">該值是與常數相關的變數（例如，男性／女性、綠色、100）。 </li> 
    </ul> <p>比較運算子會加入鍵值對，並設定它們之間的關係。 </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product=camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> price&gt;1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type=digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>特性</b> </td> 
   <td colname="col2"> <p>一個或多個信號的組合。 </p> <p>布林運算式和比較運算子可讓您建立特徵限定規則。 </p> <p>結合特徵和特徵群組，建立精確的資格要求。 </p> </td> 
   <td colname="col3"> <p>您可從可用訊號建立「高階相機瀏覽器」規則，表示為： </p> <p><code> product=camera AND price&gt;1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>區段</b> </td> 
   <td colname="col2"> <p>共用一組共同屬性並符合相關特徵資格的使用者。 </p> <p>布林運算式，以及時近／頻率需求，可讓您建立區段限定規則。 </p> <p>結合特徵和區段規則，建立精確的資格要求。 </p> </td> 
   <td colname="col3"> <p>您可以從可用特性和訊號建立區段規則，表示為： </p> <p><code> (product=camera AND type=digital SLR) OR (price&gt;1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

請使用下圖來記住信號、特徵和區段之間的關係。

![](assets/signals-traits-segments.png)

**使用視覺化工具和程式碼編輯器建立特徵和區段規則**

用戶端在使用者介面中使用視覺化工具和程式碼編輯器來管理特 [!DNL Audience Manager] 徵和區段。 視覺化工具可讓您使用搜尋功能、快顯選項、下拉式選單以及拖放功能來建立規則。 程式碼編輯器提供進階使用者程式設計方式，以開發受眾細分標準。

**事件呼叫傳送資料至Audience Manager**

事件呼叫會從您的網站傳送資料至 [!DNL Audience Manager]。 呼叫在HTTP請求中包含信號、特徵和區段資料。 事件本身是URL字串之 `/event` 後的一切。 如下列範例所示，此程式只需要單一事件呼叫即可將多個變數傳入 [!DNL Audience Manager]。

```
https://<domain>/event?product=camera&price>100
```

>[!MORELIKETHIS]
>
>* [區段：目的、構成和規則](../features/segments/segments-purpose.md)

