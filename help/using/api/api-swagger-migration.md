---
description: 在Audience Manager中，我們的工程師、開發人員和程式碼外觀就像您一樣。而且，和您一樣，我們想要使用可靠、精確的API文件。因此，我們將重新編寫Swagger中的API內容，並將它移至新位置。這些變更旨在協助改進您使用Audience Manager API程式碼的體驗。
seo-description: 在Audience Manager中，我們的工程師、開發人員和程式碼外觀就像您一樣。而且，和您一樣，我們想要使用可靠、精確的API文件。因此，我們將重新編寫Swagger中的API內容，並將它移至新位置。這些變更旨在協助改進您使用Audience Manager API程式碼的體驗。
seo-title: Audience Manager API程式碼移轉
solution: Audience Manager
title: Audience Manager API程式碼移轉
uuid: 93cc28c4-4b91-4c79-93d5-eg9 bb4 cc9 d5
translation-type: tm+mt
source-git-commit: d368699d0de9a43cb7cf2c1af64da941a811db71

---


# Audience Manager API Code Migration {#audience-manager-api-code-migration}

在Audience Manager中，我們的工程師、開發人員和程式碼外觀就像您一樣。And, like you, we want to work with reliable, accurate [!DNL API] documentation. As a result, we&#39;re re-writing our [!DNL API] content in [!DNL Swagger] and moving it to a new location. These changes are designed to help improve your experience with the Audience Manager [!DNL API] code.

## Movin&#39; On Up {#code-migration-details}

<!-- api-swagger-migration.xml -->

[Adobe Audience Manager API文件](https://bank.demdex.com/portal/swagger/index.html) 網站是我們修訂 [!DNL API] 內容的新首頁。We&#39;ll try to re-write and move a few sets of [!DNL API] methods with each release. This means you&#39;ll have to check in both the new location and the [REST API](../api/rest-api-main/rest-api-main.md) documentation to find all of the available methods. Eventually, all of the public [!DNL API]s will be on the [!DNL Audience Manager] [!DNL API] docs site. The following table lists the revised and migrated [!DNL API]s.

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API 類型 </th> 
   <th colname="col2" class="entry"> API方法 </th> 
  </tr> 
 </thead>
 <tbody>
 <tr> 
   <td colname="col1"> <p> <b>演算法模型</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API" format="https" scope="external"> 演算法模型</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>訪客交易市場</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4CFB3FAAC0B04E5AADD80E7D7FAF2722"> 
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> 資料饋送</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> 資料饋送請求</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> 資料饋送財務</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> 資料饋送計劃</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> 資料饋送訂閱</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>資料來源</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> 資料來源</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>衍生訊號</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> 衍生訊號</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>資料夾</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> 區段資料夾</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> 特徵檔案夾</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>報告</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> 報告</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>區段</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> 區段</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> 區段測試群組</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> 區段測試群組草稿API</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>特徵</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> 特徵</a> </p> </td> 
  </tr>
 </tbody>
</table>