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
source-wordcount: '511'
ht-degree: 14%

---

# 將Google Ad Manager （前身為DFP）資料檔案匯入Audience Manager{#import-dfp-data-files-into-audience-manager}

在 Audience Manager 可啟用 Audience Optimization for Publishers 之前，請務必確認您已符合本文所述的所有必要條件。確認符合所有必要條件之後，請聯絡客戶服務人員。

## Google Ad Manager記錄擷取的先決條件 {#prereqs-dfp-ingestion}

請注意，您必須在&#x200B;*之前*&#x200B;完成本節中說明的程式，才能繼續記錄擷取啟用的先決條件。

若要在[!DNL Audience Manager]中使用[!DNL Google Ad Manager] (先前的Google DFP)記錄檔，您必須先在廣告標籤呼叫中設定我們的[Audience Manager唯一使用者ID (UUID)](../../../reference/ids-in-aam.md)。 如此一來，我們的ID就會包含在[!DNL Google Ad Manager]記錄檔中，而且我們可以比對[!DNL Google Ad Manager]與[!DNL Audience Manager]之間的ID。 使用[!DNL Audience Manager] [!UICONTROL DIL]程式碼或[!UICONTROL Audience Management Module]在第一方Cookie中設定[!DNL Audience Manager] UUID。

以下說明如何在廣告標籤呼叫中設定[!DNL Audience Manager] ID，如檔案所述：

* [透過Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [透過Cookie目的地](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

您需要自行設定[!DNL Audience Manager] ID，並可與[!DNL Audience Manager]諮詢人員合作來檢查是否一切正常。 在下列情況下，您已正確設定[!DNL Audience Manager] ID：

* `'aamid'`是用來做為識別碼的金鑰。
* 使用者ID值的格式正確為[!DNL Audience Manager] UUID，如Audience Manager](../../../reference/ids-in-aam.md)中之ID的[索引中所述。
* 您已在您[!DNL Google Ad Manager]記錄檔的已定義欄位中包含[!DNL Audience Manager] UUID （例如CustomTargeting）。

## 啟用記錄擷取的先決條件 {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>請確認設定<span class="keyword">Audience Manager</span> UUID （如上所述）的必要步驟已在移至步驟2前完成 </p> </td> 
   <td colname="col3"> <p><span class="keyword">Audience Manager</span>客戶服務或諮詢 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 2 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理員會建立： </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">用於將Google Ad Manager擷取至<span class="keyword">Audience Manager</span>的服務帳戶。 </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">新認證。 <p>注意：此專案可能需要專屬的唯一電子郵件地址，在布建Google儲存貯體的存取權時會使用此地址。 </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">私密金鑰（以JSON為基礎的認證） </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 3 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理員會授與服務帳戶的API存取權。 此步驟可讓您存取中繼資料，以描述維度（條列專案、訂單、創意）。 <p>注意：使用您在步驟2中設定的服務帳戶電子郵件存取權來授與存取API的許可權。 </p> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 4 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理員會建立Google儲存貯體的存取權。 請記住： </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">這可透過Google群組完成。 </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">將指派給服務帳戶的唯一電子郵件地址與儲存貯體建立關聯。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 5 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理員會提供Google Ad Manager網路ID。 這可讓我們在呼叫API時傳入網路ID。 </p> </td> 
   <td colname="col3"> <p>您的Google Ad Manager管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 6 </p> </td> 
   <td colname="col2"> <p>編譯先決條件並開啟支援票證，方法是依照詳細指示<a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html">這裡</a>開始記錄擷取程式。 </p> </td> 
   <td colname="col3"> <p>您或代表您<span class="keyword">Audience Manager</span>諮詢 </p> </td> 
  </tr> 
 </tbody> 
</table>
