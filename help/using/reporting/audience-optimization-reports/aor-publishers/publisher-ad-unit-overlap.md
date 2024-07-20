---
description: 「廣告單位重疊」報表會以熱度圖顯示，以強調廣告單位之間的高和低重疊。
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: 廣告單位重疊
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# 廣告單位重疊{#ad-unit-overlap}

**[!UICONTROL Ad Unit Overlap]**&#x200B;報告會顯示為熱度圖，以強調廣告單位之間的高和低重疊。

## 使用案例 {#use-cases}

透過&#x200B;**[!UICONTROL Ad Unit Overlap]**&#x200B;報表，您可以深入瞭解對象在您的Web屬性中重疊的位置。 報表會考量您的100個熱門相關屬性，並顯示它們之間的重疊。

## 使用廣告單位重疊報表 {#using-the-report}

使用&#x200B;**[!UICONTROL Top N Base Ad Units]**&#x200B;和&#x200B;**[!UICONTROL Top N Overlapping Ad Units]**&#x200B;控制項來選取重疊所需的廣告單位數。 每個最多可選取100個專案。

使用&#x200B;**日期範圍**&#x200B;和&#x200B;**日期到**&#x200B;控制項來調整您的回顧範圍。 請注意，7天和30天回顧期間僅適用於星期日日期。

使用&#x200B;**[!UICONTROL Base Ad Unit]**&#x200B;與&#x200B;**[!UICONTROL Overlap Ad Unit]**&#x200B;控制項來選取您要在重疊報表中顯示的廣告單位。

>[!IMPORTANT]
>
>啟用[!UICONTROL Audience Optimization for Publishers]時，您必須包含[!UICONTROL Ad Unit IDs]的描述性中繼資料，如[將Google Ad Manager （先前稱為DFP）資料檔案匯入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步驟3中所述。 透過這樣做，您可以確保報告將Web屬性詳細資料顯示為[!UICONTROL Ad Unit]，而不是[!UICONTROL Ad Unit ID]。

## 解譯結果 {#interpreting-results}

您的[!UICONTROL Ad Unit Overlap]報告可能類似於下面的報告。 將滑鼠指標暫留在任何儲存格上，即可取得特定重疊的詳細資訊。 如需範例報表下表中其他資訊的說明，請參閱。

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
   <td colname="col1"> <p><span class="wintitle">重疊廣告單位</span> </p> </td> 
   <td colname="col2"> <p>庫存專案的名稱。 例如，這可以是您的其中一個網站或網站上的文章。 在上圖中，基本廣告單位為第9至18條。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">基本廣告單位</span> </p> </td> 
   <td colname="col2"> <p>庫存專案的名稱。 例如，這可以是您的其中一個網站或網站上的文章。 在上圖中，基本廣告單位為文章1 - 8。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">個重疊廣告單位不重複計數</span> </p> </td> 
   <td colname="col2"> <p>造訪廣告單位專案9 - 18的使用者人數。 此資訊會從Google廣告管理員記錄檔中擷取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">個基本廣告單位不重複計數</span> </p> </td> 
   <td colname="col2"> <p>造訪廣告單位專案1至8的使用者人數。 此資訊會從Google廣告管理員記錄檔中擷取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">個重疊不重複計數</span> </p> </td> 
   <td colname="col2"> <p>造訪過<span class="wintitle">基本廣告單位</span>與<span class="wintitle">重疊廣告單位</span>的使用者之間的重疊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">重疊百分比</span> </p> </td> 
   <td colname="col2"> <p>造訪過<span class="wintitle">基本廣告單位</span>與<span class="wintitle">重疊廣告單位</span>的使用者之間的重疊。 這是<span class="wintitle">個重疊不重複計數</span>，以<span class="wintitle">基本廣告單位</span>的百分比表示。 </p> </td> 
  </tr> 
 </tbody> 
</table>
