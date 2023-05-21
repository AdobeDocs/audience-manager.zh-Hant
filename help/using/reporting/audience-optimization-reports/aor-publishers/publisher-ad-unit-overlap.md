---
description: 「Ad Unit Overlap」報告顯示為熱圖，它突出顯示「Ad Units」之間的高和低重疊。
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: 廣告單位重疊
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 2%

---

# 廣告單位重疊{#ad-unit-overlap}

的 **[!UICONTROL Ad Unit Overlap]** 報告顯示為一個熱度圖，突出顯示Ad Units之間的高重疊和低重疊。

## 使用案例 {#use-cases}

使用 **[!UICONTROL Ad Unit Overlap]** 報告，您可以深入瞭解您的受眾在Web屬性中的重疊位置。 該報告將考慮您的100個頂級相關屬性，並顯示它們之間的重疊。

## 使用廣告單位重疊報表 {#using-the-report}

使用 **[!UICONTROL Top N Base Ad Units]** 和 **[!UICONTROL Top N Overlapping Ad Units]** 控制項以選擇重疊所需的廣告單位數。 您可以為每個項目選擇最多100個項目。

使用 **日期範圍** 和 **日期至** 控制項來調整回顧範圍。 請注意，7天和30天回溯期間僅適用於星期日。

使用 **[!UICONTROL Base Ad Unit]** 和 **[!UICONTROL Overlap Ad Unit]** 控制項，以選擇要在重疊報告中顯示的廣告單位。

>[!IMPORTANT]
>
>啟用時 [!UICONTROL Audience Optimization for Publishers]，必須包括描述性元資料 [!UICONTROL Ad Unit IDs]，如第3步中所述 [將GoogleAd Manager（以前叫DFP）資料檔案導入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 通過執行此操作，您可以確保報告將Web屬性的詳細資訊 [!UICONTROL Ad Unit] 而不是 [!UICONTROL Ad Unit ID]。

## 解釋結果 {#interpreting-results}

您 [!UICONTROL Ad Unit Overlap] 報告可能與下面的報告相似。 將滑鼠懸停在任何單元格上以獲取有關該特定重疊的詳細資訊。 有關示例報告下表中的附加資訊，請參閱說明。

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊廣告單位</span> </p> </td> 
   <td colname="col2"> <p>庫存物料的名稱。 例如，這可以是您的網站之一或您網站上的文章。 在上圖中，基本和單位是第9-18條。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 基本廣告單元</span> </p> </td> 
   <td colname="col2"> <p>庫存物料的名稱。 例如，這可以是您的網站之一或您網站上的文章。 在上圖中，基本廣告單位是第1條至第8條。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊廣告單位單位計數</span> </p> </td> 
   <td colname="col2"> <p>訪問廣告單元的用戶數9 - 18。 此資訊從Google廣告管理器日誌中提取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 基本廣告單位統一計數</span> </p> </td> 
   <td colname="col2"> <p>訪問廣告單元項1 - 8的用戶數。 此資訊從Google廣告管理器日誌中提取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊統一計數</span> </p> </td> 
   <td colname="col2"> <p>訪問過的用戶之間的重疊 <span class="wintitle"> 基本廣告單元</span> 和 <span class="wintitle"> 重疊廣告單位</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊百分比</span> </p> </td> 
   <td colname="col2"> <p>訪問過的用戶之間的重疊 <span class="wintitle"> 基本廣告單元</span> 和 <span class="wintitle"> 重疊廣告單位</span>。 這是 <span class="wintitle"> 重疊統一計數</span>，表示為 <span class="wintitle"> 基本廣告單元</span>。 </p> </td> 
  </tr> 
 </tbody> 
</table>
