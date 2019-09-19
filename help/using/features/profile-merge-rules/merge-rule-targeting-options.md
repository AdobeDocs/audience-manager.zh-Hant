---
description: 個人檔案合併規則選項可讓您根據業務需求或目標，擴充或收緊對特定對象的關注。 這些一般使用案例會探索如何使用可用選項，並建立個人、家庭和跨裝置定位的合併規則。 目前，描述檔合併規則僅適用於即時目標。
seo-description: 個人檔案合併規則選項可讓您根據業務需求或目標，擴充或收緊對特定對象的關注。 這些一般使用案例會探索如何使用可用選項，並建立個人、家庭和跨裝置定位的合併規則。 目前，描述檔合併規則僅適用於即時目標。
seo-title: 描述檔合併規則的一般使用案例
solution: Audience Manager
title: 描述檔合併規則的一般使用案例
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 描述檔合併規則的一般使用案例 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 選項可讓您根據業務需求或目標來擴充或收緊受眾對特定受眾的關注。 這些一般使用案例會探索如何使用可用選項，並建立個人、家庭和跨裝置定位的合併規則。 目前， [!UICONTROL Profile Merge Rules] 僅能與即時目標搭配使用。

![](assets/merge-rules-options.png)

>[!TIP]
>
>有關這些設定的定義和說 [!UICONTROL Merge Rule] 明，請參 [閱定義的配置檔案合併規則選項](../../features/profile-merge-rules/merge-rule-definitions.md)。

## 目標鎖定 {#focused-targeting}

網站的使用者驗證應觸發對的宣告ID呼叫 [!DNL Audience Manager]。 在此事件後， [!DNL Audience Manager] 將特徵資料寫入（及讀取）已驗證的描述檔。 已驗證的設定檔可讓 [!DNL Audience Manager]您：

* 將特徵寫入特定使用者的已驗證描述檔。
* 識別多個裝置使用者，並區分其不同之處以進行細分。

### 觸及已驗證的使用者

已驗證的設定檔選項會建立規則，讓您根據離線屬性鎖定登入網站或應用程式的使用者。 例如，金融服務公司會使用這個選項，以根據收入或離線活動的目標信用卡升級優惠或專業服務優惠鎖定已驗證的使用者。 另一個例子是，航空公司會根據累計里程，以經認證的常客為目標。

若要建立僅觸及已驗證使用者的規則，請選取 **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**。 此選項將僅使用已驗證的描述檔資料來評估區段。 此規則會忽略匿名裝置設定檔中的資料。

若要在匿名裝置設定檔中加入資料，請使 **[!UICONTROL Current Authenticated Profile]** 用+規 **[!UICONTROL Current Device Profile]** 則。

### 根據先前的驗證狀態觸及使用者

這些選項會在特定使用者瀏覽時觸及他們，但未登入。 您可以使用依賴推斷的使用者層級定位的選項來執行此動作。 推斷的定位功能可協助您觸及未明確驗證您網站但可能正線上上瀏覽的訪客。 它的運作方式是從最後一個已驗證的描述檔讀取（但不寫入）資料。 此外，為了讓已驗證的描述檔保持乾淨， [!DNL Audience Manager] 請將新的特徵資格寫入裝置描述檔，而非已驗證的描述檔。 例如，假設您是行銷人員，想要針對未登入您網站或應用程式的現有客戶測試不同的選件。 身為行銷人員，您可以針對目前未經驗證的客戶測試這些廣告，以瞭解哪些優惠獲得最多回應。

根據預先驗證觸及使用者的規則範例為：

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## 擴充目標鎖定 {#expanded-targeting}

除了有助於觸及特定客戶的規則外，行銷人員還需要增加可用於定位的資料集大小的規則。 [!UICONTROL Profile Merge Rules] 讓您使用裝置設定檔選項來執行此動作。 裝置選項會擴充符合分段資格的資料集，因為這些資料集會根據使用者在一或多個裝置上處於匿名狀態時所實現的特性。 當您嘗試使用個人裝置圖表觸及使用者所有裝置，或是使用家庭裝置圖表觸及家庭內所有裝置時，這可能很有用。 此選項的使用案例可能包括廣告家庭度假優惠。 在這種情況下，如果任何裝置上的使用者對選件有興趣，您會希望將選件套用至家庭中的每個裝置。

若要建立可展開定位資料集的規則，請選取 **[!UICONTROL Last Authenticated Profiles]** +規 **[!UICONTROL Device Graph]** 則。

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

## 裝置圖表選項 {#device-graph-options}

選擇規 [!UICONTROL device graph] 則的選項 [!UICONTROL Profile Merge] 取決於您的數位屬性和業務目標所特有的條件。 這些一般准則可協助您瞭解何時使用一種圖形，而不是使用另一種圖形。 請注意，您必須是外部裝置圖 [!DNL Adobe Experience Cloud Device Co-op] 形的成員，或與外部裝置圖形有合約關係，才能使用這些選項。 請參閱下表，以取得有關何時選擇裝置圖形選項的一般指引。 如需特定使用案例，請參 [閱描述檔連結裝置圖表使用案例](../../features/profile-merge-rules/profile-link-use-case.md)[和外部裝置圖表使用案例](../../features/profile-merge-rules/external-graph-use-cases.md)。

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 裝置圖形類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 個人資料連結</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 使用「描述檔</span> 連結」選項建立的 <span class="wintitle"> 「描述檔合併規則</span> 」最適合： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高等級客戶驗證的數位屬性。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">專注、觸及面低的宣傳活動。 描述 <span class="wintitle"> 檔連結</span> (Profile Link)裝置圖表僅建立在確定性資料上。 相對於未驗證的用戶和設備池，此設備配置檔案池始終會更小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">客戶需要處於驗證狀態才能符合區段資格的使用案例。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部裝置圖形選項 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 使用</span> Experience Cloud Device Co-op建立描述檔合併規則 <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> ，或與</a><span class="keyword"></span> Audience Manager整合的任何外部裝置圖表，最適合： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有低級別客戶驗證的數位屬性。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">廣泛、廣泛的品牌宣傳。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">客戶不需要處於已驗證狀態才符合區段資格的使用案例。 </li> 
     </ul> </p> <p> <p>提示：如果 <span class="keyword"> 您是Experience Cloud</span><span class="keyword"></span> （低驗證率）客戶，且與任何裝置圖形提供者沒有關係，則Device Co-op是您的最佳選擇。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [描述檔連結裝置圖表使用案例](../../features/profile-merge-rules/profile-link-use-case.md)
>* [外接式裝置圖表使用案例](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [描述檔合併規則常見問答集](../../faq/faq-profile-merge.md)

