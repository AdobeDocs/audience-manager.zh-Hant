---
description: 在 Audience Manager 可啟用 Audience Optimization for Publishers 之前，請務必確認您已符合本文所述的所有必要條件。確認符合所有必要條件之後，請聯絡客戶服務人員。
seo-description: 在 Audience Manager 可啟用 Audience Optimization for Publishers 之前，請務必確認您已符合本文所述的所有必要條件。確認符合所有必要條件之後，請聯絡客戶服務人員。
seo-title: 將Google Ad Manager資料檔案匯入Audience Manager
solution: Audience Manager
title: 將Google Ad Manager資料檔案匯入Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: 受眾最佳化報表
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 17%

---

# 將Google Ad Manager（之前稱為DFP）資料檔案匯入Audience Manager{#import-dfp-data-files-into-audience-manager}

在 Audience Manager 可啟用 Audience Optimization for Publishers 之前，請務必確認您已符合本文所述的所有必要條件。確認符合所有必要條件之後，請聯絡客戶服務人員。

## Google Ad Manager記錄擷取{#prereqs-dfp-ingestion}的先決條件

請注意，在&#x200B;*移至啟用記錄擷取的先決條件之前，本節所述的程式必須先完成*。

若要在[!DNL Audience Manager]中使用[!DNL Google Ad Manager]（先前稱為Google DFP）記錄檔，您必須先在廣告標籤呼叫中設定我們的[Audience Manager唯一使用者ID(UUID)](../../../reference/ids-in-aam.md)。 執行此動作後，我們的ID會包含在[!DNL Google Ad Manager]記錄檔中，而且我們可以比對[!DNL Google Ad Manager]和[!DNL Audience Manager]之間的ID。 使用[!DNL Audience Manager] [!UICONTROL DIL]程式碼或[!UICONTROL Audience Management Module]來設定第一方Cookie中的[!DNL Audience Manager] UUID。

以下說明如何在廣告標籤呼叫中設定[!DNL Audience Manager] ID，如我們的檔案所述：

* [透過Google Publisher標籤(GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [透過Cookie目的地](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

您必須自行設定[!DNL Audience Manager] ID，並可與[!DNL Audience Manager]諮詢服務合作，以檢查一切是否正常。 如果是：[!DNL Audience Manager]

* `'aamid'` 是用作識別碼的索引鍵。
* User ID值的格式正確為[!DNL Audience Manager] UUID，如[Audience Manager](../../../reference/ids-in-aam.md)中的ID索引中所述。
* 您已將[!DNL Audience Manager] UUID包含在[!DNL Google Ad Manager]記錄檔中的已定義欄位中（例如CustomTargeting）。

## 啟用記錄擷取的先決條件{#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>確認在移至步驟2之前，已完成設定<span class="keyword">Audience Manager</span> UUID（上述）的必要步驟 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience </span> Manager客戶服務或諮詢 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 2 </p> </td> 
   <td colname="col2"> <p>您的Google廣告管理員會建立： </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">用於接收Google廣告管理員的服務帳戶登入<span class="keyword">Audience Manager</span>。 </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">新認證。 <p>注意： 這可能需要此專案專屬的唯一電子郵件地址，並且在布建Google儲存貯體存取權時會使用。 </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">私密金鑰（以JSON為基礎的憑證） </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>您的Google廣告管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 3 </p> </td> 
   <td colname="col2"> <p>您的Google廣告管理員授與服務帳戶的API存取權。 此步驟可讓您存取中繼資料，以描述維度（行項目、訂單、創作元素）。 <p>注意： 使用您在步驟2中設定的服務帳戶電子郵件存取權，以授與存取API的權限。 </p> </p> </td> 
   <td colname="col3"> <p>您的Google廣告管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 4 </p> </td> 
   <td colname="col2"> <p>您的Google廣告管理員建立對Google儲存貯體的存取權。 記住： </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">這可以透過Google群組完成。 </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">將分配給服務帳戶的唯一電子郵件地址與儲存桶關聯。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>您的Google廣告管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 5 </p> </td> 
   <td colname="col2"> <p>您的Google Ad Manager管理員提供Google Ad Manager網路ID。 這可讓我們在呼叫API時傳入網路ID。 </p> </td> 
   <td colname="col3"> <p>您的Google廣告管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 6 </p> </td> 
   <td colname="col2"> <p>將電子郵件中的先決條件匯整至客AAM戶服務(aamsupport@adobe.com)，以開始記錄擷取程式。 使用下一節中的範本草擬電子郵件。 </p> </td> 
   <td colname="col3"> <p>您或<span class="keyword">Audience Manager</span>代表您諮詢 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 電子郵件模板{#email-template}

若要完成啟用記錄擷取，請寄電子郵件至aamsupport@adobe.com。 請使用附加的[電子郵件模板](assets/enable_dfp_ingestion.txt)。
