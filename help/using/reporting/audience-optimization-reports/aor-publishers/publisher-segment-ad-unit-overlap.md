---
description: 「段到廣告單位重疊」報告顯示為熱圖，它突出顯示廣告單位和Audience Manager段之間的高和低重疊。
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: 區段至廣告單位重疊
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# 區段至廣告單位重疊{#segment-to-ad-unit-overlap}

「段到廣告單位重疊」報告顯示為熱圖，它突出顯示廣告單位和Audience Manager段之間的高和低重疊。

## 使用案例 {#use-cases}

使用 [!UICONTROL Segment to Ad Unit Overlap] 報告，您可以瞭解哪些訪問者訪問您的Web屬性。 報表顯示您的成員之間的重疊 [!DNL Audience Manager] 段和訪問Web屬性的訪問者數。 重疊率越高，表示網段的許多成員都會訪問您的Web屬性。

## 使用段添加單位重疊報表 {#using-the-report}

使用 **[!UICONTROL Top N Ad Units]** 和 **[!UICONTROL Top N Segments]** 控制項以選擇重疊所需的廣告單位和段數。 您可以為每個項目選擇最多100個項目。

使用 **日期範圍** 和 **日期至** 控制項來調整回顧範圍。 請注意，7天和30天回溯期間僅適用於星期日。

使用 **[!UICONTROL Segment Name]** 和 **[!UICONTROL Ad Unit]** 框，以過濾任何段和廣告單位。

>[!IMPORTANT]
>
>啟用時 [!UICONTROL Audience Optimization for Publishers]，必須包括描述性元資料 [!UICONTROL Ad Unit IDs]，如第3步中所述 [將GoogleAd Manager（以前叫DFP）資料檔案導入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)。 通過執行此操作，您可以確保報告將Web屬性的詳細資訊 [!UICONTROL Ad Unit] 而不是 [!UICONTROL Ad Unit ID]。

## 解釋結果 {#interpreting-results}

您 [!UICONTROL Segment to Ad Unit Overlap] 報告可能與下面的報告相似。 將滑鼠懸停在任何單元格上以獲取有關該特定重疊的詳細資訊。 有關示例報告下表中的附加資訊，請參閱說明。

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 項目 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 廣告單位 </span> </p> </td> 
   <td colname="col2"> <p>庫存物料的名稱。 例如，這可以是您的網站之一或您網站上的文章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 段即時單位計數</span> </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時看到的唯一訪問者數量以及在看到他們時符合該段條件的訪問者數量 <span class="keyword"> Audience Manager</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 廣告單位單位計數</span> </p> </td> 
   <td colname="col2"> <p>此特定廣告單元的訪問者數。 此資訊從Google廣告管理器日誌中提取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊統一計數</span> </p> </td> 
   <td colname="col2"> <p>接觸廣告單元項的段成員。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊百分比</span> </p> </td> 
   <td colname="col2"> <p>廣告單元和段總體之間的重疊。 這是 <span class="wintitle"> 重疊統一計數</span>，表示為 <span class="wintitle"> 分段即時統一</span>。 </p> </td> 
  </tr> 
 </tbody> 
</table>
