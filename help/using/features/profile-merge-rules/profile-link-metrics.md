---
description: 設定檔連結量度提供對您的網站進行驗證之人員和裝置的相關資料。 當您建立合併規則，或從「個人資料合併規則」控制面板按一下現有規則時，「個人資料連結」中的資料和圖形會動態更新。 這些量度可以包含來自Adobe Experience Cloud Device Co-op或其他協力廠商裝置圖表來源的裝置圖表。
seo-description: 設定檔連結量度提供對您的網站進行驗證之人員和裝置的相關資料。 當您建立合併規則，或從「個人資料合併規則」控制面板按一下現有規則時，「個人資料連結」中的資料和圖形會動態更新。 這些量度可以包含來自Adobe Experience Cloud Device Co-op或其他協力廠商裝置圖表來源的裝置圖表。
seo-title: 設定檔合併規則的報表量度
solution: Audience Manager
title: 設定檔合併規則的報表量度
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: 個人資料合併
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 2%

---

# 設定檔合併規則的報表量度 {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] 量度提供對您的網站進行驗證的人員和裝置相關資料。當您建立合併規則，或從[!UICONTROL Profile Merge Rules]控制面板按一下現有規則時，[!UICONTROL Profile Merge Rule Reports]中的資料和圖形會動態更新。 這些量度可包含[!DNL Adobe Experience Cloud Device Co-op]或其他協力廠商裝置圖表來源的裝置圖表。

## 合併規則量度{#merge-rule-metrics}

當您的合併規則使用[Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html)或您在[!DNL Audience Manager]中可存取的其他協力廠商裝置圖表的資料時，報表會以並排長條圖傳回資料。 這可讓您比較已驗證的第一方資料與[!UICONTROL Experience Cloud Device Co-op]或其他協力廠商裝置圖表提供的跨裝置資料。 如需[!UICONTROL Device Co-op]傳回資料的相關資訊，請參閱[裝置圖表：內部進程和輸出](https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html)。 此資料會每天更新。

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
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> 活動人員</span>:過去60天內已驗證您網站的訪客人數。 </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> 跨裝置</span>:在資料來 <a href="merge-rules-start.md#create-data-source"> 源存</a> 在之存留期 <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html"> 內，所</a> 選已驗 <a href="merge-rule-definitions.md"> 證設定檔的資料來源中儲存的跨</a> 裝置ID總數。 </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> %活動人員</span>:顯 <span class="wintitle"> 示活</span> 動人數%。 </li> 
    </ul> <p> <span class="wintitle"> 已驗</span> 證的活動可讓您依活動、數量和百分比來比較資料來源。它可協助您尋找人數眾多、作用中使用者比例較高的資料來源。 或者，比較活躍使用者比較受眾總規模的高比例資料來源時，您可能會發現其價值。 例如，有時總存留期數量低、活動度高的資料來源，比存留期結果高、活動度低的資料來源更有價值。 </p> <p> <p>注意：<span class="wintitle">已驗證的活動</span>量度僅包含<span class="wintitle">設定檔連結</span>資料。 此報告不包含<span class="wintitle">裝置圖表</span>資料。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 每人平均裝置</span></b> </p> </td> 
   <td colname="col2"> <p> 顯示已驗證您網站之選定資料來源之訪客使用的平均裝置數量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 總裝置</span></b> </p> </td> 
   <td colname="col2"> <p>顯示使用者在所選資料來源中用於驗證您網站的裝置總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 總人數</span></b> </p> </td> 
   <td colname="col2"> <p>顯示為所選資料源決定性地識別的總人數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 裝置圖表量度{#device-graph-metrics}

[!UICONTROL Merge Rules]報表也會顯示所選資料來源和裝置圖表中瀏覽過您網站的使用者和裝置總數的資料。 這些量度會根據預先設定的時間間隔（回顧期間）傳回資料，這些時間間隔會依您在建立規則時選取的裝置選項而有所不同。 下表列出每個裝置圖表選項的這些報告間隔。

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置圖表選項 </th> 
   <th colname="col2" class="entry"> 報表回顧間隔 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 設定檔連結</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">總人數：60天 </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">總設備數：120天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Co-op裝置圖表</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">總人數：180天 </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">總設備數：180天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">總人數：180天 </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">總設備數：180天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 塔帕德</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">總人數：60天 </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">總裝置60天 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 報表範例{#sample-reports}

### 標準設定檔連結報表

標準[!UICONTROL Profile Link]報表如下列範例所示。 使用多個資料來源的合併規則（最多3個，最多3個）會在每個資料來源的個別索引標籤中顯示圖形。 此合併規則不包含[!UICONTROL Device Co-op]資料。

![](assets/profile-link-metrics.png)

### 使用裝置圖表資料的設定檔連結報表

[!UICONTROL Profile Link Device Graph]報表包含來自[!UICONTROL Adobe Experience Cloud Device Co-op]或協力廠商裝置圖表的裝置圖表資料，顯示[!UICONTROL Profile Link]和具有並排長條圖的裝置圖表資料。 將這些圖形彼此相鄰，可讓您評估使用[!UICONTROL Experience Cloud Device Co-op]本身與[!UICONTROL Profile Link]相比的優點。 使用多個資料來源的合併規則（最多3個，最多3個）會在每個資料來源的個別索引標籤中顯示圖形。 提醒您，[!UICONTROL Authenticated Activity]圖表和量度不會傳回[!DNL Adobe]裝置圖表或您可在[!DNL Audience Manager]中存取的其他協力廠商裝置圖表的資料。

![](assets/profile-link-graph.png)

## 設定檔連結趨勢圖{#profile-link-trend}

除了其他資料視覺效果外， [!UICONTROL Profile Link]報表還包含折線圖。 折線圖旨在顯示設定檔規則在一段時間內的趨勢。 當您從[!UICONTROL Profile Merge Rules]登陸頁面(**[!UICONTROL Audience Data > Profile Merge Rules]**)按一下規則時，可使用趨勢圖（和其他報表）。 如果您是[!UICONTROL Device Co-op]的成員，則這些圖形包括設備圖表資料，或者您可以在[!DNL Audience Manager]中訪問的其他第三方設備圖形。 按一下趨勢線以查看基礎資料。

>[!MORELIKETHIS]
>
>* [設定檔合併規則常見問題集](../../faq/faq-profile-merge.md)

