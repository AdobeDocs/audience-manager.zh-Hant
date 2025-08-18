---
description: 「個人資料合併規則」選項可讓您根據業務需求或目標擴大或收窄受眾對特定受眾的關注。 這些一般使用案例會探索如何使用可用選項，並針對個人、家庭和跨裝置目標定位建立合併規則。
seo-description: Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting.
seo-title: General Use Cases for Profile Merge Rules
solution: Audience Manager
title: 設定檔合併規則的一般使用案例
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 1%

---

# 設定檔合併規則的一般使用案例 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules]選項可讓您根據業務需求或目標，擴大或縮小受眾對特定受眾的關注。 這些一般使用案例會探索如何使用可用選項，並針對個人、家庭和跨裝置目標定位建立合併規則。 [!UICONTROL Profile Merge Rules]使用即時和批次目的地。

>[!TIP]
>
>如需這些[!UICONTROL Merge Rule]設定的定義和說明，請參閱[定義的設定檔合併規則選項](merge-rule-definitions.md)。

## 裝置目標定位 {#device-personalization}

此情境適用於想要針對Audience Manager中定義的對象區段評估單一裝置設定檔的行銷人員，以便使用支援裝置ID的鎖定目標平台（DSP、站上個人化平台和其他以裝置為基礎的目標平台），為裝置提供一致的體驗，而不考慮使用者驗證。

若要建立只鎖定裝置設定檔的規則，請選取&#x200B;**[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**。

![僅限裝置](assets/device-only.png)

假設John擁有三部智慧型手機。 其中兩個是資料計畫A上的iPhone 7s，其中一個是資料計畫B上的Samsung 。並未考慮在這三種裝置上的任何一種狀態，John的行動電信業者想要為他提供資料計畫升級，但僅限於在資料計畫A上執行的iPhone 7裝置。

使用&#x200B;**[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**&#x200B;規則時，[!DNL Device 1]和[!DNL Device 3]都符合區段的資格，而裝置2則被忽略。

![僅限裝置](assets/device-management.png)

## 共用裝置目標定位 {#target-shared-devices}

假設John和他的妻子Jane使用相同的筆記型電腦造訪線上商店，並訂購各種商品。

John使用自己的帳戶預訂旅行票和特別優惠，而Jane則使用自己的帳戶購買音樂和電影。

該商店的行銷團隊可以使用&#x200B;**[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]**&#x200B;規則，純粹根據已驗證的活動，針對具有特定交易的John和Jane進行目標定位。

![current-no-device](assets/current-no-device.png)

一旦使用此規則，Audience Manager就會完全忽略裝置設定檔，讓John的CRM ID符合該區段的資格，而不是讓Jane的CRM ID符合資格。

![共用裝置定位](assets/shared-device-targeting.png)

## 線上/離線鎖定目標 {#device-household-targeting}

此使用案例涵蓋家庭身分管理。 公司可以使用&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]**&#x200B;規則，將單一裝置設定檔與在該裝置上驗證的最後一個設定檔合併。

![last-device-profile](assets/last-device-profile.png)

假設一個區段是由收入超過$100.000/年的家庭所組成，其中至少包含一個在[!DNL iPhone 7]上為[!DNL Data Plan B]的裝置。 我們有兩個家庭設定檔（跨裝置設定檔），分別連線至兩個不同的裝置設定檔。 符合區段資格所需的特徵會分佈在裝置和跨裝置設定檔中。

Audience Manager會合併每個裝置+跨裝置設定檔配對，以檢視合併的特徵集是否符合區段的資格。 由於Audience Manager會評估合併中包含的每個設定檔，因此裝置設定檔和家庭設定檔都可以分段。

裝置和家用設定檔之間的連結可讓Audience Manager讓[!DNL Household 2]符合區段的資格，但無法符合[!DNL Household 1]的資格。 從[!DNL Household 2]，只有[!DNL Device 3]符合區段的資格。 此[!UICONTROL Profile Merge Rule]已讓行銷人員傳送一致的行銷訊息給個別裝置([!DNL Device 3])和更廣泛的家庭([!DNL Household 2])。

![家庭管理](assets/household-management.png)

## 以人物為基礎的目的地目標定位 {#all-cross-device}

>[!IMPORTANT]
>
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 此處未包含任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

此鎖定目標案例僅適用於已購買[!DNL People-Based Destinations]附加元件的客戶。 此規則可讓行銷人員根據客戶自己的已驗證資料觸及客戶。

假設線上retailer想要透過社交平台觸及現有客戶，並根據他們先前的訂單向他們顯示個人化優惠。 透過[!UICONTROL People-Based Destinations]，他們可以從自己的[!DNL CRM]擷取雜湊電子郵件地址至Audience Manager，從離線資料建立區段，並使用該雜湊識別碼將這些區段傳送至他們想要廣告的社交平台，以最佳化他們的廣告支出。

若要深入瞭解此選項，請參閱[以人物為基礎的目的地](../destinations/people-based-destinations-overview.md)。

![所有跨裝置](assets/all-cross-device.png)

## 裝置圖表選項 {#device-graph-options}

為[!UICONTROL device graph]規則選擇[!UICONTROL Profile Merge]選項取決於您的數位財產和業務目標所獨有的條件。 這些一般准則可協助您瞭解何時使用某一種圖表型別與另一種圖表型別。 請注意，您必須與外部裝置圖表具有合約關係，才能使用這些選項。 請參閱下表，瞭解何時選擇裝置圖表選項的一般指引。 如需特定使用案例，請參閱[設定檔連結裝置圖表使用案例](profile-link-use-case.md)和[外部裝置圖表使用案例](external-graph-use-cases.md)。

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置圖表型別 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">設定檔連結裝置圖表</span> </p> </td> 
   <td colname="col2"> <p>以<span class="wintitle">設定檔連結</span>選項建置的<span class="wintitle">設定檔合併</span>規則適用於： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高階客戶驗證的數位屬性。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">重點突出、觸及率低的行銷活動。 <span class="wintitle">設定檔連結</span>裝置圖表只建立在確定性資料上。 相對於未驗證的使用者和裝置集區，此裝置設定檔集區永遠會較小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">客戶必須處於已驗證狀態才能符合細分資格的使用案例。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部裝置圖表選項 </p> </td> 
   <td colname="col2"> <p>使用與<span class="wintitle"> Audience Manager</span>整合的任何外部裝置圖表建置的<span class="keyword">設定檔合併</span>規則適用於： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有低層級客戶驗證的數位屬性。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">廣泛、高觸及率的品牌行銷活動。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">客戶不需要處於已驗證狀態即可符合細分資格的使用案例。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

請觀看以下影片，以概略瞭解[!UICONTROL Profile Merge Rules]的可能使用案例。

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [設定檔連結裝置圖表使用案例](profile-link-use-case.md)
>* [外部裝置圖表使用案例](external-graph-use-cases.md)
>* [設定檔合併規則常見問題集](../../faq/faq-profile-merge.md)
