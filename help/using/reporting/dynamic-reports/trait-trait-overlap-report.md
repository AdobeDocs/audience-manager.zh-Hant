---
description: 傳回您所有第一方和第三方特徵中共用的不重複使用者人數。
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: 特徵對特徵重疊報表
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
source-git-commit: 6cc1351c3a84d4d2219f33ef6175f182b9641377
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# 特徵對特徵重疊報表{#trait-to-trait-overlap-report}

傳回您所有第一方和第三方特徵中共用的不重複使用者人數。

>[!NOTE]
>
>Audience Manager中的重疊報表遵循RBAC原則。 您只能根據您所屬的[RBAC使用者群組](/help/using/features/administration/administration-overview.md)，從您有權存取的資料來源檢視特徵。

<!-- 

c_overlap_reports.xml

 -->

## 概述

[!UICONTROL Trait-to-Trait Overlap]報表會傳回您所有特徵與第三方特徵之間共用的不重複使用者百分比。 作為最佳化工具，此報表可協助您：

* 根據您的需求，建立高重疊或低重疊的區段。 重疊程度高的特徵可為您提供目標受眾，但獨特訪客較少。 重疊程度低的特徵對於觸及較大的不重複訪客集很有幫助。
* 驗證第三方特徵資料：類似的第一方和第三方特徵之間高度重疊，表示資料合作夥伴的特徵正確且值得信賴。 相反地，低重疊度可能表示第三方特徵實際上可能不包含與您自己的類似第一方特徵相同的資訊。
* 找出特徵之間未預期的重疊，然後使用該資訊來建立創新區段。

## 範例報告

下圖提供[!UICONTROL Trait-to-Trait Overlap]報表中元素的高階概觀。

>[!NOTE]
>
>[!UICONTROL Trait-to-Trait Overlap]報表將相同特徵與其本身進行比較時會傳回空白欄位。

>[!NOTE]
>
>在特徵對特徵重疊報表中，資料夾特徵不可用於比較。 透過使用特定資料夾特徵建立區段，您可以透過[區段對特徵重疊報表](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md)執行分析。

![](assets/trait-to-trait-overlap.png)

## 深入研究個別資料點

選取個別點，以在快顯視窗中檢視資料詳細資訊。 您的點按動作會自動更新報表中顯示的資料。

## 已定義特徵對特徵重疊資料快顯欄位 {#field-definitions}

說明當您按一下個別資料點時，快顯視窗中顯示的量度。

<!-- 

r_t2t_data_pop.xml

 -->

[!UICONTROL Trait-to-Trait Overlap]報表的快顯視窗包含下列量度。 請注意，表格中的不重複量度代表您的&#x200B;*即時使用者*。

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">重疊%</span></b> </td> 
   <td colname="col2"> 顯示比較特徵之間的不重複重疊百分比（重疊不重複/特徵不重複）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">資料Source型別</span></b> </td> 
   <td colname="col2">定義特徵所屬的資料來源型別。 可以是： 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">第一方（您自己的特徵）。 </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">第三方（來自外部資料合作夥伴/廠商）。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">重疊的特徵ID</span></b> </td> 
   <td colname="col2"> 重疊特徵的唯一數值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">重疊的特徵名稱</span></b> </td> 
   <td colname="col2"> 重疊特徵的名稱。 </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle">特徵識別碼2</span></b> </td> 
   <td colname="col2"> 基礎資料來源中特徵的不重複數值ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">特徵名稱2</span></b> </td> 
   <td colname="col2"> 基礎資料來源中的特徵名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">個重疊不重複專案</span></b> </td> 
   <td colname="col2"> <p>若要取得重疊%，Audience Manager會使用以下公式：</p> <p>重疊唯一性/（基本唯一性+重疊唯一性 — 重疊唯一性）</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">個重疊特徵不重複專案</span></b> </td> 
   <td colname="col2"> 來自重疊特徵的不重複訪客數量。 </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle">基本特徵不重複</span></b> </td> 
   <td colname="col2"> 來自基本特徵的不重複訪客數量。 </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [使用資料滑桿篩選報表結果](../../reporting/dynamic-reports/data-sliders.md)
>* [動態報告中使用的形狀、顏色和大小](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [報告圖示和工具說明](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [重疊報表：更新排程和最小區段大小](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [所選Audience Manager報表中的資料取樣和錯誤率……](../../reporting/report-sampling.md)
>* [重疊報表的 CSV 檔案](../../reporting/dynamic-reports/overlap-csv-files.md)
