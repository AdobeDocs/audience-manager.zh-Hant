---
description: 用於未知使用者使用外部裝置圖表的預測、重新定位和個人化的建議和使用案例。外部裝置圖表定義為與Audience Manager分開的裝置圖表。這包括Adobe Experience Cloud Device Co-op以及Adobe與第三方決定性或可能性裝置圖形公司的其他整合。
seo-description: 用於未知使用者使用外部裝置圖表的預測、重新定位和個人化的建議和使用案例。外部裝置圖表定義為與Audience Manager分開的裝置圖表。這包括Adobe Experience Cloud Device Co-op以及Adobe與第三方決定性或可能性裝置圖形公司的其他整合。
seo-title: 外接式裝置圖表使用案例
solution: Audience Manager
title: 外接式裝置圖表使用案例
uuid: f4bc822d-39d2-4680-90ed-7ee6ead6db6f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 外接式裝置圖表使用案例 {#external-device-graph-use-cases}

用於未知使用者使用外部裝置圖表的預測、重新定位和個人化的建議和使用案例。外部裝置圖表定義為與Audience Manager分開的裝置圖表。This includes the [!DNL Adobe Experience Cloud Device Co-op] and other integrations Adobe has with third-party deterministic or probabilistic device graph companies.

## 建議 {#recommendations}

Consider the [!DNL Experience Cloud Device Co-op] and third-party device graph options for campaigns that:

* 其數位屬性的驗證層級低。Use the [Profile Link device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) if you have a large number of authenticated users.
* 鎖定大型受眾。[!DNL Experience Cloud Device Co-op] 和第三方裝置圖表包含已驗證和未驗證的資料。
* 在個人和家庭層級細分已驗證及/或未驗證的訪客。

![](assets/merge-rule-triangle1.png)

## Prospecting/Branding Use Case {#prospecting-branding-use-cases}

品牌促銷活動旨在觸及盡可能多的人。它對區段資格的限制很少。但是，這些促銷活動會不斷鎖定看見您的內容多次且不轉換的人們，因而浪費預算和印象。[!UICONTROL Profile Merge] 使用 [!DNL Device Co-op] 或第三方選項的規則可協助您建立有效的品牌推廣促銷活動。例如，您可以在多部裝置上檢視您設定的頻率片段後，將這些未知使用者加入「非市場」區段。

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>條件</b> </p> </td> 
   <td colname="col2">此使用案例假設下列條件： <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">您想要為特定廣告促銷活動提供最多10印象給匿名使用者。 </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">使用者擁有多個裝置，且可能未驗證您的網站。 </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">匿名使用者會看見廣告總共10次，並在目前裝置上以未驗證狀態瀏覽，最多可使用外部裝置圖表連結的裝置。 </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">將從目前裝置收集的匿名、未驗證的活動與外部裝置圖表連結的個裝置合併(每個裝置的廣告印象)。 </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">根據外部裝置圖表和目前裝置連結的所有種裝置上的匿名活動組合，評估未驗證的使用者區段資格。 </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">將區段傳送至任何即時目的地，作為目前裝置上的抑制區段，以及外部裝置圖形連結的所有種裝置。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#retargeting-use-case}

這些策略旨在讓未驗證或未知的使用者返回您的網站，或在網站上進行個人化瀏覽體驗。

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>條件</b> </p> </td> 
   <td colname="col2">此使用案例假設下列條件： <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">您想要根據匿名使用者在未驗證狀態下的活動，提供個人化臨場感和/或離站體驗給匿名使用者。 </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">使用者擁有多個裝置，且可能未驗證您的網站。 </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">使用者在您的網站上檢視多個頁面，並在目前裝置上以未驗證狀態瀏覽，最多可使用外部裝置圖表連結的裝置。 </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">將從目前裝置和外部裝置圖形連結的三個裝置進行合併的匿名、未驗證活動(每個裝置的多個頁面檢視)合併。 </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">根據外部裝置圖表和目前裝置連結的所有種裝置上的匿名活動組合，評估未驗證的使用者區段資格。 </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">將區段傳送至任何即時目的地，以便在目前裝置和外部裝置圖形連結的所有種裝置上提供個人化和/或離線體驗。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## Profile Merge Rule Options for External Device Graph Use Cases {#profile-merge}

這些使用案例的合併規則選項看起來類似下方顯示的可用選項。[!UICONTROL Authenticated Profile] 選項會停用，因為這些設定只能在您選取 **[!UICONTROL Current Authenticated Profile]** 時使用 **[!UICONTROL Last Authenticated Profile]**。Your [!UICONTROL Device Options] will vary depending on the type of device graph setting that you want to use or that is available to you.

![](assets/merge-rules-external.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_贊_ this]
>
>* [描述檔連結裝置圖表使用案例](../../features/profile-merge-rules/profile-link-use-case.md)
>* [描述檔合併規則的一般使用案例](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [個人檔案合併規則常見問答集](../../faq/faq-profile-merge.md)

