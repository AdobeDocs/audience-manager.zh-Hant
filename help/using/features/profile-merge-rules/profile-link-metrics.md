---
description: 描述檔連結量度提供有關在您網站上驗證的人員和裝置的資料。 當您建立合併規則或從「描述檔合併規則」控制面板按一下現有規則時，「描述檔連結」中的資料和圖形會動態更新。 這些量度可包含來自Adobe Experience Cloud Device Co-op或其他第三方裝置圖形來源的裝置圖形。
seo-description: 描述檔連結量度提供有關在您網站上驗證的人員和裝置的資料。 當您建立合併規則或從「描述檔合併規則」控制面板按一下現有規則時，「描述檔連結」中的資料和圖形會動態更新。 這些量度可包含來自Adobe Experience Cloud Device Co-op或其他第三方裝置圖形來源的裝置圖形。
seo-title: 描述檔合併規則的報表量度
solution: Audience Manager
title: 描述檔合併規則的報表量度
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


#  描述檔合併規則的報表量度 {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Link] 量度會提供您網站驗證的人員和裝置相關資料。 當您建立合併規則 [!UICONTROL Profile Link] 或按一下控制面板中的現有規則時，資料和圖形會動態 [!UICONTROL Profile Merge Rules] 更新。 這些量度可包含來自或其他協力 [!DNL Adobe Experience Cloud Device Co-op] 廠商裝置圖形來源的裝置圖形。

## 合併規則量度 {#merge-rule-metrics}

當您的合併規則使用 [Adobe Experience Cloud Device Co-op或您可在中存取的其他協力廠商裝置圖表資料時，報表會以並排長條圖形傳回資料](https://marketing.adobe.com/resources/help/en_US/mcdc/)[!DNL Audience Manager]。 這可讓您比較已驗證的第一方資料與由或另一第三方裝置圖表提供 [!UICONTROL Experience Cloud Device Co-op] 的跨裝置資料。 如需由傳回之資料的詳細資 [!UICONTROL Device Co-op]訊，請參 [閱裝置圖表：內部流程和輸出](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html)。 此資料會每日更新。

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 已驗證活動</span></b> </p> </td> 
   <td colname="col2"> <p>顯示： </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> 活動人員</span>:過去60天內已驗證您網站的人數。 </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> 跨裝置</span>:在所選已驗 <a href="../../features/profile-merge-rules/merge-rules-start.md#create-data-source"> 證的設定檔的存留期間，在「資料來源」中儲存的「跨裝置ID」總數</a><a href="../../features/manage-datasources.md#create-data-source"></a><a href="../../features/profile-merge-rules/merge-rule-definitions.md"></a> ，即「已驗證的設定檔」的「資料來源」中所儲存的「跨裝置ID」總數。 </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> %有效人員</span>:將「 <span class="wintitle"> 作用中人員</span> 」顯示為%。 </li> 
    </ul> <p> <span class="wintitle"> 「已驗證活動</span> 」可讓您依活動、卷和百分比來比較資料來源。 它可協助您尋找擁有大量人員和高比例使用者的資料來源。 或者，您可能會發現比較資料來源與高比例的使用中使用者與總讀者人數的價值。 例如，有時總存留期數較少、活動較高的資料來源比活動次數較高、存留期結果較高的資料來源更有價值。 </p> <p> <p>注意：「已驗 <span class="wintitle"> 證活動</span> 」量度僅包含 <span class="wintitle"> 「描述檔連結</span> 」資料。 此報告不包含「裝 <span class="wintitle"> 置圖表</span> 」資料。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 每人平均裝置數</span></b> </p> </td> 
   <td colname="col2"> <p> 顯示已透過您網站驗證所選資料來源之訪客所使用之平均裝置數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 裝置總數</span></b> </p> </td> 
   <td colname="col2"> <p>顯示訪客在您的網站上驗證所選資料來源時所使用的裝置總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> 總人數</span></b> </p> </td> 
   <td colname="col2"> <p>顯示已為選定資料源確定性地標識的總人數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 裝置圖表度量 {#device-graph-metrics}

報 [!UICONTROL Merge Rules] 表也會顯示所選資料來源和裝置圖表中瀏覽您網站的總人數和裝置。 這些量度會根據預先設定的時間間隔（回顧時段）傳回資料，這些時間間隔視您建立規則時選取的裝置選項而異。 下表列出每個裝置圖形選項的這些報告間隔。

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置圖表選項 </th> 
   <th colname="col2" class="entry"> 報告回顧間隔 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 個人資料連結</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">總人數：60天 </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">裝置總數：120天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Co-op裝置圖表</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">總人數：180天 </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">裝置總數：180天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">總人數：180天 </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">裝置總數：180天 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">總人數：60天 </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">裝置總數60天 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例報表 {#sample-reports}

### 標準描述檔連結報表

標準報 [!UICONTROL Profile Link] 表看起來類似下列範例。 使用多個資料來源的合併規則（最多3個，最多3個）會在每個資料來源的個別標籤中顯示圖形。 此合併規則不包含 [!UICONTROL Device Co-op] 資料。

![](assets/coop-metrics1.png)

### 具備裝置圖表資料的描述檔連結報表

包 [!UICONTROL Profile Link] 含來自或第三方裝置圖 [!UICONTROL Adobe Experience Cloud Device Co-op] 形之裝置圖形資料的報表，以並排條形圖 [!UICONTROL Profile Link] 形顯示及裝置圖形資料。 將這些圖形彼此相鄰，可讓您自行評估使用 [!UICONTROL Experience Cloud Device Co-op] 相較 [!UICONTROL Profile Link] 的優點。 使用多個資料來源的合併規則（最多3個，最多3個）會在每個資料來源的個別標籤中顯示圖形。 提醒您，圖 [!UICONTROL Authenticated Activity] 形和量度不會傳回裝置圖表或 [!DNL Adobe] 您在中可存取的其他協力廠商裝置圖表的資料 [!DNL Audience Manager]。

![](assets/coop-metrics2.png)

## 描述檔連結趨勢圖 {#profile-link-trend}

除了其他資料視覺化外，報 [!UICONTROL Profile Link] 表還包含折線圖。 折線圖旨在顯示描述檔規則隨時間的趨勢。 當您從著陸頁面()按一下規則時，趨勢圖(和其 [!UICONTROL Profile Merge Rules] 他報表) **[!UICONTROL Audience Data > Profile Merge Rules]**&#x200B;可用。 如果您是您在中可存取的其他協力廠商 [!UICONTROL Device Co-op] 裝置圖形的成員，這些圖形包括裝置圖形資料 [!DNL Audience Manager]。 按一下趨勢線以檢視基礎資料。

![](assets/authenticated_trends.png)

>[!MORE_LIKE_THIS]
>
>* [描述檔合併規則常見問答集](../../faq/faq-profile-merge.md)

