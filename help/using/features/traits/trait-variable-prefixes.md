---
description: 本文說明建立特徵規則時，必須附加至關鍵變數的前置詞。
seo-description: 本文說明建立特徵規則時，必須附加至關鍵變數的前置詞。
seo-title: 關鍵變數的前置詞要求
solution: Audience Manager
title: 關鍵變數的前置詞要求
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
translation-type: tm+mt
source-git-commit: 2206b5e40f7024084953fed52bb02fcc46ea36f1

---


# 關鍵變數的前置詞要求 {#prefix-requirements-for-key-variables}

本文說明建立特徵規則時，必須附加至關鍵變數的前置詞。

<!-- r_tb_variable_prefixes.xml -->

## 關鍵變數前置詞的用途

建立規則 [!UICONTROL Trait Builder] 時，請務必在索引鍵變數前加上建議的首碼。 這些字首可識別傳入的資料類型，並有助於避免內部的命名空間衝突 [!DNL Audience Manager]。 通常，您可以為變數指定任何名稱，但如果關鍵變數名稱與事件呼叫中的變數名稱不符，規則的資料將不會處理。

## 關鍵變數的前置詞

下表定義了使用的常用前置詞 [!UICONTROL Trait Builder]。

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 金鑰變數首碼 </th> 
   <th colname="col2" class="entry"> 識別變數 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>作為客戶專屬。 這是從您自己的屬性傳入的關鍵資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>在Audience manager <span class="keyword"> 層級</span> 。 此資料在Audience Manager生態系統中 <span class="keyword"> 是一致的</span> 。 如需 <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> 更完整的清單，請參閱DCS API呼叫的支援屬性</a> 。 <p>使用此前置詞的信號不會在「信號搜索」 <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">中呈現</a>。</p></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>包含 <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP標題資訊</a> 。 包含標題參 <code> referer</code>數<code> IP</code>, <code> accept-language</code>如、 </p> <p> <p>注意：對於使用9.0以上DIL版本的客戶，使用此訊號的資料收 <code> h_referer</code> 集將無法在Safari瀏覽器上運作。 隨著 <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0的推出</a>,Safari瀏覽器可能會將demdex.net網域分類為追蹤器，並會在資料收集要求上截斷反向連結，以僅包含原始網域，而非完整URL。 請參 <a href="../../dil/dil-overview.md#get-implement-dil-code">閱取得和實作DIL程式碼</a> ，以取得最新的DIL版本。<p>使用此前置詞的信號不會在「信號搜索」 <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">中呈現</a>。</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>我們的 <span class="wintitle"> 資料收集伺服器</span> ，允許傳遞私用參數。 基本上，任何以開頭的參 <code> p_</code> 數都會用於特徵評估，但不會記錄在下游或儲存。 </p> <p>範例：若 <code> /event?p_age=23</code> 有某個特 <code> YoungPeople = p_age &lt; 25</code>徵，則會實現該特徵，但 <code> p_age=23</code> key-value對會在請求後丟棄，且不會記錄。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [基本資訊概觀](../../features/traits/create-onboarded-rule-based-traits.md)
>* [管理特徵規則](../../features/traits/manage-trait-rules.md#managing-trait-rules)

