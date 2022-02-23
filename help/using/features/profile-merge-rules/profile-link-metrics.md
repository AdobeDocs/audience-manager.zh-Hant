---
description: 配置檔案連結度量提供有關向站點進行身份驗證的人員和設備的資料。 在建立合併規則時，或在「配置檔案合併規則」面板中按一下現有規則時，「配置檔案連結」中的資料和圖形會動態更新。 這些度量可以包括來自Adobe Experience Cloud設備合作或其他第三方設備圖形源的設備圖形。
seo-description: Profile Link metrics provide data about people and devices that authenticate to your site. The data and graphs in Profile Link update dynamically as you create a merge rules or when you click an existing rule from the Profile Merge Rules dashboard. These metrics can include device graph from the Adobe Experience Cloud Device Co-op or other third-party device graph sources.
seo-title: Report Metrics for Profile Merge Rules
solution: Audience Manager
title: 設定檔合併規則的報表量度
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: Profile Merge
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 2%

---

# 設定檔合併規則的報表量度 {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] 度量提供有關向站點進行身份驗證的人員和設備的資料。 中的資料和圖形 [!UICONTROL Profile Merge Rule Reports] 在建立合併規則時或在按一下現有規則時動態更新 [!UICONTROL Profile Merge Rules] 控制項欄。 這些度量可以包括來自 [!DNL Adobe Experience Cloud Device Co-op] 或其他第三方設備圖形源。

## 合併規則度量 {#merge-rule-metrics}

當合併規則使用來自 [Adobe Experience Cloud設備合作](https://experienceleague.adobe.com/docs/device-co-op/using/about/overview.html) 或其他第三方設備圖形，您可以訪問 [!DNL Audience Manager]。 這允許您將已驗證的第一方資料與 [!UICONTROL Experience Cloud Device Co-op] 或另一個第三方設備圖。 有關由 [!UICONTROL Device Co-op]，請參閱 [設備圖形：內部流程和輸出](https://experienceleague.adobe.com/docs/device-co-op/using/device-graph/device-graph-overview.html)。 此資料每天更新。

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 已驗證的活動</span></b> </p> </td> 
   <td colname="col2"> <p>顯示： </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> 活動人員</span>:過去60天內已驗證到您的站點的人數。 </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> 交叉設備</span>:總數 <a href="merge-rules-start.md#create-data-source"> 跨設備ID</a> 儲存在 <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html"> 資料源</a> 的 <a href="merge-rule-definitions.md"> 已驗證的配置檔案</a> 資料源存在的生存期。 </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> 活動人員百分比</span>:顯示 <span class="wintitle"> 活動人員</span> %。 </li> 
    </ul> <p> <span class="wintitle"> 已驗證的活動</span> 允許您按活動、卷和百分比比較資料源。 它可以幫助您找到一個資料源，該資料源擁有大量人員和高比例的活躍用戶。 或者，在比較資料源與活動用戶的高比例與總受眾規模時，您可能會發現其價值。 例如，有時，總生存期數和活動率較低的資料源比壽命結果較高和活動率較低的資料源更有價值。 </p> <p> <p>注：的 <span class="wintitle"> 已驗證的活動</span> 度量包含 <span class="wintitle"> 配置檔案連結</span> 僅資料。 此報告不包括 <span class="wintitle"> 設備圖</span> 資料。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 每人平均設備數</span></b> </p> </td> 
   <td colname="col2"> <p> 顯示訪問者使用的設備的平均數量，這些訪問者已通過對所選資料源的站點身份驗證。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 設備總數</span></b> </p> </td> 
   <td colname="col2"> <p>顯示已用於驗證所選資料源的站點的設備總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 總人數</span></b> </p> </td> 
   <td colname="col2"> <p>顯示為所選資料源確定標識的人員總數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 設備圖形度量 {#device-graph-metrics}

的 [!UICONTROL Merge Rules] 報告還顯示訪問您站點的選定資料源和設備圖形的人員和設備總數。 這些度量根據預設時間間隔（回溯期間）返回資料，這些時間間隔因建立規則時選擇的設備選項而異。 下表列出了每個設備圖形選項的這些報告間隔。

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設備圖形選項 </th> 
   <th colname="col2" class="entry"> 報告回查間隔 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 設定檔連結</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">人員總數：60天 </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">設備總數：120天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 合作設備圖</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">人員總數：180天 </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">設備總數：180天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">人員總數：180天 </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">設備總數：180天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 塔帕德</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">人員總數：60天 </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">設備總數60天 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例報告 {#sample-reports}

### 標準配置檔案連結報表

標準 [!UICONTROL Profile Link] 報告如下所示。 使用多個資料源（最多3個，最大值）的合併規則在每個資料源的單獨頁籤中顯示圖形。 此合併規則不包括 [!UICONTROL Device Co-op] 資料。

![](assets/profile-link-metrics.png)

### 帶設備圖資料的配置檔案連結報告

A [!UICONTROL Profile Link Device Graph] 包括設備圖形資料的報告 [!UICONTROL Adobe Experience Cloud Device Co-op] 或第三方設備圖顯示 [!UICONTROL Profile Link] 並行條形圖的設備圖形資料。 將這些圖形彼此相鄰，可評估使用 [!UICONTROL Experience Cloud Device Co-op] 與 [!UICONTROL Profile Link] 自己來。 使用多個資料源（最多3個，最大值）的合併規則在每個資料源的單獨頁籤中顯示圖形。 作為提醒， [!UICONTROL Authenticated Activity] 圖形和度量不返回資料 [!DNL Adobe] 設備圖或其他可訪問的第三方設備圖 [!DNL Audience Manager]。

![](assets/profile-link-graph.png)

## 配置檔案連結趨勢圖 {#profile-link-trend}

除了其他資料可視化外， [!UICONTROL Profile Link] 報告包括線形圖。 線形圖旨在顯示配置檔案規則隨時間的變化趨勢。 當按一下 [!UICONTROL Profile Merge Rules] 登錄頁(L) **[!UICONTROL Audience Data > Profile Merge Rules]**)。 如果您是 [!UICONTROL Device Co-op] 或其他第三方設備圖形，您可以訪問 [!DNL Audience Manager]。 按一下趨勢線查看基礎資料。

>[!MORELIKETHIS]
>
>* [配置檔案合併規則常見問題](../../faq/faq-profile-merge.md)

