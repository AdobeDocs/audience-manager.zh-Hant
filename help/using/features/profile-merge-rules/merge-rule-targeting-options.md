---
description: 個人檔案合併規則選項可讓您根據業務需求或目標，擴充或收緊對特定對象的關注。 這些一般使用案例會探索如何使用可用選項，並建立個人、家庭和跨裝置定位的合併規則。
seo-description: 個人檔案合併規則選項可讓您根據業務需求或目標，擴充或收緊對特定對象的關注。 這些一般使用案例會探索如何使用可用選項，並建立個人、家庭和跨裝置定位的合併規則。
seo-title: 設定檔合併規則的一般使用案例
solution: Audience Manager
title: 設定檔合併規則的一般使用案例
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '997'
ht-degree: 4%

---


# 設定檔合併規則的一般使用案例 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 選項可讓您根據業務需求或目標來擴充或收緊受眾對特定受眾的關注。這些一般使用案例會探索如何使用可用選項，並建立個人、家庭和跨裝置定位的合併規則。 [!UICONTROL Profile Merge Rules] 使用即時和批次目的地。

>[!TIP]
>
>有關這些[!UICONTROL Merge Rule]設定的定義和說明，請參閱[配置檔案合併規則選項定義](merge-rule-definitions.md)。

## 裝置定位{#device-personalization}

此案例適用於想要評估Audience Manager中定義之受眾群體之單一裝置設定檔的行銷人員，以便使用支援裝置ID（DSP、臨場感個人化平台和其他裝置型定位平台）的定位平台為裝置提供一致的體驗，而不考慮使用者驗證。

要建立僅針對設備配置檔案的規則，請選擇&#x200B;**[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**。

![僅限裝置](assets/device-only.png)

假設約翰擁有三部智慧手機。 其中兩款是iPhone 7s的資料計畫A，其中一款是三星的資料計畫B。John的行動電信業者未考慮他在這三種裝置上的驗證狀態，而是想為他提供資料計畫升級，但僅適用於在資料計畫A上執行的iPhone 7裝置。

使用&#x200B;**[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**&#x200B;規則，[!DNL Device 1]和[!DNL Device 3]都符合區段資格，而裝置2則會被忽略。

![僅限裝置](assets/device-management.png)

## 共用裝置定位{#target-shared-devices}

假設John和他的妻子Jane使用相同的筆記型電腦去線上商店訂購各種商品。

約翰用自己的賬戶來預訂旅行票和特價優惠，而簡用自己的賬戶來購買音樂和電影。

該商店的行銷團隊可以使用&#x200B;**[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]**&#x200B;規則，根據John和Jane的驗證活動來鎖定特定交易。

![當前——無設備](assets/current-no-device.png)

使用此規則，Audience Manager會完全忽略裝置設定檔、符合區段John的CRM ID資格，而不符合Jane的CRM ID資格。

![共用裝置定位](assets/shared-device-targeting.png)

## 線上／離線定位{#device-household-targeting}

此使用案例涵蓋家庭身份管理。 公司可使用&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]**&#x200B;規則，將單一裝置描述檔與該裝置上經過驗證的最後一個描述檔合併。

![last-device-profile](assets/last-device-profile.png)

讓我們考慮一個由收入超過$100.000/年的家庭組成的部分，其中至少包含一個[!DNL Data Plan B]上的[!DNL iPhone 7]設備。 我們有兩個家用個人檔案（跨裝置個人檔案），每個人都與兩個不同的裝置個人檔案連接。 符合區段資格所需的特性會散布在裝置和跨裝置描述檔中。

Audience Manager會合併每個裝置+跨裝置描述檔配對，以查看合併的一組特徵是否符合區段的資格。 由於Audience Manager會評估合併中包含的每個個人檔案，因此裝置個人檔案和家庭個人檔案都可以分段。

裝置與家庭設定檔之間的連結可讓Audience Manager符合區段[!DNL Household 2]的資格，但不符合[!DNL Household 1]的資格。 在[!DNL Household 2]中，只有[!DNL Device 3]符合區段資格。 此[!UICONTROL Profile Merge Rule]可讓行銷人員將一致的行銷訊息傳送至個別裝置([!DNL Device 3])和更寬的家庭([!DNL Household 2])。

![家庭管理](assets/household-management.png)

## 以人為本的目標{#all-cross-device}

>[!IMPORTANT]
>
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

此定位藍本僅適用於已購買[!DNL People-Based Destinations]附加元件的客戶。 此規則可讓行銷人員根據自己的驗證資料觸及客戶。

比方說，線上零售商想要透過社交平台觸及現有客戶，並根據先前的訂單向他們展示個人化優惠。 透過[!UICONTROL People-Based Destinations]，他們可以將其自己的[!DNL CRM]雜湊電子郵件位址內嵌至Audience Manager、從離線資料建立區段，並使用雜湊識別碼將這些區段傳送至他們要廣告的社交平台，以最佳化其廣告支出。

若要進一步瞭解此選項，請參閱[以人為本的目標](../destinations/people-based-destinations-overview.md)。

![全跨裝置](assets/all-cross-device.png)

## 設備圖形選項{#device-graph-options}

選擇[!UICONTROL Profile Merge]規則的[!UICONTROL device graph]選項取決於您的數位屬性和業務目標所特有的條件。 這些一般准則可協助您瞭解何時使用一種圖形，而不是使用另一種圖形。 請注意，您必須是[Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/zh-Hant/device-co-op/using/home.translate.html)的會員，或與外部裝置圖表有合約關係，才能使用這些選項。 有關何時選擇設備圖形選項的一般指導，請參閱下表。 如需特定使用案例，請參閱[描述檔連結裝置圖表使用案例](profile-link-use-case.md)和[外部裝置圖表使用案例](external-graph-use-cases.md)。

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置圖形類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 描述檔連結裝置圖表</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 使用</span> Profile  <span class="wintitle"> </span> Linkoption構建的Profile Mergerules非常適合： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高等級客戶驗證的數位屬性。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">專注、觸及面低的宣傳活動。 <span class="wintitle">描述檔連結</span>裝置圖表僅建立在確定性資料上。 相對於未驗證的用戶和設備池，此設備配置檔案池始終會更小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">客戶需要處於驗證狀態才能符合區段資格的使用案例。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部裝置圖形選項 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 使用</span> Experience Cloud Device Co- <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> op或與</a> Audience  <span class="keyword"> Manager整合的任何外部裝置圖形建立的描述檔</span> 總成最適合： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有低級別客戶驗證的數位屬性。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">廣泛、廣泛的品牌宣傳。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">客戶不需要處於已驗證狀態才符合區段資格的使用案例。 </li> 
     </ul> </p> <p> <p>提示：如果您是<span class="keyword"> Experience Cloud</span>低驗證度且與任何裝置圖表提供者無關的客戶，則<span class="keyword"> Device Co-op</span>是您的最佳選擇。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

請觀看以下影片，瞭解[!UICONTROL Profile Merge Rules]的可能使用案例。

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [設定檔連結裝置圖表使用案例](profile-link-use-case.md)
>* [外部裝置圖表使用案例](external-graph-use-cases.md)
>* [描述檔合併規則常見問答集](../../faq/faq-profile-merge.md)

