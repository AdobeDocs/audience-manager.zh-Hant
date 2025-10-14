---
description: Audience Manager傳送區段資訊給資料合作夥伴時，會使用數值ID識別這些物件。 身為資料合作夥伴，當您和客戶共用這些資訊（或自行處理）時，實際的名稱和說明可在報表、儀表板或其他使用者介面(UI)中為客戶提供更佳的體驗。 資料合作夥伴可使用本節所述的手動或自動化方法，讓客戶可以使用這些易記名稱。
seo-description: When Audience Manager sends segment information to a data partner, it identifies these objects with numeric IDs. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces (UI). Data partners can make these friendly names available to their customers with either the manual or automated methods described in this section.
seo-title: Retrieving Segment Metadata
solution: Audience Manager
title: 正在擷取區段中繼資料
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# 正在擷取區段中繼資料 {#retrieving-segment-metadata}

Audience Manager傳送區段資訊給資料合作夥伴時，會使用數值ID識別這些物件。 身為資料合作夥伴，當您和客戶共用這些資訊（或自行處理）時，實際的名稱和說明可在報表、儀表板或其他使用者介面([!DNL UI])中為客戶提供更好的體驗。 資料合作夥伴可使用本節所述的手動或自動化方法，讓客戶可以使用這些易記名稱。

## 手動方法 {#manual-method}

身為資料合作夥伴，您可能習慣透過手動程式，從客戶取得對象中繼資料。 這可能包括附加到電子郵件的檔案，或是來自客戶透過您為此目的建立和維護的[!DNL UI]新增該資料的檔案。 這些程式很管用，但通常很麻煩、很耗時，並且可能需要手動輸入資料。 這些方法通常用於協助讓整合快速上線運作，但長期而言無法提供最佳客戶體驗。 另外，您可以使用[!DNL Audience Manager] [!DNL API]自動取得區段中繼資料。

## 自動化方法 {#automated-method}

[!DNL Audience Manager]提供了一組[REST API](../../api/rest-api-main/rest-api-main.md)，可讓您自動擷取區段中繼資料。 透過[!DNL API]，您可以建立以排程間隔擷取區段中繼資料的工作，或在您處理[!DNL Audience Manager]資料並尋找新區段ID時自動擷取區段中繼資料的工作。 如需詳細資訊，請參閱下列步驟。

### 步驟1：檢閱Audience Manager API

[&#x200B; REST API快速入門](../../api/rest-api-main/aam-api-getting-started.md)區段包含一般需求、驗證、可用方法等資訊。 如果您之前未使用[!DNL Audience Manager] [!DNL API]，這是一個很好的起點。

### 步驟2：要求OAuth2存取認證

您需要使用者端識別碼與密碼才能進行[!DNL API]呼叫。 在整合設定程式進行期間，您可以向整合專員取得使用者端ID和密碼。 您也可以在[!UICONTROL Audience Manager Customer Care]傳送電子郵件要求給[!DNL amsupport@adobe.com]。

### 步驟3：收集每個整合客戶的客戶特定資訊

向每個整合客戶請求下列專案：

* 使用者名稱：這適用於與特定整合相關聯的目的地具有唯讀許可權的受限制使用者。
* 密碼：使用者密碼。
* 目的地ID：這是與針對特定伺服器對伺服器整合而建立的目的地相關聯的ID （整數）。

### 步驟4：使用API呼叫擷取區段中繼資料

完成上述步驟後，您可以使用`GET`方法來擷取區段中繼資料。 如需範例要求與回應，請參閱[Return Destination Mappings](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings)。 此呼叫傳回在[!DNL JSON]物件中格式化為索引鍵值配對的區段資料。 下表列出回應中傳回的一些重要區段屬性。

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
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>區段識別碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>區段名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>簡要說明區段的一些文字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>區段對應的目前狀態。 傳回的狀態選項包括： </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
