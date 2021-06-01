---
description: 當Audience Manager傳送區段資訊給資料合作夥伴時，會使用數值ID識別這些物件。 身為資料合作夥伴，當您與客戶共用此資訊（或由您親自處理）時，實際名稱和說明可為報表、控制面板或其他使用者介面(UI)中的客戶提供更好的體驗。 資料合作夥伴可透過本節所述的手動或自動化方法，為客戶提供這些好記的名稱。
seo-description: 當Audience Manager傳送區段資訊給資料合作夥伴時，會使用數值ID識別這些物件。 身為資料合作夥伴，當您與客戶共用此資訊（或由您親自處理）時，實際名稱和說明可為報表、控制面板或其他使用者介面(UI)中的客戶提供更好的體驗。 資料合作夥伴可透過本節所述的手動或自動化方法，為客戶提供這些好記的名稱。
seo-title: 擷取區段中繼資料
solution: Audience Manager
title: 擷取區段中繼資料
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: 區段
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 2%

---

# 擷取區段中繼資料 {#retrieving-segment-metadata}

當Audience Manager傳送區段資訊給資料合作夥伴時，會使用數值ID識別這些物件。 身為資料合作夥伴，當您與客戶共用此資訊（或由您親自處理）時，實際名稱和說明可為報表、控制面板或其他使用者介面([!DNL UI])中的客戶提供更好的體驗。 資料合作夥伴可透過本節所述的手動或自動化方法，為客戶提供這些好記的名稱。

## 手動方法{#manual-method}

身為資料合作夥伴，您可能習慣透過手動程式從客戶取得對象中繼資料。 這可能包括附加至電子郵件或來自客戶的檔案，這些檔案會透過您為此目的建立和維護的[!DNL UI]新增該資料。 這些程式可以運作，但通常繁瑣、耗時，而且可能需要手動輸入資料。 這些方法通常可協助讓整合快速啟動及執行，但長期而言無法提供最佳的客戶體驗。 或者，您也可以使用[!DNL Audience Manager] [!DNL API]自動取得區段中繼資料。

## 自動方法{#automated-method}

[!DNL Audience Manager] 提供一組REST  [API,](../../api/rest-api-main/rest-api-main.md) 可讓您自動擷取區段中繼資料。使用[!DNL API]，您可以建立作業，以排程間隔或自動擷取區段中繼資料，無論何時處理[!DNL Audience Manager]資料並尋找新的區段ID。 如需詳細資訊，請參閱下列步驟。

### 步驟1:檢閱Audience ManagerAPI

[REST API快速入門](../../api/rest-api-main/aam-api-getting-started.md)一節包含有關一般需求、驗證、可用方法等的資訊。 如果您之前未使用[!DNL Audience Manager] [!DNL API]，這是開始使用的好地方。

### 步驟2:要求OAuth2存取憑證

您需要用戶端ID和密碼才能進行[!DNL API]呼叫。 在整合設定程式期間，您可以向整合專員取得用戶端ID和機密。 您也可以在[!DNL amsupport@adobe.com]向[!UICONTROL Audience Manager Customer Care]發送電子郵件請求。

### 步驟3:從每個整合的客戶收集客戶特定資訊

向每個整合客戶要求下列事項：

* 用戶名：這適用於具有與特定整合相關聯之目的地唯讀權限的受限使用者。
* 密碼：用戶密碼。
* 目標ID:這是與為特定伺服器對伺服器整合所建立之目標相關聯的ID（整數）。

### 步驟4:使用API呼叫擷取區段中繼資料

完成上述步驟後，您可以使用`GET`方法來擷取區段中繼資料。 如需範例要求和回應，請參閱[傳回目標對應](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings)。 此呼叫會傳回[!DNL JSON]物件中以索引鍵值配對格式的區段資料。 下表列出回應中傳回的部分重要區段屬性。

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
   <td colname="col2"> <p><span class="keyword">Audience Manager</span>區段ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>區段名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>簡短說明區段的部分文字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>區段對應的目前狀態。 返回的狀態選項包括： </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
