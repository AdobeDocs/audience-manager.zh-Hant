---
description: 在Audience Manager，我們是工程師，開發人員，和代碼忍者，就像你一樣。 和您一樣，我們希望能使用可靠且精確的API檔案。 因此，我們會在Swagger中重新撰寫API內容，並將其移至新位置。 這些變更的設計目的，是為了協助您改善Audience ManagerAPI程式碼的使用體驗。
seo-description: 在Audience Manager，我們是工程師，開發人員，和代碼忍者，就像你一樣。 和您一樣，我們希望能使用可靠且精確的API檔案。 因此，我們會在Swagger中重新撰寫API內容，並將其移至新位置。 這些變更的設計目的，是為了協助您改善Audience ManagerAPI程式碼的使用體驗。
seo-title: Audience Manager API 程式碼移轉
solution: Audience Manager
title: Audience Manager API 程式碼移轉
uuid: 93cc28c4-4b91-4c79-93d5-ece9bb4cc9d5
feature: API
exl-id: 081be8a7-5029-45b1-8fb1-0531d5090fe0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 6%

---

# Audience Manager API 程式碼移轉 {#audience-manager-api-code-migration}

在Audience Manager，我們是工程師，開發人員，和代碼忍者，就像你一樣。 與您一樣，我們希望使用可靠、準確的[!DNL API]文檔。 因此，我們會在[!DNL Swagger]中重新撰寫[!DNL API]內容，並將其移至新位置。 這些變更旨在協助您改善Audience Manager[!DNL API]程式碼的體驗。

## 上移{#code-migration-details}

<!-- api-swagger-migration.xml -->

[Adobe Audience Manager API檔案](https://bank.demdex.com/portal/swagger/index.html)網站是修訂後[!DNL API]內容的新首頁。 我們會嘗試在每個版本中重寫並移動幾組[!DNL API]方法。 這表示您必須同時檢查新位置和[REST API](../api/rest-api-main/rest-api-main.md)檔案，才能尋找所有可用的方法。 最終，所有公用[!DNL API]s都將位於[!DNL Audience Manager] [!DNL API]檔案網站上。 下表列出修訂和移轉的[!DNL API]s。

<!--

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API Type </th> 
   <th colname="col2" class="entry"> API Methods </th> 
  </tr> 
 </thead>
 <tbody>
 <tr> 
   <td colname="col1"> <p> <b>Algorithmic Models</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API" format="https" scope="external"> Algorithmic Models</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Marketplace</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4CFB3FAAC0B04E5AADD80E7D7FAF2722"> 
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> Data Feeds</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> Data Feed Request</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> Data Feed Finance</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> Data Feed Plans</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> Data Feed Subscriptions</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Data Source</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> Data Sources</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>Derived Signals</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> Derived Signals</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>Folders</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> Segment Folders</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> Trait Folders</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Reporting</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> Reporting</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segments</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> Segments</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> Segment Test Groups</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> Segment Test Group Draft API</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Traits</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> Traits</a> </p> </td> 
  </tr>
 </tbody>
</table>

-->


| API 類型 | API方法 |
|---------|----------|
| **[!UICONTROL Algorithmic Models**] | [演算法模型](https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API) |
| **[!UICONTROL Audience Marketplace]** | <ul><li>[資料饋送](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Buyer%20API/get_available_data_feeds_)</li><li>[資料摘要請求](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Buyer%20API/post_available_data_feeds__dataSourceId__requests)</li><li>[資料摘要財務](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Finance%20API/get_data_feeds_billing_report)</li><li>[資料摘要計畫](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Seller%20API/get_data_feeds__dataSourceId__plans_)</li><li>[資料摘要訂閱](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Seller%20API/get_data_feeds__dataSourceId__subscriptions)</li></ul> |
| **[!UICONTROL Data Sources]** | [資料來源 ](https://bank.demdex.com/portal/swagger/index.html#/Data_Source_API) |
| **[!UICONTROL Folders]** | <ul><li>[區段資料夾](https://bank.demdex.com/portal/swagger/index.html#/Segment_Folder_API)</li><li>[特徵資料夾](https://bank.demdex.com/portal/swagger/index.html#/Trait%20Folder%20API)</li></ul> |
| **[!UICONTROL Reporting]** | [報表](https://bank.demdex.com/portal/swagger/index.html#/Reporting%20API) |
| **[!UICONTROL Segments]** | <ul><li>[區段](https://bank.demdex.com/portal/swagger/index.html#/Segments%20API)</li><li>[區段測試群組](https://bank.demdex.com/portal/swagger/index.html#/Segment%20Test%20Group%20API)</li><li>[區段測試群組草稿API](https://bank.demdex.com/portal/swagger/index.html#/Segment%20Test%20Group%20API/post_segment_test_groups_drafts)</li></ul> |
| **[!UICONTROL Traits]** | [特徵](https://bank.demdex.com/portal/swagger/index.html#/Traits%20API) |
