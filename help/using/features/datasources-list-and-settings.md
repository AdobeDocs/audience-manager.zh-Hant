---
description: 查看當前配置的資料源清單，添加新資料源，並編輯現有源。
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: 資料來源清單與設定
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 2%

---

# [!UICONTROL Data Sources] 清單和設定 {#data-sources-list-and-settings}

查看當前配置的清單 [!UICONTROL data sources]添加新 [!UICONTROL data sources]，編輯現有 [!UICONTROL data sources]。

您還可以管理 [!UICONTROL data sources] 使用 [!DNL API] 的雙曲餘切值。 有關詳細資訊，請參見 [資料源API方法](../api/rest-api-main/aam-api-data-sources.md)。

## [!UICONTROL Data Sources] 清單檢視 {#list-view}

的 [!UICONTROL Data Sources] 儀表板是用於管理資料源的集中式工作區。

的 [!UICONTROL Data Sources] 儀表板&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**)包含幫助您的功能和工具：

* 查看所有現有 [!UICONTROL data sources]，包括每個資料源的說明、狀態以及是否 [!UICONTROL Inbound]。 [!UICONTROL Outbound]，兩者或 [!UICONTROL Shared Provider]。
* 搜索 [!UICONTROL data sources] 姓名。
* 建立、編輯和刪除 [!UICONTROL data sources]。

## [!DNL Data Source] 設定和菜單選項 {#settings-menu-options}

中不同部分中的設定 [!UICONTROL Data Source] 管理介面可以識別 [!DNL data source]，確定其使用或共用方式，並啟用錯誤報告 [!UICONTROL Onboarding Status Report]。

## [!DNL Data Source] 詳細資料 {#details}

除文本欄位外， [!UICONTROL Data Source Details] 的子菜單。

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 菜單選項 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID 類型</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>:標識設備的cookie ID。 當資料源是Web瀏覽器或使用不能與單個人關聯的匿名資料或資料時，您會選擇此選項。 </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> 設備廣告ID</span></b>:移動設備標識符。 當資料源是移動設備或啟用Internet的設備時，選擇此選項。 </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> 交叉設備</span></b>:客戶提供的經驗證的ID。 在要建立時選擇此選項： 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">跨設備資料源和構建 <span class="wintitle"> 配置檔案合併規則</span>。 </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">使用由 <a href="https://experienceleague.adobe.com/docs/device-co-op/using/about/overview.html" format="https" scope="external"> Adobe Experience Cloud設備合作</a> 或與之整合的第三方設備圖 <span class="keyword"> Audience Manager</span>。 </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID定義</span></b> </p> </td> 
   <td colname="col2"> <p>的 <b><span class="uicontrol"> ID定義</span></b> 選項定義資料源與 <span class="keyword"> Audience Manager</span> 用戶ID(UUID)和關聯設備 <span class="keyword"> Adobe Experience Cloud設備合作</span> 或與之整合的第三方設備圖 <span class="keyword"> Audience Manager</span>。 選項包括: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> 人員：</span></b> 用於定義單個人員的ID。 此ID可以映射到多個 <span class="keyword"> Audience Manager</span> ID。 </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> 家庭：</span></b> 用於定義一組人員的ID。 此ID可以映射到多個Audience ManagerID。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[資料導出控制項](../features/data-export-controls.md) 是可應用於的可選分類規則 [!UICONTROL data source] 和 [!UICONTROL destination]。 它們阻止您向 [!UICONTROL destination] 當該操作違反資料隱私或使用協定時。 如果您不使用 [!UICONTROL Data Export Controls]。

>[!IMPORTANT]
>
>除非您在 [!UICONTROL destination]。

選項包括:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] 設定 {#data-source-settings}

的 [!UICONTROL Data Source Settings] 包含下面列出的控制項和選項。 其中一些設定具有附加的子選項和菜單項，您可以選擇這些子選項和菜單項來修改資料源。

### [!UICONTROL Inbound Data Source] 設定

選擇 **[!UICONTROL Inbound]** 複選框。 選擇 **[!UICONTROL Inbound]** 複選框顯示下面描述的2組附加控制項。

>[!NOTE]
>
>的 **[!UICONTROL Inbound]** 複選框僅用於顯示或隱藏 [!UICONTROL data source] 下面介紹的控制項。 取消檢查 **[!UICONTROL Inbound]** 選項不會以任何方式影響資料接收。 無論選中此選項，都將處理您的已掛接資料。

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 設定 </th> 
   <th colname="col2" class="entry"> 菜單選項 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID 類型</span></b> </p> </td> 
   <td colname="col2"> <p>的 <b><span class="uicontrol"> 入站</span></b> 選項需要ID類型。 選項包括: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> 客戶ID</span></b>:標識具有客戶ID的入站資料。 </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience ManagerID</span></b>:標識具有 <span class="keyword"> Audience Manager</span> ID。 </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience CloudID</span></b>:標識具有 <span class="keyword"> Experience Cloud</span> ID。 請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Experience CloudID</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 檔案格式疑難解答</span></b> </p> </td> 
   <td colname="col2"> <p>選擇 <b><span class="uicontrol"> 啟用檔案錯誤採樣</span></b> 需要解決入站檔案處理的問題。 此功能將生成一個錯誤示例報告，其中顯示檔案格式和語法錯誤。 </p> <p>請參閱 <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> 入門狀態報告：關於</a> 的子菜單。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他 [!UICONTROL Data Source] 設定

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
   <td colname="col2"> <p>資料源將資料發送到目標。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已啟用共用</span></b> </p> </td> 
   <td colname="col2"> <p>您的資料源可以與其他合作夥伴共用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 用作已驗證的配置檔案</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨設備資料源包含已驗證的ID。 已驗證ID已收集並同步到 <span class="keyword"> Audience Manager</span> 驗證事件期間的ID（例如，用戶登錄現場、應用內等）。 已驗證的ID可用於儲存此ID的其他源的板載資料。 它還可用於連結中的多個設備ID <span class="wintitle"> 配置檔案連結</span>。 </p> <p>此選項顯示一個文本欄位，該欄位允許您使用別名更名資料源。 如果使用別名，則此新名稱將覆蓋資料源名稱，並顯示在 <span class="wintitle"> 已驗證的配置檔案選項</span> 當 <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> 建立配置檔案合併規則</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 用作設備圖</span></b> </p> </td> 
   <td colname="col2"> <p>建立資料源作為設備圖形，您可以向其他 <span class="keyword"> Audience Manager</span> 客戶。 在選擇此選項之前，請使用 <span class="keyword"> Audience Manager</span> 顧問 <span class="wintitle"> 資料源</span> 應該與共用。 您的顧問必須通過我們的內部流程為這些公司提供資源。 </p> <p>此選項顯示一個文本欄位，該欄位允許您使用別名更名資料源。 如果使用別名，則此新名稱將覆蓋資料源名稱，並顯示在 <span class="wintitle"> 設備選項</span> 當 <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> 建立配置檔案合併規則</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 與特定Audience Manager客戶共用關聯的訪問者或設備ID</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨設備資料源包含來自設備圖形的ID。 設備圖形是映射到一個或多個ID的集合 <span class="keyword"> Audience Manager</span> 群集的ID。 此集群通常代表個人或更大的家庭群體。 僅對列為「資料提供程式」的帳戶可用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 跨Audience Manager平台共用關聯的訪問者或設備ID</span></b> </p> </td> 
   <td colname="col2"> <p>您的資料源包含可以跨其他共用的訪問者或設備ID <span class="keyword"> Experience Cloud</span> 解決方案。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 非活動客戶ID的資料保留</span></b> </p> </td> 
   <td colname="col2"> <p>允許您設定非活動客戶ID的資料保留期。 這將確定Audience Manager在上次在Audience Manager平台上看到客戶ID後，將客戶ID保留在資料庫中的時間。</p> <p>預設值為24個月（720天）。 您可以設定的最小值為1個月，最大值為5年。 注意，我們把所有月份都算為30天。</p> <p>Audience Manager根據您為非活動客戶ID設定的資料保留期，每週運行一次刪除非活動客戶ID的流程。</p> <p>Audience Manager根據您為非活動客戶ID設定的資料保留期，每週運行一次刪除非活動客戶ID的流程。</p> <p><b>注釋</b>:此控制項僅適用於跨設備資料源。 另請參見 <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> 建立跨設備資料源 </a>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 獨特特性整合代碼</span></b> </p> </td> 
   <td colname="col2"> <p>要強制使用同一資料源中的兩個特徵不具有相同的整合代碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 唯一段整合代碼</span></b> </p> </td> 
   <td colname="col2"> <p>要強制使用同一資料源中的兩個段不具有相同的整合代碼。 </p> </td> 
  </tr>
 </tbody>
</table>
