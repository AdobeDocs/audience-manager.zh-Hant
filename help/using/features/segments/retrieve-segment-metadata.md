---
description: 當Audience Manager傳送區段資訊給資料合作夥伴時，它會使用數值ID識別這些物件。作為資料合作夥伴，當您與客戶共用此資訊(或自行處理)時，實際的名稱和說明可為客戶、控制面板或其他使用者介面(UI)中的客戶提供更佳的體驗。資料合作夥伴可以使用本節所述的手動或自動化方法，將這些友好名稱提供給客戶使用。
seo-description: 當Audience Manager傳送區段資訊給資料合作夥伴時，它會使用數值ID識別這些物件。作為資料合作夥伴，當您與客戶共用此資訊(或自行處理)時，實際的名稱和說明可為客戶、控制面板或其他使用者介面(UI)中的客戶提供更佳的體驗。資料合作夥伴可以使用本節所述的手動或自動化方法，將這些友好名稱提供給客戶使用。
seo-title: 擷取區段中繼資料
solution: Audience Manager
title: 擷取區段中繼資料
uuid: 719e2c41-8878-4e8a-967a-e367421 f9 f84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Retrieving Segment Metadata {#retrieving-segment-metadata}

當Audience Manager傳送區段資訊給資料合作夥伴時，它會使用數值ID識別這些物件。As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces ([!DNL UI]). 資料合作夥伴可以使用本節所述的手動或自動化方法，將這些友好名稱提供給客戶使用。

## Manual method {#manual-method}

身為資料合作夥伴，您可能習慣透過手動流程獲取客戶的受眾中繼資料。This could include files attached to emails or from customers adding that data through a [!DNL UI] you&#39;ve built and maintained for this purpose. 這些程序運作起來很麻煩，但是通常需要耗費大量時間，而且可能需要手動輸入資料。這些方法通常用於協助整合快速運作，但在長期內並不提供最佳的客戶體驗。As an alternative, you can use the [!DNL Audience Manager] [!DNL API] to get segment metadata automatically.

## Automated method {#automated-method}

[!DNL Audience Manager] 提供一組 [REST API](../../api/rest-api-main/rest-api-main.md) ，可讓您自動擷取區段中繼資料。With the [!DNL API], you can create jobs that retrieve segment metadata at scheduled intervals or automatically, whenever you process [!DNL Audience Manager] data and find a new segment ID. 如需詳細資訊，請參閱下列步驟。

### 步驟1：檢閱Audience Manager API

The [Getting Started with REST APIs](../../api/rest-api-main/aam-api-getting-started.md) section contains information about general requirements, authentication, available methods, etc. This is a good place to begin if you haven&#39;t worked with the [!DNL Audience Manager] [!DNL API] before.

### 步驟2：要求OAuth存取憑證

You need a client ID and secret to make [!DNL API] calls. 在整合設定過程中，您可以從整合專員取得客戶ID和密碼。You can also send an email request to [!UICONTROL Audience Manager Customer Care] at [!DNL amsupport@adobe.com].

### 步驟3：收集每個整合客戶的特定客戶資訊

向每個整合客戶要求下列事項：

* 使用者名稱：這是針對具有特定整合之目標之唯讀權限的受限制使用者。
* 密碼：使用者密碼。
* 目的地ID：這是與針對特定伺服器與伺服器整合所建立之目的地相關聯的ID(整數)。

### 步驟4：使用API呼叫擷取區段中繼資料

After completing the previous steps, you can use a `GET` method to retrieve segment metadata. For a sample request and response, see [Return Destination Mappings](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). This call returns segment data formatted as key-value pairs in a [!DNL JSON] object. 下表列出回應中傳回的部分重要區段屬性。

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> destinationMappingID</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 區段ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> socialName</code> </p> </td> 
   <td colname="col2"> <p>區段名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ElementDescription</code> </p> </td> 
   <td colname="col2"> <p>一些簡短描述區段的文字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ElementStatus</code> </p> </td> 
   <td colname="col2"> <p>區段對應的目前狀態。傳回狀態選項包括： </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> active</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> 已刪除</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>