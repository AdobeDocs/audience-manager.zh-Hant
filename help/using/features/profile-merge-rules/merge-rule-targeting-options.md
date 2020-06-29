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

[!UICONTROL Profile Merge Rules] 選項可讓您根據業務需求或目標來擴充或收緊受眾對特定受眾的關注。 這些一般使用案例會探索如何使用可用選項，並建立個人、家庭和跨裝置定位的合併規則。 [!UICONTROL Profile Merge Rules] 使用即時和批次目的地。

>[!TIP]
>
>有關這些設定的定義和說 [!UICONTROL Merge Rule] 明，請參 [閱定義的配置檔案合併規則選項](merge-rule-definitions.md)。

## 裝置定位 {#device-personalization}

此案例適用於想要評估Audience Manager中定義之受眾群體之單一裝置設定檔的行銷人員，以便使用支援裝置ID（DSP、臨場感個人化平台和其他裝置型定位平台）的定位平台為裝置提供一致的體驗，而不考慮使用者驗證。

若要建立僅針對裝置設定檔的規則，請選取 **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**。

![僅限裝置](assets/device-only.png)

假設約翰擁有三部智慧手機。 其中兩款是iPhone 7s的資料計畫A，其中一款是三星的資料計畫B。 John的行動電信業者未考慮他在這三種裝置上的驗證狀態，而是想為他提供資料計畫升級，但僅適用於在資料計畫A上執行的iPhone 7裝置。

使用 **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** 規則 [!DNL Device 1] ，並且兩 [!DNL Device 3] 者都符合區段的資格，而裝置2則會被忽略。

![僅限裝置](assets/device-management.png)

## 共用裝置定位 {#target-shared-devices}

假設John和他的妻子Jane使用相同的筆記型電腦去線上商店訂購各種商品。

約翰用自己的賬戶來預訂旅行票和特價優惠，而簡用自己的賬戶來購買音樂和電影。

該店的行銷團隊可使用 **[!UICONTROL Current Authenticated Profiles]** +規 **[!UICONTROL No Device Profile]** 則，根據John和Jane的驗證活動，針對特定交易進行鎖定。

![當前——無設備](assets/current-no-device.png)

使用此規則，Audience Manager會完全忽略裝置設定檔、符合區段John的CRM ID資格，而不符合Jane的CRM ID資格。

![共用裝置定位](assets/shared-device-targeting.png)

## 線上／離線定位 {#device-household-targeting}

此使用案例涵蓋家庭身份管理。 公司可以使用+規則，將單一裝置描述檔與在該裝置上驗證的最後一個描述檔 **[!UICONTROL Last Authenticated Profiles]** 合併 **[!UICONTROL Device Profile]** 。

![last-device-profile](assets/last-device-profile.png)

讓我們考慮一個由年收入超過$100.000美元的家庭組成的部分，其中至少包含一個 [!DNL iPhone 7] 設備 [!DNL Data Plan B]。 我們有兩個家用個人檔案（跨裝置個人檔案），每個人都與兩個不同的裝置個人檔案連接。 符合區段資格所需的特性會散布在裝置和跨裝置描述檔中。

Audience Manager會合併每個裝置+跨裝置描述檔配對，以查看合併的一組特徵是否符合區段的資格。 由於Audience Manager會評估合併中包含的每個個人檔案，因此裝置個人檔案和家庭個人檔案都可以分段。

裝置與家庭個人檔案之間的連結可讓Audience Manager符合區段 [!DNL Household 2] 資格，但無法 [!DNL Household 1]。 從 [!DNL Household 2]，僅 [!DNL Device 3] 符合區段資格。 這 [!UICONTROL Profile Merge Rule] 可讓行銷人員向個別裝置([!DNL Device 3])和更廣大的家庭([!DNL Household 2])傳遞一致的行銷訊息。

![家庭管理](assets/household-management.png)

## 以人為本的目標鎖定 {#all-cross-device}

>[!IMPORTANT]
>
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

此定位藍本僅適用於已購買附加元件 [!DNL People-Based Destinations] 的客戶。 此規則可讓行銷人員根據自己的驗證資料觸及客戶。

比方說，線上零售商想要透過社交平台觸及現有客戶，並根據先前的訂單向他們展示個人化優惠。 有了 [!UICONTROL People-Based Destinations]，他們可以將自己的雜湊電子郵件地址收錄到 [!DNL CRM] Audience Manager中、從離線資料建立區段，並將這些區段傳送至他們想要廣告的社交平台，使用雜湊識別碼，最佳化其廣告支出。

若要進一步瞭解此選項，請參 [閱以人為本的目的地](../destinations/people-based-destinations-overview.md)。

![全跨裝置](assets/all-cross-device.png)

## 裝置圖表選項 {#device-graph-options}

選擇規 [!UICONTROL device graph] 則的選項 [!UICONTROL Profile Merge] 取決於您的數位屬性和業務目標所特有的條件。 這些一般准則可協助您瞭解何時使用一種圖形，而不是使用另一種圖形。 請注意，您必須是 [Adobe Experience Cloud Device Co-op的會員](https://docs.adobe.com/content/help/zh-Hant/device-co-op/using/home.translate.html) ，或與外部裝置圖表有合約關係才能使用這些選項。 有關何時選擇設備圖形選項的一般指導，請參閱下表。 如需特定使用案例，請參 [閱描述檔連結裝置圖表使用案例](profile-link-use-case.md)[和外部裝置圖表使用案例](external-graph-use-cases.md)。

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
   <td colname="col2"> <p><span class="wintitle"> 使用「描述檔</span> 連結」選項建立的 <span class="wintitle"> 「描述檔合併規則</span> 」最適合： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高等級客戶驗證的數位屬性。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">專注、觸及面低的宣傳活動。 描述 <span class="wintitle"> 檔連結</span> (Profile Link)裝置圖表僅建立在確定性資料上。 相對於未驗證的用戶和設備池，此設備配置檔案池始終會更小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">客戶需要處於驗證狀態才能符合區段資格的使用案例。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部裝置圖形選項 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 使用</span> Experience Cloud Device Co-op建立描述檔合併規則 <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> ，或與</a><span class="keyword"></span> Audience Manager整合的任何外部裝置圖表，最適合： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有低級別客戶驗證的數位屬性。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">廣泛、廣泛的品牌宣傳。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">客戶不需要處於已驗證狀態才符合區段資格的使用案例。 </li> 
     </ul> </p> <p> <p>提示： 如果 <span class="keyword"> 您是Experience Cloud</span><span class="keyword"></span> （低驗證率）客戶，且與任何裝置圖形提供者沒有關係，則Device Co-op是您的最佳選擇。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

請觀看以下影片，以取得可能使用案例的概觀 [!UICONTROL Profile Merge Rules]。

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [設定檔連結裝置圖表使用案例](profile-link-use-case.md)
>* [外部裝置圖表使用案例](external-graph-use-cases.md)
>* [描述檔合併規則常見問答集](../../faq/faq-profile-merge.md)

