---
description: 個人資料合併規則選項可讓您根據業務需求或目標，展開或緊縮對象專注於特定受眾。這些一般使用案例探討如何使用可用選項，並建立個人、家庭和跨裝置目標鎖定規則。描述檔合併規則目前僅適用於即時目的地。
seo-description: 個人資料合併規則選項可讓您根據業務需求或目標，展開或緊縮對象專注於特定受眾。這些一般使用案例探討如何使用可用選項，並建立個人、家庭和跨裝置目標鎖定規則。描述檔合併規則目前僅適用於即時目的地。
seo-title: 描述檔合併規則的一般使用案例
solution: Audience Manager
title: 描述檔合併規則的一般使用案例
uuid: c9eb41c8-fe19-45f8-9ff1-552c11 ef08 da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# General Use Cases for Profile Merge Rules {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 選項可讓您根據業務需求或目標，擴大或緊縮對象對特定受眾的關注程度。這些一般使用案例探討如何使用可用選項，並建立個人、家庭和跨裝置目標鎖定規則。Currently, [!UICONTROL Profile Merge Rules] work with real-time destinations only.

![](assets/merge-rules-options.png)

>[!TIP]
>
>For definitions and descriptions of these [!UICONTROL Merge Rule] settings, see [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md).

## Focused targeting {#focused-targeting}

User authentication to a website should trigger a declared ID call to [!DNL Audience Manager]. After this event, [!DNL Audience Manager] writes trait data to (and reads from) an authenticated profile. The authenticated profile lets [!DNL Audience Manager]:

* 將特性寫入特定使用者專屬的已驗證設定檔。
* 識別並區分多個裝置使用者以進行分段。

### 觸及已驗證的使用者

已驗證的描述檔選項可建立規則，讓您定位根據離線屬性登入網站或應用程式的使用者。例如，金融服務公司會使用此選項來定位已驗證的使用者，使用目標信用卡升級優惠或根據收入或離線活動的專業化服務提供方案。另一個例子是，航空公司將基於交易里程的交易進行驗證。

To create a rule that reaches only authenticated users, select **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. 此選項只會使用已驗證的描述檔資料來評估區段。此規則會忽略匿名裝置設定檔中的資料。

To also include data in the anonymous device profile, use the **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL Current Device Profile]** rule.

### 根據先前的驗證狀態觸及使用者

這些選項會在使用者瀏覽但未登入時觸及到特定使用者。您可以使用依賴於使用者層級定位的選項來執行此動作。反向定位可協助您覆蓋未明確驗證至您網站但可能線上瀏覽的訪客。它可借由從上次驗證的個人檔案讀取(但不是寫入)資料來運作。And, to help keep the authenticated profile clean, [!DNL Audience Manager] writes new trait qualifications to the device profile instead of the authenticated profile. 例如，假設您是行銷人員，想要向未登入您網站或應用程式的現有客戶測試不同的選件。身為行銷人員，您可以與目前未驗證的客戶測試這些廣告，瞭解哪些優惠能獲得最大的回應。

根據縮寫驗證來觸及使用者的規則範例為：

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Expanded targeting {#expanded-targeting}

除了有助於觸及特定客戶的規則外，行銷人員還需要增加可供目標鎖定的資料集大小的規則。[!UICONTROL Profile Merge Rules] 可讓您使用裝置描述檔選項來執行此動作。裝置選項可將資料集的符合範圍擴展至區段，因為它們可在使用者在一或多個裝置上匿名狀態時實現。當您嘗試透過家用裝置圖表或家用裝置圖表，透過家用裝置或所有裝置觸及使用者時，這可能會很有用。此選項的使用案例可能包括廣告系列度假方案。在這種情況下，如果任何裝置上的使用者對選件顯示興趣，您將會想要觸及該選件中的每個裝置。

To create a rule that expands the targeting data set, select the **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Graph]** rule.

<!-- 

<p>Rules that use the device graph option extend your data set even further. With the device graph option, <span class="keyword"> Audience Manager</span> relies on the device profiles aggregated from the last 3 devices that a visitor used for authentication to your site. The device graph rules include: </p> 
<p> 
 <ul id="ul_3008B6AF16EC408F98EC4088111281FB"> 
  <li id="li_FA2087F1ED454CD0B9E09656B79ED23B"> <b><span class="uicontrol"> Current Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
  <li id="li_001A8DB517CB4EE394DBD530F2080FD5"> <b><span class="uicontrol"> Last Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
 </ul> </p> 
<p> 
 <note type="tip">
  Create a simple rule with 
  <b><span class="uicontrol"> No Authenticated Profile</span></b> + 
  <b><span class="uicontrol"> Current Device Profile</span></b> when you're still developing a strategy and are unsure about which options to choose or if your site doesn't use authentication. 
 </note> </p>

 -->

## Device Graph Options {#device-graph-options}

Choosing a [!UICONTROL device graph] option for a [!UICONTROL Profile Merge] rule depends on conditions unique to your digital properties and business goals. 這些一般指引可協助您瞭解何時使用一種圖表。Note, you must be a member of the [!DNL Adobe Experience Cloud Device Co-op] or have a contractual relationship with an external device graph to use these options. 請參閱下表以取得選擇裝置圖表選項的一般指引。For specific use cases, see [Profile Link Device Graph Use Cases](../../features/profile-merge-rules/profile-link-use-case.md) and [External Device Graph Use Cases](../../features/profile-merge-rules/external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置圖表類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 個人資料連結</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 使用</span><span class="wintitle"> 描述檔連結</span> 選項建立的設定檔合併規則最適合： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高階客戶驗證的數位屬性。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">集中、低觸及的宣傳活動。<span class="wintitle"> 描述檔連結</span> 裝置圖表僅建立在決定性資料之上。這個裝置設定檔存放區會比未驗證的使用者和裝置存放區小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">客戶必須處於已驗證狀態才能獲得分段的使用案例。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部裝置圖表選項 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 使用Experience</span> Cloud Device <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Co-op</a> 或與 <span class="keyword"> Audience Manager</span> 整合的任何外部裝置圖形建立的設定檔合併規則最適合： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有低階客戶驗證的數位屬性。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">廣泛、高觸及品牌宣傳活動。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">客戶不需要處於驗證狀態以符合分段資格的使用案例。 </li> 
     </ul> </p> <p> <p>Tip: The <span class="keyword"> Device Co-op</span> is your best option if you're a <span class="keyword"> Experience Cloud</span> customer with low authentication and no relationship with any device graph provider. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_贊_ this]
>
>* [描述檔連結裝置圖表使用案例](../../features/profile-merge-rules/profile-link-use-case.md)
>* [外接式裝置圖表使用案例](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [個人檔案合併規則常見問答集](../../faq/faq-profile-merge.md)

