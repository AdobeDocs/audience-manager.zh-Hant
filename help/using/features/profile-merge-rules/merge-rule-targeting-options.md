---
description: 「設定檔合併規則」選項可讓您根據業務需求或目標，擴大或縮小對象對特定對象的關注。 這些一般使用案例探討如何使用可用選項，以及為個人、家庭和跨裝置鎖定目標建立合併規則。
seo-description: 「設定檔合併規則」選項可讓您根據業務需求或目標，擴大或縮小對象對特定對象的關注。 這些一般使用案例探討如何使用可用選項，以及為個人、家庭和跨裝置鎖定目標建立合併規則。
seo-title: 設定檔合併規則的一般使用案例
solution: Audience Manager
title: 設定檔合併規則的一般使用案例
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: 個人資料合併
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 4%

---

# 設定檔合併規則的一般使用案例 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 選項可讓您根據業務需求或目標，擴大或縮小受眾對特定受眾的關注。這些一般使用案例探討如何使用可用選項，以及為個人、家庭和跨裝置鎖定目標建立合併規則。 [!UICONTROL Profile Merge Rules] 處理即時和批次目的地。

>[!TIP]
>
>有關這些[!UICONTROL Merge Rule]設定的定義和說明，請參閱[定義的配置檔案合併規則選項](merge-rule-definitions.md)。

## 裝置目標定位{#device-personalization}

此情境適用於想要針對Audience Manager中定義的對象區段評估單一裝置設定檔的行銷人員，以便使用支援裝置ID的鎖定目標平台(DSP、站上個人化平台和其他以裝置為基礎的鎖定目標平台)為裝置提供一致的體驗，而不考慮使用者驗證。

若要建立僅鎖定裝置設定檔的規則，請選取&#x200B;**[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**。

![僅限裝置](assets/device-only.png)

假設約翰擁有三部智慧手機。 其中兩部是A型資料計畫的iPhone 7，其中一部是B型資料計畫的三星。John的移動運營商不考慮他在這三部設備中的驗證狀態，而是希望為他提供資料計畫升級，但只針對在A型資料計畫上運行的iPhone 7設備。

使用&#x200B;**[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**&#x200B;規則，[!DNL Device 1]和[!DNL Device 3]都符合區段資格，而裝置2會遭忽略。

![僅限裝置](assets/device-management.png)

## 共用裝置目標定位{#target-shared-devices}

假設John和妻子Jane使用同一台筆記型電腦訪問線上商店並訂購各種商品。

約翰用自己的賬戶來預訂旅行票和特別優惠，而簡則用自己的賬戶來購買音樂和電影。

該商店的行銷團隊可使用&#x200B;**[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]**&#x200B;規則，純粹根據其已驗證的活動，透過特定交易鎖定John和Jane。

![當前 — 無設備](assets/current-no-device.png)

使用此規則時，Jane會完全忽略裝置設定檔、為區段授與John的CRM ID資格，而不符合Jane的CRM ID資格。

![共用裝置鎖定](assets/shared-device-targeting.png)

## 線上/離線定位{#device-household-targeting}

此使用案例涵蓋家庭身份管理。 公司可使用&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]**&#x200B;規則，將單一裝置設定檔與該裝置上已驗證的最後一個設定檔合併。

![last-device-profile](assets/last-device-profile.png)

讓我們考慮一個由收入超過$100.000/年的家庭組成的部分，其中至少包含一個[!DNL Data Plan B]上的[!DNL iPhone 7]設備。 我們有兩個家庭設定檔（跨裝置設定檔），每個設定檔都連接至兩個不同的裝置設定檔。 符合區段資格所需的特徵會分佈在裝置與跨裝置設定檔中。

Audience Manager會合併每個裝置+跨裝置設定檔組，以查看合併的一組特徵是否符合區段資格。 由於Audience Manager會評估合併中包含的每個設定檔，因此裝置設定檔和家庭設定檔都可以分段。

裝置和家庭設定檔之間的連結可讓Audience Manager符合區段的[!DNL Household 2]資格，但不能[!DNL Household 1]資格。 從[!DNL Household 2]，只有[!DNL Device 3]符合區段資格。 此[!UICONTROL Profile Merge Rule]可讓行銷人員傳送一致的行銷訊息給個別裝置([!DNL Device 3])和較寬的家庭([!DNL Household 2])。

![家庭管理](assets/household-management.png)

## 以人物為基礎的目的地鎖定目標{#all-cross-device}

>[!IMPORTANT]
>
>本文包含的產品檔案旨在引導您完成此功能的設定與使用。 這裡沒有任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

此定位案例僅適用於已購買[!DNL People-Based Destinations]附加元件的客戶。 此規則可讓行銷人員根據自己的已驗證資料觸及客戶。

假設某個線上零售商想要透過社交平台觸及現有客戶，並根據先前的訂單顯示個人化優惠方案。 透過[!UICONTROL People-Based Destinations]，他們可以將自己的[!DNL CRM]雜湊電子郵件地址內嵌至Audience Manager、從離線資料建立區段，並使用該雜湊識別碼將這些區段傳送至要廣告的社交平台，以最佳化其廣告支出。

若要深入了解此選項，請參閱[以人物為基礎的目的地](../destinations/people-based-destinations-overview.md)。

![全跨裝置](assets/all-cross-device.png)

## 裝置圖表選項{#device-graph-options}

為[!UICONTROL Profile Merge]規則選擇[!UICONTROL device graph]選項取決於您的數位屬性和業務目標所特有的條件。 這些一般准則可協助您了解何時使用一種圖形，而何時使用另一種圖形。 請注意，您必須是[Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/zh-Hant/device-co-op/using/home.translate.html)的成員，或與外部裝置圖表有合約關係，才能使用這些選項。 請參閱下表，了解選擇裝置圖表選項的一般指引。 如需特定使用案例，請參閱[設定檔連結裝置圖表使用案例](profile-link-use-case.md)和[外部裝置圖表使用案例](external-graph-use-cases.md)。

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置圖表類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 設定檔連結裝置圖表</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 使用</span> 「設定檔連結」選項 <span class="wintitle"> 建</span> 立的設定檔合併，非常適合： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高級別客戶驗證的數位屬性。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">重點突出、觸及面低的行銷活動。 <span class="wintitle">設定檔連結</span>裝置圖表僅建置在確定性資料上。 相對於未驗證的使用者和裝置池，此裝置設定檔池一律較小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">客戶需要處於驗證狀態才能符合分段資格的使用案例。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部裝置圖表選項 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 以</span> Experience Cloud裝置共同 <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> 作業或任何與Audience Manager整</a> 合的外部裝置圖表所建 <span class="keyword"> 立的設</span> 定檔合併，是下列最佳選擇： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有低級別客戶驗證的數位屬性。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">廣泛、廣泛的品牌宣傳。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">客戶不需要處於已驗證狀態才能符合分段資格的使用案例。 </li> 
     </ul> </p> <p> <p>提示：如果您是驗證率低且與任何裝置圖表提供者沒有任何關係的<span class="keyword">Experience Cloud</span>客戶，<span class="keyword"> Device Co-op</span>是最佳選項。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

請觀看以下影片，概略了解[!UICONTROL Profile Merge Rules]的可能使用案例。

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [設定檔連結裝置圖表使用案例](profile-link-use-case.md)
* [外部裝置圖表使用案例](external-graph-use-cases.md)
* [設定檔合併規則常見問題集](../../faq/faq-profile-merge.md)

