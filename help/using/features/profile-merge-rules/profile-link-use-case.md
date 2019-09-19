---
description: 使用描述檔連結裝置圖表，針對區段重新定位和個人化區段資格的建議和使用案例。
seo-description: 使用描述檔連結裝置圖表，針對區段重新定位和個人化區段資格的建議和使用案例。
seo-title: 描述檔連結裝置圖表使用案例
solution: Audience Manager
title: 描述檔連結裝置圖表使用案例
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 描述檔連結裝置圖表使用案例 {#profile-link-device-graph-use-cases}

透過裝置圖表，針對細分重新定位及個人化細分資格的建議和使 [!UICONTROL Profile Link] 用案例。

## 建議 {#recommendations}

請考慮適 [!UICONTROL Profile Link] 用於下列促銷活動的裝置圖表：

* 在其數位屬性上擁有高等級的驗證。 如果您 [有少量已驗證的使用者](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) ，請使用外部裝置圖形選項。
* 需要精確鎖定已知受眾。 使 [!UICONTROL Profile Link device graph] 用第一方驗證資料建立。
* 即時鎖定已知受眾的已驗證和未驗證狀態。

![](assets/merge-rule-triangle2.png)

## 重新定位使用案例和描述檔合併規則設定 {#retargeting-use-cases}

重新鎖定先前已在多個裝置上驗證網站和／或應用程式內的觀眾。 區段可由下列描述檔組成：

* 上次已知的已驗證裝置設定檔。
* 每個裝置設定檔的匿名活動。

>[!NOTE]
>
>其中一種描述檔類型的特徵資訊可用於建立區段。

### 重新定位範例

讓我們來看看這個例子如何與信用卡公司合作。 此範例僅使用從3個裝置設定檔所檢視的匿名活動收集的特徵資訊。

<table id="table_8C5ABA47A0634EBA9B1AA1B5C2AABF07"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>條件</b> </p> </td> 
   <td colname="col2"> <p>此使用案例假設下列條件： </p> <p> 
     <ul id="ul_72373D0F304044AE84E4CC055E3E8154"> 
      <li id="li_375DA786ED4D4F18A74C8FE42ABF8448">使用者有3種裝置，是最後一個在信用卡公司網站／應用程式上在所有3種裝置上進行驗證的人。 </li> 
      <li id="li_77FDBFAED21B4DE19AB2B6C112E0C64B">在第一裝置上，處於未驗證狀態的用戶查看優質信用卡的選件。 </li> 
      <li id="li_D3BE1B30BCCA49EA931AA9D97DD5F86D">在第二裝置上，處於未驗證狀態的使用者檢視優質信用卡優惠頁面。 </li> 
      <li id="li_39D894624FC44806B6DB2C77F459B39E">在第三裝置上，處於未驗證狀態的使用者檢視優質信用卡費用和費率頁面。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>有了這些條件， <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_1B6174F5C3AF4C32831D4217C5113789"> 
      <li id="li_98FE54696B604C3C8D93CC1C1FBB48D9">使用目前裝置上最後一個已驗證的設定檔，合併從所有3個裝置收集的匿名未驗證活動。 </li> 
      <li id="li_A73C7DCE36BA42B6BAD26D8A075416C1">根據下列項目評估匿名使用者的區段資格： 
       <ul id="ul_EF66EAFD12CA44F5ACCB66319606D937"> 
        <li id="li_541762056ECF4BC1ABF1F5116B5FED6C">所有3種裝置上的匿名活動組合。 </li> 
        <li id="li_C386CB62E5234E10AFEDE900ADC0E261">目前裝置上最後一個已驗證的設定檔。 </li> 
       </ul> </li> 
      <li id="li_5C9BDC8FF886494589F005C9658A923C">將區段傳送至任何即時目的地，以便在所有3種裝置上重新定位。 </li>
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 重新定位描述檔合併規則範例

若要設定重新定位 [!UICONTROL Profile Link]，您的 [!UICONTROL Authenticated Options] 和 [!UICONTROL Device Options] 應如下所示的規則設定。 這些 [!UICONTROL Authenticated Profile] 選項與此範例不同，因為這些設定會使用跨裝置資料來源的名稱。

![描述檔合併規則設定](assets/merge-rules-internal3.png)

## 個人化使用案例和描述檔合併規則設定 {#personalization-use-case}

根據跨多種裝置的活動，為經過驗證的現場和／或應用程式內受眾提供個人化體驗。 區段可由下列描述檔組成：

* 目前已驗證的裝置設定檔。
* 匿名裝置設定檔。

>[!NOTE]
>
>使用者必須處於已驗證狀態才能符合區段的資格。

### 個人化範例

讓我們來看看這個例子如何與信用卡公司合作。

<table id="table_D2F4D5D27EB54224BB2CC1D843DDEDA3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 使用案例 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>條件</b> </p> </td> 
   <td colname="col2"> <p>我們的使用案例假定以下條件： </p> <p> 
     <ul id="ul_C4D2108E7B1C4D3C89411A9CCCDA6DAC"> 
      <li id="li_2F10EB17466B4B91A94DF707C3CB6BE5">使用者有3種裝置，是最後一個在信用卡公司網站／應用程式上在所有3種裝置上進行驗證的人。 </li> 
      <li id="li_1559C4DA51254BCF95291133F32A4057">在第一裝置上，處於未驗證狀態的用戶查看優質信用卡的選件。 </li> 
      <li id="li_734465E5619C474291C42921160CEC6B">在第二裝置上，處於未驗證狀態的使用者檢視優質信用卡優惠頁面。 </li> 
      <li id="li_B96ABC0205384B59A1901708505B8BF8">在第三裝置上，處於未驗證狀態的使用者檢視優質信用卡費用和費率頁面。 </li> 
      <li id="li_1A7BDBD546BD4B8EACF4292D885127F2">客戶會在其中任何裝置上進行驗證（登入）以檢查其餘額。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>結果</b> </p> </td> 
   <td colname="col2"> <p>有了這些條件， <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_37DBF5FEABC5463D85C74AD9150EA177"> 
      <li id="li_B60FFA5CF3F64FB69997AA05595900D7">使用目前已驗證的設定檔，合併從所有3台裝置收集的匿名未驗證活動。 已驗證的描述檔在每個裝置上提供通用識別碼。 </li> 
      <li id="li_AB9FD87DD804474BA33805C364B7B92D">根據下列項目評估已驗證的使用者區段資格： 
       <ul id="ul_EAF99E72159D4E329052B71344D9C69B"> 
        <li id="li_0B5E52BA6D8B493980291EA7B0AE235A">所有3種裝置上的匿名活動組合。 </li> 
        <li id="li_07588DEFBEF64F97850CB12CD62D0213">目前已驗證的個人檔案。 </li> 
       </ul> </li> 
      <li id="li_E7CFCEAD7610496189F4486000D7860A">將區段傳送至任何即時目的地，以便在使用者目前裝置上進行驗證時為其建立個人化瀏覽體驗。 <p>注意： 這可讓區段的3個裝置符合資格，不論驗證狀態為何。 如果這些裝置是共用裝置，這可能會造成隱私權方面的顧慮。 </p> </li>
     </ul> </p> </td>
  </tr>
 </tbody> 
</table>

### 個人化描述檔合併規則範例

若要設定個人化， [!UICONTROL Profile Link]您的 [!UICONTROL Authenticated Options] 和 [!UICONTROL Device Options] 應類似下列的規則設定。 這些 [!UICONTROL Authenticated Profile] 選項與此範例不同，因為這些設定會使用跨裝置資料來源的名稱。

![](assets/merge-rules-internal4.png)

如需這些裝置圖表處理方式的詳細資訊，請下載我們的PDF、 [Audience manager和外部裝置圖表](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf)。

>[!MORE_LIKE_THIS]
>
>* [外接式裝置圖表使用案例](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [描述檔合併規則的一般使用案例](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [描述檔合併規則常見問答集](../../faq/faq-profile-merge.md)

