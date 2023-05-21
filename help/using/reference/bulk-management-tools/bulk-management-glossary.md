---
description: 已定義列標題標籤。
seo-description: Column header labels defined.
seo-title: Bulk Management Tools Glossary
solution: Audience Manager
title: 大量管理工具字彙表
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: BAAAM
exl-id: 036d16c7-1546-4539-a318-455b98e10026
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 4%

---

# 大量管理工具字彙表{#bulk-management-tools-glossary}

已定義列標題標籤。

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[RBAC組權限](../../features/administration/administration-overview.md) 在 [!DNL Audience Manager] UI在 [!UICONTROL Bulk Management Tools]。

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 列標題 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 資料源ID</span> </p> </td> 
   <td colname="col2"> <p>的ID <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 資料源</a> 要成批返回或分配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivedSignalId</span> </p> </td> 
   <td colname="col2"> <p>A <a href="../../features/derived-signals.md"> 衍生信號</a> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 說明</span> </p> </td> 
   <td colname="col2"> <p>您可以為對象提供的簡短、資訊性說明。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 目標ID</span> </p> </td> 
   <td colname="col2"> <p>的ID <a href="../../features/destinations/destinations.md"> 目標</a> 要映射或刪除。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 目標映射ID</span> </p> </td> 
   <td colname="col2"> <p>將段映射到目標時分配給該段的特殊ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 資料夾ID</span> </p> </td> 
   <td colname="col2"> <p>段或特徵資料夾的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 名稱</span> </p> </td> 
   <td colname="col2"> <p>您正在使用的對象的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 父資料夾ID</span> </p> </td> 
   <td colname="col2"> <p>包含其他資料夾的段或特性資料夾的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>段ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 源密鑰</span> </p> </td> 
   <td colname="col2"> <p>信號是傳入到的資料位 <span class="keyword"> Audience Manager</span> 基於用戶活動。 這些作為 <a href="../../reference/key-value-pairs-explained.md"> 鍵值對</a>。 源鍵是不變的常數。 它有助於對可更改的源值進行分類。 請參閱 <a href="../../features/derived-signals.md"> 派生信號</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>源值是作為部分傳遞的變數 <a href="../../reference/key-value-pairs-explained.md"> 鍵值對</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>指示段何時開始發送到目標。 使用 <i>yyyy-mm-dd</i> 的子菜單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 目標密鑰</span> </p> </td> 
   <td colname="col2">導出信號中使用的鍵。 請參閱 <a href="../../features/derived-signals.md"> 派生信號</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 目標值</span> </p> </td> 
   <td colname="col2"> <p>用派生的信號鍵傳遞的值。 請參閱 <a href="../../features/derived-signals.md"> 派生信號</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>傳遞到非基於Cookie的目標的ID。 對於基於cookie的目標，這是 <a href="../../reference/key-value-pairs-explained.md"> 鍵值對</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule/segmentRule</span> </p> </td> 
   <td colname="col2"> <p>用於收集資料的實際特性或段規則。 批量請求返回在中建立的規則 <span class="keyword"> Audience Manager</span> 和 <a href="../../features/traits/about-trait-builder.md"> 特徵規則生成器</a> 或 <a href="../../features/segments/segment-builder.md"> 段規則生成器</a>。 您還可以使用這些工具來構建規則，並在更新段或特性時批量應用它們。 </p> <p>另請參見 <a href="../../reference/bulk-management-tools/bulk-rules.md"> 建立或更新特徵規則和段規則</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>標識特徵類型的字串。 選項包括: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>當用戶符合段時，DIL觸發的像素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 值別名</span> </p> </td> 
   <td colname="col2"> <p>中的鍵 <a href="../../reference/key-value-pairs-explained.md"> 鍵值對</a> 傳遞到cookie目標。 </p> </td> 
  </tr> 
 </tbody> 
</table>
