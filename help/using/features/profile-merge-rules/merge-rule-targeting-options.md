---
description: 配置檔案合併規則選項允許您根據業務需要或目標來擴展或收緊受眾關注特定受眾。 這些一般使用案例探討了如何使用可用選項並為單個、家庭和跨設備目標建立合併規則。
seo-description: Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting.
seo-title: General Use Cases for Profile Merge Rules
solution: Audience Manager
title: 設定檔合併規則的一般使用案例
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 2%

---

# 設定檔合併規則的一般使用案例 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 選項允許您根據業務需要或目標擴展或收緊觀眾對特定受眾的關注。 這些一般使用案例探討了如何使用可用選項並為單個、家庭和跨設備目標建立合併規則。 [!UICONTROL Profile Merge Rules] 使用即時和批處理目標。

>[!TIP]
>
>有關這些定義和說明 [!UICONTROL Merge Rule] 設定，請參閱 [配置檔案合併規則選項已定義](merge-rule-definitions.md)。

## 設備目標 {#device-personalization}

本方案適用於希望評估在Audience Manager中定義的受眾段的單個設備配置檔案的營銷人員，以便使用支援設備ID(DSP現場個性化平台和其他基於設備的目標平台)的目標平台向設備提供一致的體驗，而不考慮用戶身份驗證。

要建立僅針對設備配置檔案的規則，請選擇 **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**。

![僅設備](assets/device-only.png)

假設約翰擁有三部智慧手機。 其中兩個是iPhoneA計畫中的7，其中一個是三星B計畫。John的移動運營商不考慮他在三台設備中任何一台上經過身份驗證的狀態，而是希望為他提供資料計畫升級，但只針對在資料計畫A上運行的iPhone7設備。

使用 **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** 規則， [!DNL Device 1] 和 [!DNL Device 3] 兩者均符合該段的條件，而忽略設備2。

![僅設備](assets/device-management.png)

## 共用設備目標 {#target-shared-devices}

比如說，約翰和他的妻子簡，使用同一台筆記型電腦訪問一家線上商店並訂購各種商品。

John用自己的賬戶來預訂旅行票和特別交易，而Jane用自己的賬戶來購買音樂和電影。

商店的營銷團隊可以 **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** 將John和Jane的交易目標定為具體交易，這完全基於他們經過認證的行為。

![無設備電流](assets/current-no-device.png)

通過使用此規則，Audience Manager將完全忽略設備配置檔案，為段限定John的CRM ID，而不限定Jane的CRM ID。

![共用設備目標](assets/shared-device-targeting.png)

## 聯機/離線目標 {#device-household-targeting}

此用例涵蓋家庭身份管理。 公司可以使用 **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** 規則。

![最後設備配置檔案](assets/last-device-profile.png)

讓我們考慮一個由年收入超過100.000美元/年的家庭組成的部分，其中至少包含一個設備， [!DNL iPhone 7] 上 [!DNL Data Plan B]。 我們有兩個家庭配置式（跨設備配置式），每個配置式都連接到兩個不同的設備配置式。 符合該段要求的特徵分佈在設備和跨設備配置檔案之間。

Audience Manager合併每個設備+跨設備配置檔案對，以查看合併的一組特徵是否符合段的條件。 由於Audience Manager評估合併中包括的每個簡檔，因此設備簡檔和家庭簡檔都可被分段。

設備和家庭簡檔之間的連接允許Audience Manager符合 [!DNL Household 2] 分部，但 [!DNL Household 1]。 從 [!DNL Household 2]只 [!DNL Device 3] 符合該分部的資格。 此 [!UICONTROL Profile Merge Rule] 已使商家能夠向單個設備傳遞一致的營銷消息([!DNL Device 3])和更廣大的家庭([!DNL Household 2])。

![家庭管理](assets/household-management.png)

## 針對基於人的目標 {#all-cross-device}

>[!IMPORTANT]
>
>本文包含旨在指導您完成此功能的設定和使用的產品文檔。 這裡沒有法律建議。 請咨詢您自己的法律顧問以獲得法律指導。

此目標方案僅適用於已購買 [!DNL People-Based Destinations] 附件。 此規則允許商家根據自己的經過身份驗證的資料聯繫客戶。

比如，一家線上零售商希望通過社交平台接觸現有客戶，並根據之前的訂單向他們展示個性化的優惠。 與 [!UICONTROL People-Based Destinations]，他們可以從自己的郵箱中攝取哈希的電子郵件地址 [!DNL CRM] 在Audience Manager中，從離線資料構建段，並將這些段發送到他們希望在其上進行廣告的社交平台，使用經過散列的標識符優化其廣告支出。

要瞭解有關此選項的詳細資訊，請參閱 [基於人的目的地](../destinations/people-based-destinations-overview.md)。

![全跨設備](assets/all-cross-device.png)

## 設備圖形選項 {#device-graph-options}

選擇 [!UICONTROL device graph] 選項 [!UICONTROL Profile Merge] 規則取決於您的數字屬性和業務目標所特有的條件。 這些一般准則可以幫助您瞭解何時使用一種圖形與另一種圖形。 請注意，您必須是 [Adobe Experience Cloud設備合作](https://experienceleague.adobe.com/docs/device-co-op/using/home.html) 或與外部設備圖形有合同關係以使用這些選項。 有關何時選擇設備圖形選項的一般指導，請參閱下表。 有關特定使用案例，請參見 [配置檔案連結設備圖形使用案例](profile-link-use-case.md) 和 [外部設備圖形使用案例](external-graph-use-cases.md)。

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設備圖形類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 配置檔案連結設備圖</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 配置檔案合併</span> 使用 <span class="wintitle"> 配置檔案連結</span> 選項非常適合： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高級客戶身份驗證的數字屬性。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">重點突出、影響範圍小的活動。 的 <span class="wintitle"> 配置檔案連結</span> 設備圖只建立在確定性資料上。 與未經身份驗證的用戶和設備池相比，此設備配置檔案池始終會更小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">使用客戶需要處於經過驗證的狀態才能符合細分要求的案例。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部設備圖形選項 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 配置檔案合併</span> 使用 <a href="https://experienceleague.adobe.com/docs/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud設備合作</a> 或任何整合的外部設備圖形 <span class="keyword"> Audience Manager</span> 適合： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有低級別客戶身份驗證的數字屬性。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">廣泛、影響深遠的品牌宣傳。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">使用客戶不需要處於經過驗證的狀態才有資格進行細分的情況。 </li> 
     </ul> </p> <p> <p>提示：的 <span class="keyword"> 設備合作</span> 如果你是 <span class="keyword"> Experience Cloud</span> 身份驗證低且與任何設備圖形提供商沒有關係的客戶。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

觀看以下視頻，瞭解可能的使用案例 [!UICONTROL Profile Merge Rules]。

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [設定檔連結裝置圖表使用案例](profile-link-use-case.md)
>* [外部裝置圖表使用案例](external-graph-use-cases.md)
>* [配置檔案合併規則常見問題](../../faq/faq-profile-merge.md)

