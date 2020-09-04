---
description: 已定義列標題標籤。
seo-description: 已定義列標題標籤。
seo-title: 大量管理工具字彙表
solution: Audience Manager
title: 大量管理工具字彙表
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: baaam
translation-type: tm+mt
source-git-commit: adab01a81c0002d28c2387a20d8ae284e11a5e41
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 5%

---


# 大量管理工具字彙表{#bulk-management-tools-glossary}

已定義列標題標籤。

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[UI中指派的](../../features/administration/administration-overview.md) RBAC群組權 [!DNL Audience Manager] 限在中接受 [!UICONTROL Bulk Management Tools]。

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
   <td colname="col2"> <p>您要大量傳 <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 回或指派</a> 之資料來源的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivedSignalId</span> </p> </td> 
   <td colname="col2"> <p>衍 <a href="../../features/derived-signals.md"> 生信號</a> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 說明</span> </p> </td> 
   <td colname="col2"> <p>您可以提供給物件的簡短、資訊豐富的說明。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>要映射或刪 <a href="../../features/destinations/destinations.md"> 除的</a> 目標ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>區段對應至目標時指派的特殊ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>區段或特徵資料夾的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 名稱</span> </p> </td> 
   <td colname="col2"> <p>您正在使用的對象的名稱。 </p> </td> 
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
   <td colname="col2"> <p>訊號是根據使用者活動傳入 <span class="keyword"> Audience Manager</span> 的資料位。 這些值會以 <a href="../../reference/key-value-pairs-explained.md"> 鍵值對的形式傳送</a>。 原始碼是不變的常數。 它有助於將可變更的來源值分類。 請參閱 <a href="../../features/derived-signals.md"> 衍生訊號</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>源值是作為鍵值對的一部分傳入 <a href="../../reference/key-value-pairs-explained.md"> 的變數</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>指出區段何時可開始傳送至目的地。 使用 <code>yyyy-mm-dd</code> 格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">導出信號中使用的鍵。 請參閱 <a href="../../features/derived-signals.md"> 衍生訊號</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>與衍生的信號鍵一起傳遞的值。 請參閱 <a href="../../features/derived-signals.md"> 衍生訊號</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>傳遞至非Cookie型目標的ID。 對於Cookie型目標，這是金鑰值對 <a href="../../reference/key-value-pairs-explained.md"> 中的金鑰</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>用於收集資料的實際特徵或區段規則。 大量請求會傳回在 <span class="keyword"> Audience Manager中使用特徵規則產生器</span> ，或區段規則產生器建 <a href="../../features/traits/about-trait-builder.md"> 立的規則</a><a href="../../features/segments/segment-builder.md"></a>。 您也可以使用這些工具來建立規則，並在更新區段或特徵時大量套用規則。 </p> <p>See also, <a href="../../reference/bulk-management-tools/bulk-rules.md"> Create or Update Trait Rules and Segment Rules</a>. </p> </td> 
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
   <td colname="col2"> <p>當使用者符合區段資格時，由DIL引發像素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>傳遞至Cookie目 <a href="../../reference/key-value-pairs-explained.md"> 標的金鑰</a> -值對中的金鑰。 </p> </td> 
  </tr> 
 </tbody> 
</table>

