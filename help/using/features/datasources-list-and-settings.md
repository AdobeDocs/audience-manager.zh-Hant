---
description: 檢視您目前設定之資料來源的清單、新增資料來源，以及編輯現有來源。
seo-description: 檢視您目前設定之資料來源的清單、新增資料來源，以及編輯現有來源。
seo-title: 資料來源清單與設定
solution: Audience Manager
title: 資料來源清單與設定
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
translation-type: tm+mt
source-git-commit: 6b55441c2bdde6cf2333852fd59fbe87f4e531eb
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 1%

---


# 資料來源清單與設定 {#data-sources-list-and-settings}

檢視您目前設定之資料來源的清單、新增資料來源，以及編輯現有來源。

<!-- c_datasources.xml -->

您也可以使用方法管理資料 [!DNL API] 來源。 如需詳細資訊，請參 [閱資料來源API方法](../api/rest-api-main/aam-api-data-sources.md)。

## 資料來源清單檢視 {#list-view}

控制 [!UICONTROL Data Sources] 面板是集中式工作區，用於管理資料來源。

<!-- c_datasources_list.xml -->

控制 [!UICONTROL Data Sources] 面板(**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**)包含可協助您：

* 查看您所有現有的資料來源，包括每個資料來源的說明、狀態，以及 [!UICONTROL Inbound]是 [!UICONTROL Outbound]、兩者或 [!UICONTROL Shared Provider]。
* 依名稱搜尋資料來源。
* 建立、編輯和刪除資料來源。

## 資料來源設定和功能表選項 {#settings-menu-options}

管理介面不同區段中的設 [!UICONTROL Data Source] 定會識別您的資料來源，決定資料來源的使用或共用方式，並讓您為啟用錯誤報告 [!UICONTROL Onboarding Status Report]。

## 資料來源詳細資料 {#details}

<!-- datasource-settings-definitions.xml -->

除了文字欄位外，此區 [!UICONTROL Data Source Details] 段還包含下列控制項和選項。

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: 識別裝置的Cookie ID。 當您的資料來源是網頁瀏覽器，或使用匿名資料或無法與單一人員關聯的資料時，您可以選取此選項。 </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> 裝置廣告ID</span></b>: 行動裝置識別碼。 當您的資料來源是行動裝置或啟用網際網路的裝置時，請選取此選項。 </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> 跨裝置</span></b>: 客戶提供的驗證ID。 當您要建立時，請選取此選項： 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">跨裝置資料來源，並建立描述檔 <span class="wintitle"> 合併規則</span>。 </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">使用 <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Adobe Experience Cloud Device Co-op或與</a> Audience Manager整合的其他協力廠商裝置圖表所提供的連結的資料來源 <span class="keyword"></span>。 </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID定義</span></b> </p> </td> 
   <td colname="col2"> <p>「 <b><span class="uicontrol"> ID定義</span></b> 」選項定義資料來源與 <span class="keyword"> Audience Manager</span> ID(UUID)的關係，這些關係由 <span class="keyword"></span><span class="keyword"></span>Adobe Experience Cloud Device Co-op或與Audience Manager Manager整合的第三方設備連結，或者由第三方設備連結。 選項包括: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> 人員：</span></b> 用於定義單一人員的ID。 此ID可對應至多個 <span class="keyword"> Audience Manager</span> ID。 </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> 家庭：</span></b> 用來定義人員群組的ID。 此ID可對應至多個Audience Manager ID。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 資料匯出控制 {#export-controls}

[「資料匯出控制](../features/data-export-controls.md) 」是可套用至資料來源和目的地的選用分類規則。 當該動作違反資料隱私或使用協定時，您無法將資料傳送至目的地。 如果您未使用，請略過本節 [!UICONTROL Data Export Controls]。

>[!IMPORTANT]
>
>除非您在目標上設定相符的匯出標籤，否則匯出限制將無法運作。

選項包括:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

包含 [!UICONTROL Data Source Settings] 下列的控制項和選項。 其中有些設定有其他子選項和功能表項目，您可以選取這些項目來修改資料來源。

### 傳入資料來源設定

選擇數 **[!UICONTROL Inbound]** 據源設計為接收入站資料時的複選框。 選取核取方 **[!UICONTROL Inbound]** 塊可顯示下列說明的2組其他控制項。

>[!NOTE]
>
>此核 **[!UICONTROL Inbound]** 取方塊僅用於顯示或隱藏下述資料來源控制項。 取消勾選 **[!UICONTROL Inbound]** 選項不會以任何方式影響資料擷取。 無論勾選此選項，您已登入的資料都會受到處理。

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
   <td colname="col2"> <p>「入 <b><span class="uicontrol"> 站</span></b> 」選項需要ID類型。 選項包括: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> 客戶ID</span></b>: 使用客戶ID識別傳入資料。 </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager ID</span></b>: 使用 <span class="keyword"> Audience Manager</span> ID識別傳入資料。 </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: 使用 <span class="keyword"> Experience Cloud</span> ID識別傳入資料。 See <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 檔案格式疑難排解</span></b> </p> </td> 
   <td colname="col2"> <p>當您需要 <b><span class="uicontrol"> 疑難排解傳入檔案處理的問題時</span></b> ，請選取「啟用檔案錯誤取樣」。 此功能會產生錯誤範例報表，顯示檔案格式和語法錯誤。 </p> <p>請參 <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> 閱入門狀態報表： 關於</a> ，以取得有關錯誤報告和錯誤取樣的資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他資料來源設定

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 選擇時間 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 出站</span></b> </p> </td> 
   <td colname="col2"> <p>您的資料來源會將資料傳送至目的地。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 共用已啟用</span></b> </p> </td> 
   <td colname="col2"> <p>您的資料來源可與其他合作夥伴共用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 用作已驗證的設定檔</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨裝置資料來源包含已驗證的ID。 在驗證事件（例如，使用者登入網站、應用程式內等）期間，會收集已驗證的ID並同步至 <span class="keyword"> Audience Manager</span> ID。 已驗證ID可用於儲存此ID之其他來源的板載資料。 它也可用於在描述檔連結中連結多個 <span class="wintitle"> 裝置ID</span>。 </p> <p>此選項會顯示一個文本欄位，該欄位允許您使用別名更名資料源。 如果您使用別名，此新名稱會覆寫資料來源名稱，並在您建立「描述檔合併」規則時 <span class="wintitle"> ，出現在「已驗證的描述檔選項</span><a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> 」中</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 用作裝置圖表</span></b> </p> </td> 
   <td colname="col2"> <p>建立資料來源作為裝置圖形，您可以提供給其他 <span class="keyword"> Audience Manager</span> 客戶。 在您選取此選項之前，請先向 <span class="keyword"> Audience Manager</span> 顧問告知應與哪些 <span class="wintitle"> 客戶共用此資料來源</span> 。 您的顧問必須透過我們的內部流程為這些公司提供服務。 </p> <p>此選項會顯示一個文本欄位，該欄位允許您使用別名更名資料源。 如果您使用別名，此新名稱會覆寫資料來源名稱，並在您建立描述檔合併規則時出現在 <span class="wintitle"> 「裝置選項</span><a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> 」中</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 與特定Audience Manager客戶共用相關訪客或裝置ID</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨裝置資料來源包含來自裝置圖表的ID。 裝置圖表是映射至叢集的一或多個 <span class="keyword"> Audience Manager</span> ID的ID集合。 這個群體通常代表一個或更大的家庭群體。 僅適用於列為「資料提供者」的帳戶。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 在Audience Manager平台上共用相關訪客或裝置ID</span></b> </p> </td> 
   <td colname="col2"> <p>您的資料來源包含可在其他 <span class="keyword"> Experience Cloud解決方案間共用的訪客或裝</span> 置ID。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 非活動客戶ID的資料保留</span></b> </p> </td> 
   <td colname="col2"> <p>允許您為非活動客戶ID設定資料保留期。 這會決定客戶ID上次在Audience Manager平台上顯示後，Audience Manager在我們的資料庫中保留多久的時間。</p> <p>預設值為24個月（720天）。 您可設定的最小值為1個月，最大值為5年。 請注意，我們會將所有月份計算為30天。</p> <p>Audience Manager會根據您為非作用中客戶ID設定的資料保留率，執行每週刪除非作用中客戶ID一次的程式。</p> <p>Audience Manager會根據您為非作用中客戶ID設定的資料保留率，執行每週刪除非作用中客戶ID一次的程式。</p> <p><b>注意</b>: 此控制項僅適用於跨裝置資料來源。 另請參閱 <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> 建立跨裝置資料來源 </a>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 獨特特徵整合代碼</span></b> </p> </td> 
   <td colname="col2"> <p>您想要從相同的資料來源強制執行這兩個特徵時，沒有相同的整合代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 唯一區段整合代碼</span></b> </p> </td> 
   <td colname="col2"> <p>您想要從同一個資料來源強制這兩個區段沒有相同的整合代碼。 </p> </td> 
  </tr>
 </tbody>
</table>
