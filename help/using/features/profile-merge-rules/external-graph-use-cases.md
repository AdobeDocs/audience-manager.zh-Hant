---
description: 使用外部裝置圖表，為未知使用者提供潛在客戶、重新定位目標及個人化的建議和使用案例。 外部裝置圖表定義為與Audience manager分開的裝置圖表。 這包括Adobe Experience Cloud Device Co-op以及Adobe與協力廠商確定性或概率性裝置圖形公司的其他整合。
seo-description: 使用外部裝置圖表，為未知使用者提供潛在客戶、重新定位目標及個人化的建議和使用案例。 外部裝置圖表定義為與Audience manager分開的裝置圖表。 這包括Adobe Experience Cloud Device Co-op以及Adobe與協力廠商確定性或概率性裝置圖形公司的其他整合。
seo-title: 外接式裝置圖表使用案例
solution: Audience Manager
title: 外接式裝置圖表使用案例
uuid: f4bc822d-39d2-4680-90ed-7ee2ead6db6f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 外接式裝置圖表使用案例 {#external-device-graph-use-cases}

使用外部裝置圖表，為未知使用者提供潛在客戶、重新定位目標及個人化的建議和使用案例。 外部裝置圖表定義為與Audience manager分開的裝置圖表。 這包括Adobe [!DNL Adobe Experience Cloud Device Co-op] 與協力廠商確定性或概率性裝置圖形公司的整合。

## 建議 {#recommendations}

請考慮下 [!DNL Experience Cloud Device Co-op] 列促銷活動的第三方裝置圖形選項：

* 其數位屬性的驗證級別較低。 如果您有 [大量已驗證的使用者](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) ，請使用「描述檔連結裝置圖形」選項。
* 鎖定大型受眾。 該 [!DNL Experience Cloud Device Co-op] 和協力廠商裝置圖表包含已驗證和未驗證的資料。
* 在個人和家庭層級劃分已驗證和／或未驗證的訪客。

![](assets/merge-rule-triangle1.png)

## 潛在客戶／品牌使用案例 {#prospecting-branding-use-cases}

品牌宣傳旨在觸及到盡可能多的人。 它對區段資格設定的限制很少。 但是，這些促銷活動會持續鎖定多次檢視您內容且未轉換的訪客，以浪費預算和印象。 使用 [!UICONTROL Profile Merge] 或協力廠商選 [!DNL Device Co-op] 項的規則可協助您建立有效的品牌宣傳。 例如，您可以在設定頻率上限的多個裝置上看到這些未知使用者後，將其新增至「非市場內」區段。

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
      <li id="li_81AE304924724146A24FAB5B6533AD8E">您想要針對特定廣告促銷活動，向匿名使用者提供最多10個曝光。 </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">使用者擁有多種裝置，且可能或未經過您網站的驗證。 </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">匿名使用者在其目前裝置上以未驗證狀態瀏覽廣告時，可共看到廣告10次，而透過外部裝置圖表連結的裝置則多達3次。 </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">您已定義 <span class="keyword"> Audience Manager區段</span> ，以在匿名使用者看到10個曝光後符合資格。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>有了這些條件， <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">合併從目前裝置收集到的匿名未驗證活動，以及由外部裝置圖表連結的3個裝置（每個裝置的廣告曝光數）。 </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">根據由外部裝置圖形和目前裝置連結的所有3個裝置上的匿名活動組合，評估未驗證的使用者區段資格。 </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">將區段傳送至任何即時目的地，以用作目前裝置上的抑制區段，以及所有由外部裝置圖形連結的3個裝置。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 重新定位或網站個人化使用案例 {#retargeting-use-case}

這些策略旨在讓未經驗證或未知的使用者回到您的網站，或在網站上個人化其瀏覽體驗。

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
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">您想要根據匿名使用者在未驗證狀態下在您網站上的活動，為其提供個人化的現場和／或離站體驗。 </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">使用者擁有多種裝置，且可能或未經過您網站的驗證。 </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">使用者在您網站上檢視多個頁面，同時在其目前裝置上以未驗證狀態瀏覽，並透過外部裝置圖形連結最多3個裝置。 </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">您已定義 <span class="keyword"> Audience Manager</span> 區段，以在使用者在未驗證狀態下瀏覽時檢視了您網站上的多個頁面後，才符合其資格。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>有了這些條件， <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">合併從目前裝置收集到的匿名未驗證活動，以及由外部裝置圖表連結的3個裝置（每個裝置的多個頁面檢視）。 </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">根據由外部裝置圖形和目前裝置連結的所有3個裝置上的匿名活動組合，評估未驗證的使用者區段資格。 </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">將區段傳送至任何即時目的地，以便透過目前的裝置以及由外部裝置圖形連結的所有3個裝置，提供個人化的現場和／或場外體驗。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## 外部設備圖形使用案例的配置檔案合併規則選項 {#profile-merge}

這些使用案例的合併規則選項看起來與下列可用的選項類似。 選 [!UICONTROL Authenticated Profile] 項會停用，因為這些設定僅在您選取或時 **[!UICONTROL Current Authenticated Profile]** 才可 **[!UICONTROL Last Authenticated Profile]**&#x200B;用。 您 [!UICONTROL Device Options] 的裝置圖表設定會視您要使用或可用的裝置圖表設定類型而有所不同。

![](assets/merge-rules-external.png)

如需這些裝置圖表處理方式的詳細資訊，請下載我們的PDF、 [Audience manager和外部裝置圖表](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf)。

>[!MORE_LIKE_THIS]
>
>* [描述檔連結裝置圖表使用案例](../../features/profile-merge-rules/profile-link-use-case.md)
>* [描述檔合併規則的一般使用案例](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [描述檔合併規則常見問答集](../../faq/faq-profile-merge.md)

