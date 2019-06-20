---
description: 檢視目前設定的資料來源清單、新增資料來源以及編輯現有來源。
seo-description: 檢視目前設定的資料來源清單、新增資料來源以及編輯現有來源。
seo-title: 資料來源清單和設定
solution: Audience Manager
title: 資料來源清單和設定
uuid: 280a6acd-fef0-4737-a96 d-9fbc8 bfc8
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Data Sources List and Settings {#data-sources-list-and-settings}

檢視目前設定的資料來源清單、新增資料來源以及編輯現有來源。

<!-- c_datasources.xml -->

You can also manage data sources using [!DNL API] methods. For more information, see [Data Source API Methods](../api/rest-api-main/aam-api-data-sources.md).

## Data Sources List View {#list-view}

[!UICONTROL Data Sources] 控制面板是管理資料來源的集中式工作區。

<!-- c_datasources_list.xml -->

[!UICONTROL Data Sources] 控制面板(**[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**)包含可幫助您：

* See all your existing data sources, including each data source&#39;s description, status, and whether it is [!UICONTROL Inbound], [!UICONTROL Outbound], both, or a [!UICONTROL Shared Provider].
* 依名稱搜尋資料來源。
* 建立、編輯和刪除資料來源。

## Data Source Settings and Menu Options {#settings-menu-options}

[!UICONTROL Data Source] 管理介面中不同區段的設定會識別您的資料來源，判斷其使用或共用方式，並讓您啓用錯誤報告 [!UICONTROL Onboarding Status Report]。

## Data Source Details {#details}

<!-- datasource-settings-definitions.xml -->

In addition to text fields, the [!UICONTROL Data Source Details] section contains the controls and options listed below.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 功能表選項 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID 類型</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>：識別裝置的Cookie ID。當您的資料來源是網頁瀏覽器或處理無法與單一人員關聯的匿名資料或資料時，您會選取此選項。 </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> 裝置廣告ID</span></b>：行動裝置識別碼。當您的資料來源為行動裝置或啓用網際網路的裝置時，請選取此選項。 </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> 跨裝置</span></b>：客戶提供的已驗證ID。若要建立下列選項，請選取此選項： 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">A cross-device data source and build a <span class="wintitle"> Profile Merge Rule</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">A data source that uses links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID定義</span></b> </p> </td> 
   <td colname="col2"> <p><b><span class="uicontrol"> ID定義</span></b> 選項定義資料來源必須對 <span class="keyword"> Audience Manager</span> 使用者ID(UUID)和關聯的裝置(由 <span class="keyword"> Adobe Experience Cloud Device Co-op</span> 或其他與 <span class="keyword"> Audience Manager整合的協力廠商裝置圖表)所連結</span>的關係。選項包括: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> 人員：</span></b> 用來定義單一人員的ID。This ID can be mapped to multiple <span class="keyword"> Audience Manager</span> IDs. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> 家庭：</span></b> 用來定義一組人員的ID。此ID可對應至多個Audience Manager ID。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 資料匯出控制 {#export-controls}

[「資料匯出控制」](../features/data-export-controls.md) 是可選的分類規則，您可套用至資料來源和目的地。當該動作違反資料隱私權或使用合約時，就無法將資料傳送至目的地。Skip this section if you do not use [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>除非您在目的地設定相符的匯出標籤，否則匯出限制將無法運作。

選項包括:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

[!UICONTROL Data Source Settings] 其中包含下列控制項和選項。其中有些設定包含額外的子選項和功能表項目，您可選擇修改資料來源。

### 傳入資料來源設定

Select the **[!UICONTROL Inbound]** check box when your data source is designed to receive inbound data. Selecting the **[!UICONTROL Inbound]** check box exposes 2 additional groups of controls described below.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 功能表選項 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID 類型</span></b> </p> </td> 
   <td colname="col2"> <p><b><span class="uicontrol"> 「傳入</span></b> 」選項需要ID類型。選項包括: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> 客戶ID</span></b>：以客戶ID識別傳入的資料。 </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager ID</span></b>：使用 <span class="keyword"> Audience Manager</span> ID識別傳入的資料。 </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>：使用 <span class="keyword"> Experience Cloud</span> ID識別傳入的資料。See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 檔案格式疑難排解</span></b> </p> </td> 
   <td colname="col2"> <p>Select <b><span class="uicontrol"> Enable file error sampling</span></b> when you need to troubleshoot problems with inbound file processing. 此功能會產生錯誤範例報表，顯示檔案格式和語法錯誤。 </p> <p>See <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Onboarding Status Report: About</a> for information about error reporting and error sampling. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他資料來源設定

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 選取時機 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 對外輸出</span></b> </p> </td> 
   <td colname="col2"> <p>資料來源會傳送資料至目的地。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 共用已啓用</span></b> </p> </td> 
   <td colname="col2"> <p>您的資料來源可與其他合作夥伴共用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 作為驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨裝置資料來源包含已驗證的ID。An Authenticated ID is collected and synced to an <span class="keyword"> Audience Manager</span> ID during an authentication event (e.g, a user logs in on-site, in-app, etc.). 驗證ID可用於儲存此ID之其他來源的展示板資料。It can also be used to link multiple device IDs in <span class="wintitle"> Profile Link</span>. </p> <p>此選項會顯示文字欄位，讓您以別名重新命名資料來源。If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Authenticated Profile Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 當做裝置圖表使用</span></b> </p> </td> 
   <td colname="col2"> <p>Creates a data source as a device graph which you can provide to other <span class="keyword"> Audience Manager</span> customers. Before you select this option, tell with your <span class="keyword"> Audience Manager</span> consultant which customers this <span class="wintitle"> Data Source</span> should be shared with. 您的顧問必須透過我們的內部流程布建這些公司。 </p> <p>此選項會顯示文字欄位，讓您以別名重新命名資料來源。If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Device Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 與特定Audience Manager客戶共用關聯的訪客或裝置ID</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨裝置資料來源包含來自裝置圖表的ID。A device graph is a collection of IDs which map to one or more <span class="keyword"> Audience Manager</span> IDs to a cluster. 此叢集通常代表某人或大型群組。僅適用於列為「資料提供者」的帳戶。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 跨Audience Manager平台共用關聯訪客或裝置ID</span></b> </p> </td> 
   <td colname="col2"> <p>Your data source contains visitor or device IDs that can be shared across other <span class="keyword"> Experience Cloud</span> solutions. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 非活動客戶ID的資料保留</span></b> </p> </td> 
   <td colname="col2"> <p>可讓您設定非活動中客戶ID的資料保留期。這可判斷Audience Manager在Audience Manager平台上最後一次看到後，Audience Manager會保留客戶ID的時間。</p> <p>預設值為24個月(720天)。您可以設定的最小值為個月，而最大值為年。請注意，我們將所有月份計為30天。</p> <p>Audience Manager會執行一個程序，根據您為非活動客戶ID設定的資料保留，每周刪除一次非活動中客戶ID。</p> <p>Audience Manager會執行一個程序，根據您為非活動客戶ID設定的資料保留，每周刪除一次非活動中客戶ID。</p> <p><b>注意</b>：此控制項僅適用於跨裝置資料來源。See also, <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 獨特特徵整合代碼</span></b> </p> </td> 
   <td colname="col2"> <p>您想要強制來自相同資料來源的兩個特性沒有相同的整合代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 唯一區段整合代碼</span></b> </p> </td> 
   <td colname="col2"> <p>您想要強制來自相同資料來源的兩個區段沒有相同的整合代碼。 </p> </td> 
  </tr>
 </tbody>
</table>
