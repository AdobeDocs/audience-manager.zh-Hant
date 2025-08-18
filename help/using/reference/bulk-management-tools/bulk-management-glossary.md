---
description: 已定義欄標題標籤。
seo-description: Column header labels defined.
seo-title: Bulk Management Tools Glossary
solution: Audience Manager
title: 大量管理工具字彙表
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: BAAAM
exl-id: 036d16c7-1546-4539-a318-455b98e10026
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 0%

---

# 大量管理工具字彙表{#bulk-management-tools-glossary}

已定義欄標題標籤。

>[!IMPORTANT]
>
>大量管理工具並非正式支援的Adobe產品。 客戶服務提供的疑難排解與支援將依個別情況處理。

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>在[ UI中指派的](../../features/administration/administration-overview.md)RBAC群組許可權[!DNL Audience Manager]已在[!UICONTROL Bulk Management Tools]中接受。

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄標題 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> dataSourceId</span> </p> </td> 
   <td colname="col2"> <p>您要傳回或大量指派的<a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings">資料來源</a>識別碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivedSignalId</span> </p> </td> 
   <td colname="col2"> <p><a href="../../features/derived-signals.md">衍生訊號</a> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">描述</span> </p> </td> 
   <td colname="col2"> <p>您可以為物件提供的簡短資訊性說明。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">目的地識別碼</span> </p> </td> 
   <td colname="col2"> <p>您要對應或刪除的<a href="../../features/destinations/destinations.md">目的地</a>識別碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>區段對應至目的地時，系統會將特殊ID指派給區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>區段或特徵資料夾的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">名稱</span> </p> </td> 
   <td colname="col2"> <p>您正在使用的物件名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>包含其他資料夾的區段或特徵資料夾的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>區段ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>訊號是根據使用者活動傳入<span class="keyword"> Audience Manager</span>的資料位元。 這些會以<a href="../../reference/key-value-pairs-explained.md">機碼值組</a>傳輸。 來源金鑰是不變更的常數。 它有助於將可變更的來源值分類。 請參閱<a href="../../features/derived-signals.md">衍生訊號</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>來源值是作為<a href="../../reference/key-value-pairs-explained.md">機碼值組</a>的一部分傳入的變數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>表示區段何時可以開始傳送至目的地。 使用<i>yyyy-mm-dd</i>格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">用於衍生訊號的金鑰。 請參閱<a href="../../features/derived-signals.md">衍生訊號</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>使用衍生訊號鍵傳入的值。 請參閱<a href="../../features/derived-signals.md">衍生訊號</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">特徵別名</span> </p> </td> 
   <td colname="col2"> <p>傳遞到非Cookie型目的地的ID。 對於以Cookie為基礎的目的地，這是<a href="../../reference/key-value-pairs-explained.md">機碼值組</a>中的機碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>用來收集資料的實際特徵或區段規則。 大量請求會傳回在<span class="keyword"> Audience Manager</span>中以<a href="../../features/traits/about-trait-builder.md">特徵規則產生器</a>或<a href="../../features/segments/segment-builder.md">區段規則產生器</a>建立的規則。 您也可以使用這些工具來建立規則，並在更新區段或特徵時大量套用規則。 </p> <p>另請參閱<a href="../../reference/bulk-management-tools/bulk-rules.md">建立或更新特徵規則和區段規則</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">特徵型別</span> </p> </td> 
   <td colname="col2"> <p>識別特徵型別的字串。 選項包括: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>使用者符合區段資格時DIL引發的畫素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p><a href="../../reference/key-value-pairs-explained.md">機碼值組</a>中的機碼已傳遞至Cookie目的地。 </p> </td> 
  </tr> 
 </tbody> 
</table>
