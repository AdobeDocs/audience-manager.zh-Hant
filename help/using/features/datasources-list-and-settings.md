---
description: 檢視目前設定的資料來源清單、新增資料來源及編輯現有的來源。
seo-description: 檢視目前設定的資料來源清單、新增資料來源及編輯現有的來源。
seo-title: 資料來源清單與設定
solution: Audience Manager
title: 資料來源清單與設定
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: 資料來源
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1120'
ht-degree: 3%

---

# [!UICONTROL Data Sources] 清單與設定  {#data-sources-list-and-settings}

查看當前配置的[!UICONTROL data sources]清單，添加新[!UICONTROL data sources]，並編輯現有[!UICONTROL data sources]。

您也可以使用[!DNL API]方法管理[!UICONTROL data sources]。 如需詳細資訊，請參閱[資料來源API方法](../api/rest-api-main/aam-api-data-sources.md)。

## [!UICONTROL Data Sources] 清單檢視 {#list-view}

[!UICONTROL Data Sources]控制面板是用於管理資料來源的集中工作區。

[!UICONTROL Data Sources]控制面板(**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**)包含可協助您：

* 查看所有現有[!UICONTROL data sources]，包括每個資料源的說明、狀態，以及它是[!UICONTROL Inbound]、[!UICONTROL Outbound]、兩者還是[!UICONTROL Shared Provider]。
* 按名稱搜索[!UICONTROL data sources]。
* 建立、編輯和刪除[!UICONTROL data sources]。

## [!DNL Data Source] 設定和功能表選項  {#settings-menu-options}

[!UICONTROL Data Source]管理介面不同部分中的設定可標識您的[!DNL data source]，確定如何使用或共用，並允許您為[!UICONTROL Onboarding Status Report]啟用錯誤報告。

## [!DNL Data Source] 詳細資料 {#details}

除了文字欄位， [!UICONTROL Data Source Details]區段還包含下列控制項和選項。

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>:識別裝置的Cookie ID。當您的資料來源為網頁瀏覽器，或使用無法與單一人員相關聯的匿名資料或資料時，您可以選取此選項。 </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> 裝置廣告ID</span></b>:行動裝置識別碼。當您的資料來源為行動裝置或啟用網際網路的裝置時，請選取此選項。 </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> 跨裝置</span></b>:客戶提供的驗證ID。要建立時，請選取此選項： 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">跨裝置資料來源並建立<span class="wintitle">設定檔合併規則</span>。 </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">使用<a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a>或與<span class="keyword">Audience Manager</span>整合的其他協力廠商裝置圖表所提供的連結的資料來源。 </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID定義</span></b> </p> </td> 
   <td colname="col2"> <p><b><span class="uicontrol"> ID定義</span></b>選項定義資料源與<span class="keyword">Audience Manager</span>用戶ID(UUID)以及由<span class="keyword"> Adobe Experience Cloud Device Co-op</span>或與<span class="keyword">Audience Manager</span>整合的其他第三方設備圖形所連結的相關設備的關係。 選項包括: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> 人員：</span></b> 用於定義單一人員的ID。此ID可對應至多個<span class="keyword">Audience Manager</span> ID。 </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> 家庭： </span></b> 用來定義一組人員的ID。此ID可對應至多個Audience ManagerID。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[資料匯](../features/data-export-controls.md) 出控制是可套用至和的選用分 [!UICONTROL data source] 類規 [!UICONTROL destination]則。當動作違反資料隱私權或使用合約時，這會防止您將資料傳送至[!UICONTROL destination]。 如果不使用[!UICONTROL Data Export Controls]，請跳過此部分。

>[!IMPORTANT]
>
>除非您在[!UICONTROL destination]上設定相符的匯出標籤，否則匯出限制將無法運作。

選項包括:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] 設定 {#data-source-settings}

[!UICONTROL Data Source Settings]包含下列控制項和選項。 其中有些設定有其他子選項和菜單項，您可以選擇這些項來修改資料源。

### [!UICONTROL Inbound Data Source] 設定

當您的資料來源設計為接收入站資料時，請選取&#x200B;**[!UICONTROL Inbound]**&#x200B;核取方塊。 選取&#x200B;**[!UICONTROL Inbound]**&#x200B;核取方塊會顯示以下說明的其他2組控制項。

>[!NOTE]
>
>**[!UICONTROL Inbound]**&#x200B;核取方塊的用途僅止於顯示或隱藏以下所述的[!UICONTROL data source]控制項。 取消勾選&#x200B;**[!UICONTROL Inbound]**&#x200B;選項不會以任何方式影響資料擷取。 無論勾選此選項，已上線的資料都會經過處理。

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
   <td colname="col2"> <p><b><span class="uicontrol">入站</span></b>選項需要ID類型。 選項包括: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> 客戶ID</span></b>:使用客戶ID識別傳入資料。 </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience ManagerID</span></b>:使用Audience ManagerID識別 <span class="keyword"> 傳入</span> 資料。 </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience CloudID</span></b>:使用Experience CloudID識別 <span class="keyword"> 傳入</span> 資料。請參閱<a href="https://docs.adobe.com/content/help/zh-Hant/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Experience CloudID</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 檔案格式疑難排解</span></b> </p> </td> 
   <td colname="col2"> <p>當您需要疑難排解傳入檔案處理的問題時，請選取<b><span class="uicontrol">啟用檔案錯誤取樣</span></b>。 此功能會產生錯誤範例報表，顯示檔案格式和語法錯誤。 </p> <p>請參閱<a href="../reporting/onboarding-status-report.md#onboarding-status-about">入門狀態報表：關於</a> ，以取得關於錯誤報告和錯誤取樣的資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他[!UICONTROL Data Source]設定

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 選擇時間 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 傳出</span></b> </p> </td> 
   <td colname="col2"> <p>您的資料來源會將資料傳送至目的地。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 共用已啟用</span></b> </p> </td> 
   <td colname="col2"> <p>您的資料來源可與其他合作夥伴共用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 作為已驗證的設定檔使用</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨裝置資料來源包含已驗證的ID。 驗證ID會在驗證事件（例如使用者登入網站、應用程式內等）期間收集並同步至<span class="keyword">Audience Manager</span> ID。 已驗證ID可用於儲存此ID之其他來源的板載資料。 它也可用於在<span class="wintitle">設定檔連結</span>中連結多個裝置ID。 </p> <p>此選項會顯示一個文本欄位，該欄位允許您使用別名更名資料源。 如果您使用別名，此新名稱將覆蓋資料源名稱，並在您<a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule">建立配置檔案合併規則</a>時顯示在<span class="wintitle">已驗證配置檔案選項</span>中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 作為裝置圖表使用</span></b> </p> </td> 
   <td colname="col2"> <p>建立資料源作為設備圖表，您可以提供給其他<span class="keyword">Audience Manager</span>客戶。 在選擇此選項之前，請告訴您的<span class="keyword">Audience Manager</span>顧問應該與哪些客戶共用此<span class="wintitle">資料源</span>。 您的顧問必須透過我們的內部程式來布建這些公司。 </p> <p>此選項會顯示一個文本欄位，該欄位允許您使用別名更名資料源。 如果使用別名，則此新名稱將覆蓋資料源名稱，並在<a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule">建立配置檔案合併規則</a>時顯示在<span class="wintitle">設備選項</span>中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 與特定Audience Manager客戶共用相關的訪客或裝置ID</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨裝置資料來源包含裝置圖表的ID。 裝置圖表是ID的集合，會對應至叢集的一或多個<span class="keyword">Audience Manager</span> ID。 此群組通常代表人員或較大的家庭群組。 僅適用於列為「資料提供者」的帳戶。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 在整個Audience Manager平台上共用相關的訪客或裝置ID</span></b> </p> </td> 
   <td colname="col2"> <p>您的資料來源包含可在其他<span class="keyword">Experience Cloud</span>解決方案間共用的訪客或裝置ID。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 非作用中客戶ID的資料保留</span></b> </p> </td> 
   <td colname="col2"> <p>可讓您為非作用中的客戶ID設定資料保留期。 這決定了Audience Manager在Audience Manager平台上最後一次看到客戶ID後，將客戶ID保留在資料庫中的時間長度。</p> <p>預設值為24個月（720天）。 您可設定的最小值為1個月，最大值為5年。 請注意，我們會將所有月份計為30天。</p> <p>Audience Manager會根據您為非作用中客戶ID所設定的資料保留率，執行每週刪除非作用中客戶ID一次的程式。</p> <p>Audience Manager會根據您為非作用中客戶ID所設定的資料保留率，執行每週刪除非作用中客戶ID一次的程式。</p> <p><b>注意</b>:此控制項僅適用於跨裝置資料來源。另請參閱<a href="../features/profile-merge-rules/merge-rules-start.md#settings">建立跨裝置資料來源</a>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 唯一特徵整合代碼</span></b> </p> </td> 
   <td colname="col2"> <p>您想要從相同資料來源強制執行這兩個特徵沒有相同的整合代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 不重複區段整合代碼</span></b> </p> </td> 
   <td colname="col2"> <p>您想要從相同資料來源強制執行這兩個區段沒有相同的整合代碼。 </p> </td> 
  </tr>
 </tbody>
</table>
