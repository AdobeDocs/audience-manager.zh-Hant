---
description: 「區段至廣告單位重疊」報表會顯示為熱圖，反白標示廣告單位與Audience Manager區段之間的高低重疊。
seo-description: 「區段至廣告單位重疊」報表會顯示為熱圖，反白標示廣告單位與Audience Manager區段之間的高低重疊。
seo-title: 區段至廣告單位重疊
solution: Audience Manager
title: 區段至廣告單位重疊
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: 受眾最佳化報表
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 5%

---

# 區段至廣告單位重疊{#segment-to-ad-unit-overlap}

「區段至廣告單位重疊」報表會顯示為熱圖，反白標示廣告單位與Audience Manager區段之間的高低重疊。

## 使用案例 {#use-cases}

透過[!UICONTROL Segment to Ad Unit Overlap]報表，您可以瞭解哪些對象瀏覽您的Web屬性。 報表會顯示[!DNL Audience Manager]區段成員與您網頁屬性訪客人數的重疊。 較高的重疊率表示區段的許多成員會造訪您的Web屬性。

## 使用區段來廣告單位重疊報表{#using-the-report}

使用&#x200B;**[!UICONTROL Top N Ad Units]**&#x200B;和&#x200B;**[!UICONTROL Top N Segments]**&#x200B;控制項，為重疊選取所需的廣告單位和區段數。 您最多可以為每個項目選取100個項目。

使用&#x200B;**日範圍**&#x200B;和&#x200B;**日期至**&#x200B;控制項來調整回顧範圍。 請注意，7天和30天回顧期間僅適用於星期日。

使用&#x200B;**[!UICONTROL Segment Name]**&#x200B;和&#x200B;**[!UICONTROL Ad Unit]**&#x200B;方塊來篩選任何區段和廣告單位。

>[!IMPORTANT]
>
>啟用[!UICONTROL Audience Optimization for Publishers]時，您必須包含[!UICONTROL Ad Unit IDs]的說明性中繼資料，如[將Google廣告管理員（舊稱DFP）資料檔案匯入Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)的步驟3所述。 執行此動作後，您可確保報表會將Web屬性詳細資訊設為[!UICONTROL Ad Unit]，而非[!UICONTROL Ad Unit ID]。

## 解讀結果{#interpreting-results}

您的[!UICONTROL Segment to Ad Unit Overlap]報表看起來可能類似於下方報表。 將滑鼠指標暫留在任何儲存格上，以取得有關該特定重疊的詳細資訊。 請參閱範例報表下表格中的其他資訊說明。

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
   <td colname="col1"> <p><span class="wintitle"> 廣告單位  </span> </p> </td> 
   <td colname="col2"> <p>庫存項目的名稱。 例如，這可以是您的其中一個網站或網站上的文章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 分段即時獨特值計數</span> </p> </td> 
   <td colname="col2"> <p>在指定時間範圍內即時檢視的獨特訪客數量，以及<span class="keyword">Audience Manager</span>看到區段時符合資格的訪客數量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 廣告單位獨特值計數</span> </p> </td> 
   <td colname="col2"> <p>此特定廣告單位的訪客數。 此資訊會從Google廣告管理員記錄檔中擷取。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊唯一客戶計數</span> </p> </td> 
   <td colname="col2"> <p>您區段中接觸廣告單位項目的成員。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 重疊百分比</span> </p> </td> 
   <td colname="col2"> <p>廣告單位和群體人口之間的重疊。 這是<span class="wintitle">重疊獨特值計數</span>，表示為<span class="wintitle">分段即時獨特值</span>的百分比。 </p> </td> 
  </tr> 
 </tbody> 
</table>
