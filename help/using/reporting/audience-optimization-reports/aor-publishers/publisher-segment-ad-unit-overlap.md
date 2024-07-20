---
description: 「區段至廣告單位重疊」報表會以熱度圖顯示，並反白標示廣告單位與Audience Manager區段之間的高和低重疊。
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: 區段至廣告單位重疊
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 1%

---

# 區段至廣告單位重疊{#segment-to-ad-unit-overlap}

「區段至廣告單位重疊」報表會以熱度圖顯示，並反白標示廣告單位與Audience Manager區段之間的高和低重疊。

## 使用案例 {#use-cases}

透過[!UICONTROL Segment to Ad Unit Overlap]報表，您可以瞭解哪些對象造訪您的Web屬性。 此報表顯示[!DNL Audience Manager]區段的成員與您Web屬性的訪客數之間的重疊。 重疊程度越高，表示區段的許多成員都會造訪您的Web屬性。

## 使用區段來廣告單位重疊報表 {#using-the-report}

使用&#x200B;**[!UICONTROL Top N Ad Units]**&#x200B;和&#x200B;**[!UICONTROL Top N Segments]**&#x200B;控制項來選取重疊所需的廣告單位數和區段數。 每個最多可選取100個專案。

使用&#x200B;**日期範圍**&#x200B;和&#x200B;**日期到**&#x200B;控制項來調整您的回顧範圍。 請注意，7天和30天回顧期間僅適用於星期日日期。

使用&#x200B;**[!UICONTROL Segment Name]**&#x200B;和&#x200B;**[!UICONTROL Ad Unit]**&#x200B;方塊來篩選任何區段和廣告單位。

>[!IMPORTANT]
>
>啟用[!UICONTROL Audience Optimization for Publishers]時，您必須包含[!UICONTROL Ad Unit IDs]的描述性中繼資料，如[將Google Ad Manager （先前稱為DFP）資料檔案匯入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步驟3中所述。 透過這樣做，您可以確保報告將Web屬性詳細資料顯示為[!UICONTROL Ad Unit]，而不是[!UICONTROL Ad Unit ID]。

## 解譯結果 {#interpreting-results}

您的[!UICONTROL Segment to Ad Unit Overlap]報告可能類似於下面的報告。 將滑鼠指標暫留在任何儲存格上，即可取得特定重疊的詳細資訊。 如需範例報表下表中其他資訊的說明，請參閱。

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
   <td colname="col1"> <p><span class="wintitle">廣告單位</span> </p> </td> 
   <td colname="col2"> <p>庫存專案的名稱。 例如，這可以是您的其中一個網站或網站上的文章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">區段即時不重複計數</span> </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時檢視的不重複訪客數量，以及在<span class="keyword">Audience Manager</span>看到符合區段資格的不重複訪客數量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">廣告單位不重複計數</span> </p> </td> 
   <td colname="col2"> <p>此特定廣告單位的訪客數。 此資訊會從Google廣告管理員記錄檔中擷取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">個重疊不重複計數</span> </p> </td> 
   <td colname="col2"> <p>展示至廣告單位專案的區段成員。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">重疊百分比</span> </p> </td> 
   <td colname="col2"> <p>廣告單位和區段母體之間的重疊。 這是<span class="wintitle">個重疊不重複計數</span>，以<span class="wintitle">個區段即時不重複計數</span>的百分比表示。 </p> </td> 
  </tr> 
 </tbody> 
</table>
