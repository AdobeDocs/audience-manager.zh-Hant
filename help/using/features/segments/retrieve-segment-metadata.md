---
description: 當Audience manager傳送區段資訊給資料合作夥伴時，它會以數值ID識別這些物件。 身為資料合作夥伴，當您與客戶分享此資訊（或自行處理）時，實際名稱和說明會在報表、儀表板或其他使用者介面(UI)中為客戶提供更佳的體驗。 資料合作夥伴可使用本節所述的手動或自動方法，讓客戶取用這些好記名稱。
seo-description: 當Audience manager傳送區段資訊給資料合作夥伴時，它會以數值ID識別這些物件。 身為資料合作夥伴，當您與客戶分享此資訊（或自行處理）時，實際名稱和說明會在報表、儀表板或其他使用者介面(UI)中為客戶提供更佳的體驗。 資料合作夥伴可使用本節所述的手動或自動方法，讓客戶取用這些好記名稱。
seo-title: 擷取區段中繼資料
solution: Audience Manager
title: 擷取區段中繼資料
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 擷取區段中繼資料 {#retrieving-segment-metadata}

當Audience manager傳送區段資訊給資料合作夥伴時，它會以數值ID識別這些物件。 身為資料合作夥伴，當您與客戶分享此資訊（或自行處理）時，實際名稱和說明會在報表、儀表板或其他使用者介面([!DNL UI])中為客戶提供更佳的體驗。 資料合作夥伴可使用本節所述的手動或自動方法，讓客戶取用這些好記名稱。

## 手動方法 {#manual-method}

身為資料合作夥伴，您可能習慣透過手動程式從客戶取得受眾中繼資料。 這可能包括附加至電子郵件或客戶的檔案，這些檔案是透過您為此而 [!DNL UI] 建立和維護的資料新增的。 這些程式可以運作，但通常繁瑣、耗時，而且可能需要手動輸入資料。 這些方法通常有助於快速啟動和執行整合，但長期而言，它們無法提供最佳的客戶體驗。 或者，您可以使用區段中繼 [!DNL Audience Manager] 資料 [!DNL API] 自動取得區段。

## 自動化方法 {#automated-method}

[!DNL Audience Manager] 提供一組 [REST API](../../api/rest-api-main/rest-api-main.md) ，可讓您自動擷取區段中繼資料。 使用， [!DNL API]您可以建立工作，以排程間隔擷取區段中繼資料，或在您處理資料並尋找新區段ID時 [!DNL Audience Manager] 自動擷取區段中繼資料。 如需詳細資訊，請參閱下列步驟。

### 步驟1:檢視Audience Manager API

「 [REST API快速入門](../../api/rest-api-main/aam-api-getting-started.md) 」一節包含一般需求、驗證、可用方法等資訊。 如果你以前沒和他共事過，這是個好的開 [!DNL Audience Manager][!DNL API] 始。

### 步驟2:要求OAuth2存取認證

您需要用戶端ID和機密才能進行 [!DNL API] 呼叫。 在整合設定程式期間，您可以向整合專員取得用戶端ID和機密。 您也可以寄送電子郵件要求 [!UICONTROL Audience Manager Customer Care] 至 [!DNL amsupport@adobe.com]。

### 步驟3:向每個整合式客戶收集客戶專屬資訊

向每位整合式客戶要求下列事項：

* 使用者名稱：這是針對具有特定整合相關目的地唯讀權限的受限制使用者。
* 密碼：用戶密碼。
* 目標ID:這是與為特定伺服器對伺服器整合所建立之目標相關聯的ID（整數）。

### 步驟4:使用API呼叫擷取區段中繼資料

完成上述步驟後，您可以使用方法 `GET` 擷取區段中繼資料。 如需請求和回應的範例，請參閱 [回訪目標映射](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings)。 此呼叫會傳回格式化為物件中鍵值配對的區段 [!DNL JSON] 資料。 下表列出回應中傳回的部分重要區段屬性。

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> destinationMappingId</code> </p> </td> 
   <td colname="col2"> <p>Audience Manager <span class="keyword"> 區段</span> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>區段名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>一些簡要說明區段的文字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>區段對應的目前狀態。 傳回的狀態選項包括： </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> 活動</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> 非活動</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> 已刪除</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>