---
description: 當Audience Manager向資料夥伴發送段資訊時，它會用數字ID標識這些對象。 作為資料合作夥伴，當您與客戶共用此資訊（或自行處理此資訊）時，實際的名稱和描述將為客戶在報告、儀表板或其他用戶介面(UI)中提供更好的體驗。 資料合作夥伴可以使用本節中介紹的手動或自動方法，為客戶提供這些友好名稱。
seo-description: When Audience Manager sends segment information to a data partner, it identifies these objects with numeric IDs. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces (UI). Data partners can make these friendly names available to their customers with either the manual or automated methods described in this section.
seo-title: Retrieving Segment Metadata
solution: Audience Manager
title: 擷取區段中繼資料
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 1%

---

# 擷取區段中繼資料 {#retrieving-segment-metadata}

當Audience Manager向資料夥伴發送段資訊時，它會用數字ID標識這些對象。 作為資料合作夥伴，當您與客戶共用此資訊（或自行處理此資訊）時，實際的名稱和描述將為客戶在報告、儀表板或其他用戶介面([!DNL UI])。 資料合作夥伴可以使用本節中介紹的手動或自動方法，為客戶提供這些友好名稱。

## 手動方法 {#manual-method}

作為資料合作夥伴，您可能已習慣於通過手動流程從客戶處獲取受眾元資料。 這可能包括附加到電子郵件或通過 [!DNL UI] 你為此建造和維護了。 這些過程是有效的，但往往繁瑣、耗時，並且可能需要手動資料輸入工作。 這些方法通常用於幫助快速啟動和運行整合，但從長期來看，它們無法提供最佳的客戶體驗。 作為替代方法，您可以 [!DNL Audience Manager] [!DNL API] 自動獲取段元資料。

## 自動化方法 {#automated-method}

[!DNL Audience Manager] 提供一組 [REST API](../../api/rest-api-main/rest-api-main.md) 即可自動檢索段元資料。 使用 [!DNL API]，您可以建立按預定時間間隔檢索段元資料的作業，或者在處理 [!DNL Audience Manager] 找到新的段ID。 有關詳細資訊，請參閱以下步驟。

### 步驟1:查看Audience ManagerAPI

的 [REST API入門](../../api/rest-api-main/aam-api-getting-started.md) 部分包含有關一般要求、驗證和可用方法等的資訊。 如果你沒有和 [!DNL Audience Manager] [!DNL API] 。

### 步驟2:請求OAuth2訪問憑據

你需要一個客戶ID和密碼 [!DNL API] 呼叫。 在整合設定過程中，您可以從整合專家處獲取客戶端ID和機密。 您還可以向 [!UICONTROL Audience Manager Customer Care] 在 [!DNL amsupport@adobe.com]。

### 第3步：從每個整合的客戶收集特定於客戶的資訊

請求每個整合客戶提供以下資訊：

* 用戶名：這適用於對與特定整合關聯的目標具有只讀權限的受限用戶。
* 密碼：用戶密碼。
* 目標ID:這是與為特定伺服器到伺服器整合建立的目標關聯的ID（整數）。

### 第4步：使用API調用檢索段元資料

完成上述步驟後，可使用 `GET` 檢索段元資料的方法。 有關示例請求和響應，請參閱 [返回目標映射](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings)。 此調用返回以鍵值對格式化的段資料 [!DNL JSON] 的雙曲餘切值。 下表列出了響應中返回的某些重要段屬性。

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
   <td colname="col2"> <p>的 <span class="keyword"> Audience Manager</span> 段ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>段名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>一些簡要描述該段的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>段映射的當前狀態。 返回的狀態選項包括： </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
