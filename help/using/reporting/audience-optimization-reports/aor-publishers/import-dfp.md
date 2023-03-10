---
description: 在 Audience Manager 可啟用 Audience Optimization for Publishers 之前，請務必確認您已符合本文所述的所有必要條件。確認符合所有必要條件之後，請聯絡客戶服務人員。
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import Google Ad Manager Data Files Into Audience Manager
solution: Audience Manager
title: 將Google Ad Manager資料檔案匯入Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
source-git-commit: 7147091e6c253e8124f5f21a2251c1a76ac9d808
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 13%

---

# 將Google Ad Manager（原稱DFP）資料檔案匯入Audience Manager{#import-dfp-data-files-into-audience-manager}

在 Audience Manager 可啟用 Audience Optimization for Publishers 之前，請務必確認您已符合本文所述的所有必要條件。確認符合所有必要條件之後，請聯絡客戶服務人員。

## Google Ad Manager記錄擷取的必要條件 {#prereqs-dfp-ingestion}

請注意，必須完成本節所述的程式 *befor* 您將移至記錄擷取啟用的先決條件。

為了使用 [!DNL Google Ad Manager] (原稱Google DFP)登入的記錄檔 [!DNL Audience Manager]您必須先將 [Audience Manager不重複使用者ID(UUID)](../../../reference/ids-in-aam.md) 在廣告標籤呼叫中。 如此一來，我們的ID就會包含在 [!DNL Google Ad Manager] 記錄檔，我們可以比對 [!DNL Google Ad Manager] 和 [!DNL Audience Manager]. 使用 [!DNL Audience Manager] [!UICONTROL DIL] 代碼或 [!UICONTROL Audience Management Module] 設定 [!DNL Audience Manager] 第一方Cookie中的UUID。

以下說明如何設定 [!DNL Audience Manager] 廣告標籤呼叫中的ID，如本檔案所述：

* [透過Google發佈商標籤(GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [透過Cookie目的地](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

您必須設定 [!DNL Audience Manager] 自行識別，並可搭配 [!DNL Audience Manager] 諮詢服務，檢查一切是否正常。 您已設定 [!DNL Audience Manager] 如果：

* `'aamid'` 是用作識別碼的鍵。
* 使用者ID值的格式正確為 [!DNL Audience Manager] UUID，如 [Audience Manager中的ID索引](../../../reference/ids-in-aam.md).
* 您已將 [!DNL Audience Manager] 在 [!DNL Google Ad Manager] 記錄檔（例如自訂鎖定目標）。

## 啟用記錄擷取的必要條件 {#prereqs-ingestion-enablement}

<table id="table_C980A9F9B0FB4157B4908A64768B1571"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 步驟 </th> 
   <th colname="col2" class="entry"> 詳細資料 </th> 
   <th colname="col3" class="entry"> 擁有者 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>步驟 1 </p> </td> 
   <td colname="col2"> <p>確認設定 <span class="keyword"> Audience Manager</span> 移至步驟2之前，已完成UUID（如上所述） </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> 客戶服務或諮詢 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 2 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理員會建立： </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">擷取Google Ad Manager的服務帳戶會登入 <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">新憑據。 <p>注意：這可能需要此專案專屬的唯一電子郵件地址，且在布建Google儲存貯體的存取權時將使用。 </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">私密金鑰（以JSON為基礎的憑證） </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 3 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理員授予服務帳戶的API存取權。 此步驟可讓存取中繼資料來勾勒維度（行項目、訂單、創作）。 <p>注意：使用您在步驟2中設定的服務帳戶電子郵件存取權，授予存取API的權限。 </p> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 4 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理員建立了Google儲存貯體的存取權。 記住： </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">這可透過Google群組來完成。 </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">將指派給服務帳戶的唯一電子郵件地址與儲存貯體相關聯。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 5 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理員會提供Google Ad Manager網路ID。 這可讓我們在呼叫API時傳遞網路ID。 </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 6 </p> </td> 
   <td colname="col2"> <p>按照詳細說明編譯先決條件並開啟支援票證 <a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html">此處</a> 啟動記錄擷取程式。 </p> </td> 
   <td colname="col3"> <p>您，或 <span class="keyword"> Audience Manager</span> 代表您諮詢 </p> </td> 
  </tr> 
 </tbody> 
</table>
