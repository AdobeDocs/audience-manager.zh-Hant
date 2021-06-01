---
description: 本文說明建立特徵規則時，您必須附加至關鍵變數的前置詞。
seo-description: 本文說明建立特徵規則時，您必須附加至關鍵變數的前置詞。
seo-title: 關鍵變數的前置詞要求
solution: Audience Manager
title: 關鍵變數的前置詞要求
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: 特徵
exl-id: 67fe0c74-6831-48cb-90cf-417ebbf7f272
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 5%

---

# 關鍵變數的前置詞要求 {#prefix-requirements-for-key-variables}

本文說明建立特徵規則時，您必須附加至關鍵變數的前置詞。

<!-- r_tb_variable_prefixes.xml -->

## 關鍵變數前置詞的用途

建立[!UICONTROL Trait Builder]規則時，請務必以建議的首碼為關鍵變數加上前置詞。 這些前置詞標識傳入的資料類型，有助於避免[!DNL Audience Manager]內的命名空間衝突。 一般而言，您可以為變數指定任何名稱，但如果關鍵變數名稱與事件呼叫中的變數名稱不符，規則的資料將不會處理。

## 關鍵變數的前置詞

下表定義[!UICONTROL Trait Builder]使用的常用前置詞。

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 關鍵變數首碼 </th> 
   <th colname="col2" class="entry"> 識別變數 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>客戶專屬。 這是從您自己的屬性傳入的關鍵資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>在<span class="keyword">Audience Manager</span>層級。 此資料在<span class="keyword">Audience Manager</span>生態系統中均一。 如需更完整的清單，請參閱<a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> DCS API呼叫的支援屬性</a> 。</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>其中包含<a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP標題</a>資訊。 包括標題參數，如<code> referer</code>、<code> IP</code>、<code> accept-language</code>等。 </p> <p> <p>注意：若客戶使用9.0以前的DIL版本，使用<code> h_referer</code>訊號的資料收集將無法在Safari瀏覽器上運作。 導入<a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>後，Safari瀏覽器可能會將demdex.net網域分類為追蹤器，並會截斷資料收集請求上的反向連結，使其僅包含來源，而非完整URL。 如需最新DIL版本，請參閱<a href="../../dil/dil-overview.md#get-implement-dil-code">取得並實作DIL程式碼</a>。<p>使用此首碼的訊號不會出現在<a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Signal Search</a>中。</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>我們的<span class="wintitle">資料收集伺服器</span>允許傳遞私有參數。 基本上，任何以<code> p_</code>開頭的參數都會用於特徵評估，但不會在下遊記錄或儲存。 </p> <p>範例：在<code> /event?p_age=23</code>和<code> YoungPeople = p_age &lt; 25</code>等特徵中，將會實現特徵，但在請求後會捨棄<code> p_age=23</code>索引鍵值組，且不會記錄。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [基本資訊概述](../../features/traits/create-onboarded-rule-based-traits.md)
* [管理特徵規則](../../features/traits/manage-trait-rules.md#managing-trait-rules)

