---
description: 本文介紹建立特性規則時必須附加到關鍵變數的前置詞。
seo-description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-title: Prefix Requirements for Key Variables
solution: Audience Manager
title: 關鍵變數的前置詞要求
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
exl-id: 67fe0c74-6831-48cb-90cf-417ebbf7f272
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 4%

---

# 關鍵變數的前置詞要求 {#prefix-requirements-for-key-variables}

本文介紹建立特性規則時必須附加到關鍵變數的前置詞。

<!-- r_tb_variable_prefixes.xml -->

## 密鑰變數前置詞的用途

建立時 [!UICONTROL Trait Builder] 規則，在鍵變數前加上推薦的前置詞非常重要。 這些前置詞標識傳入的資料類型並幫助避免在 [!DNL Audience Manager]。 通常，您可以為變數指定任何名稱，但如果關鍵變數名稱與事件調用中的變數名稱不匹配，則規則的資料將不會處理。

## 鍵變數的前置詞

下表定義了使用的常用前置詞 [!UICONTROL Trait Builder]。

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 鍵變數前置詞 </th> 
   <th colname="col2" class="entry"> 標識變數 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>作為特定於客戶。 這是從您自己的屬性發送的關鍵資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>在 <span class="keyword"> Audience Manager</span> 級別。 此資料在 <span class="keyword"> Audience Manager</span> 生態系統。 請參閱 <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> DCS API調用的支援屬性</a> 的子菜單。</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>包含 <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP頭</a> 的下界。 包括標題參數，如 <code> referer</code>。<code> IP</code>。 <code> accept-language</code>的子菜單。 </p> <p> <p>注：對於使用9.0以上DIL版本的客戶，使用 <code> h_referer</code> 信號在Safari瀏覽器上無法工作。 隨著 <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, Safari瀏覽器可以將demdex.net域分類為跟蹤器，並將截斷資料收集請求上的引用者，以僅包含原點，而不包含完整URL。 請參閱 <a href="../../dil/dil-overview.md#get-implement-dil-code">獲取和實施DIL代碼</a> 的子菜單。<p>使用此前置詞的信號未在 <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">信號搜索</a>。</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>我們的 <span class="wintitle"> 資料收集伺服器</span> 允許傳遞私有參數。 基本上，任何以 <code> p_</code> 將用於特徵評估，但不會記錄到下游或儲存。 </p> <p>示例：給 <code> /event?p_age=23</code> 和一種 <code> YoungPeople = p_age &lt; 25</code>這個特徵會實現，但是 <code> p_age=23</code> 請求後將刪除key-value對，不會記錄。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [基本資訊概述](../../features/traits/create-onboarded-rule-based-traits.md)
>* [管理特徵規則](../../features/traits/manage-trait-rules.md#managing-trait-rules)

