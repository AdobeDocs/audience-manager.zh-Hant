---
description: Recommendations和使用案例，透過外部裝置圖表為未知使用者探索、重新鎖定目標和個人化。 外部裝置圖表定義為與Audience Manager分開的裝置圖表。 這包括Adobe Experience Cloud Device Co-op和其他與協力廠商確定性或可能性裝置圖形公司整合的Adobe。
seo-description: Recommendations和使用案例，透過外部裝置圖表為未知使用者探索、重新鎖定目標和個人化。 外部裝置圖表定義為與Audience Manager分開的裝置圖表。 這包括Adobe Experience Cloud Device Co-op和其他與協力廠商確定性或可能性裝置圖形公司整合的Adobe。
seo-title: 外部裝置圖表使用案例
solution: Audience Manager
title: 外部裝置圖表使用案例
uuid: f4bc822d-39d2-4680-90ed-7ee2ead6db6f
feature: 個人資料合併
exl-id: 657aecfd-7fa3-466e-8331-c49cc921e3a9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 5%

---

# 外部裝置圖表使用案例 {#external-device-graph-use-cases}

Recommendations和使用案例，透過外部裝置圖表為未知使用者探索、重新鎖定目標和個人化。 外部裝置圖表定義為與Audience Manager分開的裝置圖表。 這包括[!DNL Adobe Experience Cloud Device Co-op]和其他整合Adobe與第三方確定性或可能性裝置圖表公司的整合。

## 建議 {#recommendations}

請考量促銷活動的[!DNL Experience Cloud Device Co-op]和協力廠商裝置圖表選項，這些促銷活動包括：

* 其數位屬性的驗證層級較低。 如果您有大量已驗證的使用者，請使用[!UICONTROL Profile Link Device Graph option]。
* 鎖定大型受眾。 [!DNL Experience Cloud Device Co-op]和協力廠商裝置圖表包含已驗證和未驗證的資料。
* 在個人和家庭層級劃分已驗證和/或未驗證的訪客。

![](assets/merge-rule-triangle1.png)
<!-- 
## Prospecting/Branding Use Case {#prospecting-branding-use-cases}

A branding campaign is designed to reach as many people as possible. It places few limits on segment qualification. But, these campaigns can waste budget and impressions by constantly targeting people who see your content multiple times and don't convert. A [!UICONTROL Profile Merge] rule that uses the [!DNL Device Co-op] or third-party option can help you create an efficient branding campaign. For example, you can add these unknown users to a "not in-market" segment after seeing them across multiple devices for your set frequency cap.

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">This use case assumes these conditions: <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">You want to deliver a maximum of 10 impressions to an anonymous user for a specific ad campaign. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">A user has 4 devices and may or may not have authenticated on your site. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">An anonymous user sees the ad a total of 10 times while browsing in an unauthenticated state on their current device and 3 devices linked to the current device by an external device graph. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Merges the anonymous, unauthenticated activity collected from the current device and the 3 devices linked by the external device graph (the ad impressions from each device). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Evaluates the unauthenticated user for segment qualification based on a combination of anonymous activity across all 3 devices linked by the external device graph and the current device. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Sends the segment to any real-time destination for use as a suppression segment on the current device and all 3 devices linked by the external device graph. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#retargeting-use-case}

These strategies are designed to bring an unauthenticated or unknown user back to your site or personalize their browsing experience while they're on-site.

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">This use case assumes these conditions: <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">You want to deliver a personalized on-site and/or off-site experience to an anonymous user based on their activity on your site while in an unauthenticated state. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">A user has multiple devices and may or may not have authenticated to your site. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">A user views multiple pages on your site while browsing in an unauthenticated state on their current device and 3 other devices linked by an external device graph. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state.</li>
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Merges the anonymous, unauthenticated activity collected from the current devices and the 3 devices linked by the external device graph (the multiple page views from each device). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Evaluates the unauthenticated user for segment qualification based on a combination of anonymous activity across all 3 devices linked by the external device graph and the current device. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Sends the segment to any real-time destination to deliver a personalized on-site and/or off-site experience across the current device and all 3 devices linked by the external device graph. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table> -->

## 擴展設備目標定位{#audience-expansion}

此使用案例說明如何透過[!DNL Adobe Co-Op Device Graph]或其他[!DNL External Device Graphs]，透過精確的跨裝置個人化來擴充可定址對象的大小。

假設簡有三台設備，她經常用這些設備來搜索度假套餐：她的筆記型電腦([!DNL Device 1])、智慧手機([!DNL Device 2])和平板電腦([!DNL Device 3])。 使用筆記型電腦時，Jane搜尋了航班、酒店和導遊。 在使用智慧手機和平板電腦時，她只訪問了旅行社的首頁。

通過使用[!UICONTROL No Cross-Device Profile] + [!UICONTROL Adobe Co-op Device Graph]規則，旅行社可以合併所有三個設備配置檔案，因為它們通過[!UICONTROL Adobe Co-op Device Graph]連結到同一個所有者。

![audience-expansion-rule](assets/audience-expansion-rule.png)

在我們的範例中，[!DNL Device 1]上已收集符合區段資格所需的特徵。 由於Audience Manager符合參與區段之設定檔合併的每個裝置設定檔的資格，因此Jane的三個裝置設定檔現在都會進行分段。

透過此規則，裝置圖表將符合區段資格的裝置設定檔數量從1個擴充至3個，讓旅行社能將一致的訊息傳送給Jane擁有的所有三部裝置。

![對象擴展](assets/audience-expansion.png)

## 進階跨裝置鎖定目標{#advanced-graph-expansion}

此使用案例顯示如何透過外部裝置圖表或[!DNL Adobe Co-Op Device Graph]中的裝置，使用&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Adobe Co-Op Device Graph]**&#x200B;規則，針對已驗證的訪客擴展受眾鎖定目標。

![最後裝置圖表](assets/last-device-coop.png)

在以下範例中，Acme Inc.公司想要鎖定所有年收入超過$100.000/年、[!DNL Data Plan A]上訂閱[!DNL Acme Inc.]且使用[!DNL iPhone 7]裝置的家庭。

John在資料計畫A上使用iPhone 7，在Acme Inc.網站上驗證。 同時，John的[!DNL Co-Op Device Graph]群集包含他經常使用的另外兩個設備：他的筆記型電腦([!DNL Device 1])和次要智慧手機[!DNL Device 2]（[!DNL Data Plan B]上的[!DNL Samsung S7]）。

透過使用&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Adobe Co-Op Device Graph]**,[!DNL Acme Inc.]可從John的裝置圖表叢集傳送個人化訊息至所有三部裝置，即使其中只有一部裝置最初符合區段資格亦然。

![進階圖表展開](assets/advanced-device-graph-expansion.png)

>[!MORELIKETHIS]
>
>* [設定檔連結裝置圖表使用案例](profile-link-use-case.md)
* [設定檔合併規則的一般使用案例](merge-rule-targeting-options.md)
* [設定檔合併規則常見問題集](../../faq/faq-profile-merge.md)

