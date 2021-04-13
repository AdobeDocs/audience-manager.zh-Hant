---
description: 「廣告單位重疊」報表會以熱圖顯示，反白顯示廣告單位之間的高與低重疊。
seo-description: 「廣告單位重疊」報表會以熱圖顯示，反白顯示廣告單位之間的高與低重疊。
seo-title: 廣告單位重疊
solution: Audience Manager
title: 廣告單位重疊
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: 受眾最佳化報表
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 3%

---

# 廣告單位重疊{#ad-unit-overlap}

**[!UICONTROL Ad Unit Overlap]**&#x200B;報表會以熱圖顯示，反白標示廣告單位之間的高與低重疊。

## 使用案例 {#use-cases}

透過&#x200B;**[!UICONTROL Ad Unit Overlap]**&#x200B;報表，您可以深入瞭解您的讀者在Web屬性中的重疊位置。 報表會考慮您的100個排名最前的相關屬性，並顯示它們之間的重疊。

## 使用廣告單位重疊報表{#using-the-report}

使用&#x200B;**[!UICONTROL Top N Base Ad Units]**&#x200B;和&#x200B;**[!UICONTROL Top N Overlapping Ad Units]**&#x200B;控制項，為重疊選擇所需的廣告單位數。 您最多可以為每個項目選取100個項目。

使用&#x200B;**日範圍**&#x200B;和&#x200B;**日期至**&#x200B;控制項來調整回顧範圍。 請注意，7天和30天回顧期間僅適用於星期日。

使用&#x200B;**[!UICONTROL Base Ad Unit]**&#x200B;和&#x200B;**[!UICONTROL Overlap Ad Unit]**&#x200B;控制項，選取您要在重疊報表中顯示的廣告單位。

>[!IMPORTANT]
>
>啟用[!UICONTROL Audience Optimization for Publishers]時，您必須包含[!UICONTROL Ad Unit IDs]的說明性中繼資料，如[將Google廣告管理員（舊稱DFP）資料檔案匯入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步驟3所述。 執行此動作後，您可確保報表會將Web屬性詳細資訊設為[!UICONTROL Ad Unit]，而非[!UICONTROL Ad Unit ID]。

## 解讀結果{#interpreting-results}

您的[!UICONTROL Ad Unit Overlap]報表看起來可能類似於下方報表。 將滑鼠指標暫留在任何儲存格上，以取得有關該特定重疊的詳細資訊。 請參閱範例報表下表格中的其他資訊說明。

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
   <td colname="col2"> <p>庫存項目的名稱。 例如，這可以是您的其中一個網站或網站上的文章。 在上圖中，基本廣告單位為第9-18條。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 基本廣告單元</span> </p> </td> 
   <td colname="col2"> <p>庫存項目的名稱。 例如，這可以是您的其中一個網站或網站上的文章。 在上圖中，基本廣告單位為文章1 - 8。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊廣告單位唯一客戶計數</span> </p> </td> 
   <td colname="col2"> <p>已瀏覽廣告單位項目的使用者人數9 - 18。 此資訊會從Google廣告管理員記錄檔中擷取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 基本廣告單位唯一客戶計數</span> </p> </td> 
   <td colname="col2"> <p>已瀏覽廣告單位項目1 - 8的使用者人數。 此資訊會從Google廣告管理員記錄檔中擷取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊唯一客戶計數</span> </p> </td> 
   <td colname="col2"> <p>已瀏覽<span class="wintitle">基本廣告單元</span>和<span class="wintitle">重疊廣告單元</span>的用戶之間的重疊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊百分比</span> </p> </td> 
   <td colname="col2"> <p>已瀏覽<span class="wintitle">基本廣告單元</span>和<span class="wintitle">重疊廣告單元</span>的用戶之間的重疊。 這是<span class="wintitle">重疊唯一值計數</span>，表示為<span class="wintitle">基本廣告單位</span>的百分比。 </p> </td> 
  </tr> 
 </tbody> 
</table>
