---
description: 列標題已定義。
seo-description: 列標題已定義。
seo-title: 大量管理工具字彙表
solution: Audience Manager
title: 大量管理工具字彙表
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: BAAAM
exl-id: 036d16c7-1546-4539-a318-455b98e10026
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 5%

---

# 大量管理工具字彙表{#bulk-management-tools-glossary}

列標題已定義。

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[UI中](../../features/administration/administration-overview.md) 指派的RBAC [!DNL Audience Manager] 群組權限會遵循 [!UICONTROL Bulk Management Tools]。

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
   <td colname="col2"> <p>要大量返回或分配的<a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings">資料源</a>的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivedSignalId</span> </p> </td> 
   <td colname="col2"> <p>A <a href="../../features/derived-signals.md">派生信號</a> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 說明</span> </p> </td> 
   <td colname="col2"> <p>您可為物件提供簡短且內容豐富的說明。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>要映射或刪除的<a href="../../features/destinations/destinations.md">目標</a>的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>區段對應至目的地時指派的特殊ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>區段或特徵資料夾的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 名稱</span> </p> </td> 
   <td colname="col2"> <p>您正在使用的物件的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>包含其他資料夾之區段或特徵資料夾的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>區段ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>訊號是根據使用者活動而傳入<span class="keyword">Audience Manager</span>的資料位。 這些值會以<a href="../../reference/key-value-pairs-explained.md">鍵值配對</a>傳送。 源密鑰是不變的常數。 有助於將可變更的來源值分類。 請參閱<a href="../../features/derived-signals.md">衍生訊號</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>源值是作為<a href="../../reference/key-value-pairs-explained.md">鍵值對</a>一部分傳入的變數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>指出區段何時可開始傳送至目的地。 使用<i>yyyy-mm-dd</i>格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">衍生訊號中使用的鍵值。 請參閱<a href="../../features/derived-signals.md">衍生訊號</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>用衍生訊號鍵傳入的值。 請參閱<a href="../../features/derived-signals.md">衍生訊號</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>傳遞至非Cookie型目的地的ID。 對於Cookie型目的地，這是<a href="../../reference/key-value-pairs-explained.md">索引鍵值組</a>中的索引鍵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>用於收集資料的實際特徵或區段規則。 大量請求會傳回在<span class="keyword">Audience Manager</span>中使用<a href="../../features/traits/about-trait-builder.md">特徵規則產生器</a>或<a href="../../features/segments/segment-builder.md">區段規則產生器</a>建立的規則。 您也可以使用這些工具來建立規則，並在更新區段或特徵時大量套用。 </p> <p>另請參閱<a href="../../reference/bulk-management-tools/bulk-rules.md">建立或更新特徵規則和區段規則</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>識別特徵類型的字串。 選項包括: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>使用者符合區段資格時由DIL引發的像素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>傳遞至Cookie目的地的<a href="../../reference/key-value-pairs-explained.md">鍵值組</a>中的鍵值。 </p> </td> 
  </tr> 
 </tbody> 
</table>
