---
description: 檢視目前設定的資料來源清單、新增資料來源，以及編輯現有來源。
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: 資料來源清單與設定
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# [!UICONTROL Data Sources]清單與設定 {#data-sources-list-and-settings}

檢視您目前設定的[!UICONTROL data sources]清單、新增新的[!UICONTROL data sources]，以及編輯現有的[!UICONTROL data sources]。

您也可以使用[!UICONTROL data sources]方法來管理[!DNL API]。 如需詳細資訊，請參閱[資料Source API方法](../api/rest-api-main/aam-api-data-sources.md)。

## [!UICONTROL Data Sources]清單檢視 {#list-view}

[!UICONTROL Data Sources]儀表板是管理資料來源的集中式工作區。

[!UICONTROL Data Sources]儀表板(**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**)包含可協助您：

* 檢視您所有現有的[!UICONTROL data sources]，包括每個資料來源的描述、狀態，以及它是[!UICONTROL Inbound]、[!UICONTROL Outbound]、兩者還是[!UICONTROL Shared Provider]。
* 依名稱搜尋[!UICONTROL data sources]。
* 建立、編輯和刪除[!UICONTROL data sources]。

## [!DNL Data Source]設定和功能表選項 {#settings-menu-options}

[!UICONTROL Data Source]管理介面不同區段中的設定可識別您的[!DNL data source]、決定如何使用或共用它，以及讓您啟用[!UICONTROL Onboarding Status Report]的錯誤報告。

## [!DNL Data Source]詳細資料 {#details}

除了文字欄位外，[!UICONTROL Data Source Details]區段還包含下列控制項和選項。

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 功能表選項 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID型別</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>：識別裝置的Cookie識別碼。 當您的資料來源為網頁瀏覽器，或使用無法與單一人員相關聯的匿名資料或資料時，您可以選取此選項。 </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol">裝置Advertising識別碼</span></b>：行動裝置識別碼。 當您的資料來源是行動裝置或啟用網際網路的裝置時，請選取此選項。 </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol">跨裝置</span></b>：客戶提供的驗證ID。 當您要建立以下專案時，請選取此選項： 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">跨裝置資料來源並建置<span class="wintitle">設定檔合併規則</span>。 </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">使用與<span class="keyword"> Audience Manager</span>整合的協力廠商裝置圖表所提供連結的資料來源。 </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID定義</span></b> </p> </td> 
   <td colname="col2"> <p><b><span class="uicontrol"> ID定義</span></b>選項會定義資料來源與<span class="keyword"> Audience Manager</span>使用者ID (UUID)以及透過與<span class="keyword"> Audience Manager</span>整合的協力廠商裝置圖表連結之相關裝置的關係。 選項包括: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol">人員：</span></b>用來定義單一人員的識別碼。 此ID可對應至多個<span class="keyword">個Audience Manager</span> ID。 </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol">家庭：</span></b>用來定義一組人員的識別碼。 此ID可對應至多個Audience Manager ID。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[資料匯出控制項](../features/data-export-controls.md)是選擇性分類規則，可套用至[!UICONTROL data source]和[!UICONTROL destination]。 當動作違反資料隱私權或使用合約時，這些動作會使您無法將資料傳送至[!UICONTROL destination]。 如果您不使用[!UICONTROL Data Export Controls]，請略過此章節。

>[!IMPORTANT]
>
>除非您在[!UICONTROL destination]上設定相符的匯出標籤，否則匯出限制將無法運作。

選項包括:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source]設定 {#data-source-settings}

[!UICONTROL Data Source Settings]包含下列的控制項和選項。 其中一些設定具有其他子選項和選單專案，您可以選取它們來修改資料來源。

### [!UICONTROL Inbound Data Source]設定

當您的資料來源設計用來接收傳入資料時，請選取&#x200B;**[!UICONTROL Inbound]**&#x200B;核取方塊。 選取&#x200B;**[!UICONTROL Inbound]**&#x200B;核取方塊會顯示下列另外兩組控制項。

>[!NOTE]
>
>**[!UICONTROL Inbound]**&#x200B;核取方塊僅用於顯示或隱藏如下所述的[!UICONTROL data source]控制項。 取消核取&#x200B;**[!UICONTROL Inbound]**&#x200B;選項並不會以任何方式影響資料擷取。 無論此選項是否勾選，系統都會處理您的已上線資料。

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 功能表選項 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID型別</span></b> </p> </td> 
   <td colname="col2"> <p><b><span class="uicontrol">輸入</span></b>選項需要ID型別。 選項包括: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol">客戶識別碼</span></b>：使用客戶識別碼識別傳入資料。 </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager ID</span></b>：識別具有<span class="keyword"> Audience Manager</span> ID的傳入資料。 </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>：識別具有<span class="keyword"> Experience Cloud</span> ID的傳入資料。 檢視<a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=zh-Hant" format="https" scope="external"> Cookie與Experience Cloud ID</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">檔案格式疑難排解</span></b> </p> </td> 
   <td colname="col2"> <p>當您需要疑難排解傳入檔案處理問題時，請選取<b><span class="uicontrol">啟用檔案錯誤取樣</span></b>。 此功能會產生錯誤範例報告，顯示檔案格式和語法錯誤。 </p> <p>請參閱<a href="../reporting/onboarding-status-report.md#onboarding-status-about">上線狀態報告：關於</a>，以取得有關錯誤報告和錯誤取樣的相關資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他[!UICONTROL Data Source]設定

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 選擇時機 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">傳出</span></b> </p> </td> 
   <td colname="col2"> <p>您的資料來源會將資料傳送至目的地。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">共用已啟用</span></b> </p> </td> 
   <td colname="col2"> <p>您的資料來源可以與其他合作夥伴共用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">用作已驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨裝置資料來源包含已驗證的ID。 已驗證的ID會收集並在驗證事件期間（例如，使用者登入網站、應用程式內等）同步至<span class="keyword">個Audience Manager</span> ID。 已驗證的ID可用於來自其他儲存此ID之來源的主機板內資料。 它也可以用來連結<span class="wintitle">設定檔連結</span>中的多個裝置ID。 </p> <p>此選項會顯示文字欄位，讓您以別名重新命名資料來源。 如果您使用別名，這個新名稱會覆寫資料來源名稱，並在您<span class="wintitle">建立設定檔合併規則</span>時顯示在<a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule">已驗證的設定檔選項</a>中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">用作裝置圖表</span></b> </p> </td> 
   <td colname="col2"> <p>建立資料來源作為裝置圖表，以供您提供給其他<span class="keyword">個Audience Manager</span>客戶。 在選取此選項之前，請告訴您的<span class="keyword"> Audience Manager</span>顧問，該<span class="wintitle">資料Source</span>應該與哪些客戶共用。 您的顧問必須透過我們的內部程式布建這些公司。 </p> <p>此選項會顯示文字欄位，讓您以別名重新命名資料來源。 如果您使用別名，這個新名稱會覆寫資料來源名稱，並在您<span class="wintitle">建立設定檔合併規則</span>時出現在<a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule">裝置選項</a>中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">與特定Audience Manager客戶共用相關聯的訪客或裝置ID</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨裝置資料來源包含來自裝置圖表的ID。 裝置圖表是一組ID，對應至一或多個<span class="keyword">個Audience Manager</span> ID至叢集。 此叢集通常代表個人或較大的家庭群組。 僅適用於列為「資料提供者」的帳戶。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">在Audience Manager平台中共用相關的訪客或裝置ID</span></b> </p> </td> 
   <td colname="col2"> <p>您的資料來源包含可在其他<span class="keyword">個Experience Cloud</span>解決方案之間共用的訪客或裝置ID。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> 非使用中客戶ID的<b><span class="uicontrol">資料保留</span></b> </p> </td> 
   <td colname="col2"> <p>可讓您設定非作用中客戶ID的資料保留期間。 這會決定Audience Manager將客戶ID在Audience Manager平台上最後一次看到後，保留在資料庫中的時間。</p> <p>預設值為24個月（720天）。 您可以設定的最小值為1個月，最大值為5年。 請注意，我們會將所有月份計為30天。</p> <p>Audience Manager會根據您為非作用中客戶ID設定的資料保留，執行每週刪除一次非作用中客戶ID的程式。</p> <p>Audience Manager會根據您為非作用中客戶ID設定的資料保留，執行每週刪除一次非作用中客戶ID的程式。</p> <p><b>注意</b>：此控制項僅適用於跨裝置資料來源。 另請參閱<a href="../features/profile-merge-rules/merge-rules-start.md#settings">建立跨裝置資料Source </a>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">個唯一特徵整合代碼</span></b> </p> </td> 
   <td colname="col2"> <p>您想要強制實施來自相同資料來源的兩個特徵沒有相同整合程式碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">唯一區段整合代碼</span></b> </p> </td> 
   <td colname="col2"> <p>您要強制來自相同資料來源的兩個區段沒有相同的整合程式碼。 </p> </td> 
  </tr>
 </tbody>
</table>
