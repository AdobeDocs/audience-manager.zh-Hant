---
description: 在 Audience Manager 可啟用 Audience Optimization for Publishers 之前，請務必確認您已符合本文所述的所有必要條件。確認符合所有必要條件之後，請聯絡客戶服務人員。
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import Google Ad Manager Data Files Into Audience Manager
solution: Audience Manager
title: 將GoogleAd Manager資料檔案導入Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
source-git-commit: 7147091e6c253e8124f5f21a2251c1a76ac9d808
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 13%

---

# 將GoogleAd Manager（以前叫DFP）資料檔案導入Audience Manager{#import-dfp-data-files-into-audience-manager}

在 Audience Manager 可啟用 Audience Optimization for Publishers 之前，請務必確認您已符合本文所述的所有必要條件。確認符合所有必要條件之後，請聯絡客戶服務人員。

## GoogleAd Manager日誌接收的先決條件 {#prereqs-dfp-ingestion}

請注意，此部分中描述的過程必須完成 *先* 您將轉到啟用日誌攝取的先決條件。

為了使用 [!DNL Google Ad Manager] (以前稱為GoogleDFP)日誌檔案 [!DNL Audience Manager]你必須先把 [Audience Manager唯一用戶ID(UUID)](../../../reference/ids-in-aam.md) 在廣告標籤呼叫中。 通過執行此操作，我們的ID將包含在 [!DNL Google Ad Manager] 日誌，我們可以匹配 [!DNL Google Ad Manager] 和 [!DNL Audience Manager]。 使用 [!DNL Audience Manager] [!UICONTROL DIL] 代碼或 [!UICONTROL Audience Management Module] 設定 [!DNL Audience Manager] 第一方cookie中的UUID。

下面是如何設定 [!DNL Audience Manager] 廣告標籤呼叫中的ID，如我們的文檔所述：

* [通過Google發佈者標籤(GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [通過Cookie目標](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

您需要設定 [!DNL Audience Manager] 自我確認，可以 [!DNL Audience Manager] 咨詢一下，檢查一切是否正常。 您已設定 [!DNL Audience Manager] 如果：

* `'aamid'` 是用作標識符的鍵。
* 用戶ID值的格式正確， [!DNL Audience Manager] UUID，如 [Audience Manager中ID的索引](../../../reference/ids-in-aam.md)。
* 您已包括 [!DNL Audience Manager] 在定義的欄位中的UUID [!DNL Google Ad Manager] 日誌（例如，自定義目標）。

## 啟用日誌接收的先決條件 {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>確認設定 <span class="keyword"> Audience Manager</span> UUID（上面概述）在轉到步驟2之前已完成 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> 客戶服務或咨詢 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 2 </p> </td> 
   <td colname="col2"> <p>您的Google廣告管理員建立： </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">用於插入GoogleAd Manager登錄的服務帳戶 <span class="keyword"> Audience Manager</span>。 </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">新憑據。 <p>注：這可能需要特定於此項目的唯一電子郵件地址，並且在設定對Google儲存桶的訪問時將使用該地址。 </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">私鑰（基於JSON的憑據） </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>您的Google廣告經理管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 3 </p> </td> 
   <td colname="col2"> <p>您的GoogleAd Manager管理員授予對服務帳戶的API訪問權限。 此步驟允許訪問元資料以定義維（行項、訂單、建立）。 <p>注：使用您在步驟2中設定的服務帳戶電子郵件訪問權限授予訪問API的權限。 </p> </p> </td> 
   <td colname="col3"> <p>您的Google廣告經理管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 4 </p> </td> 
   <td colname="col2"> <p>您的Google廣告經理管理員建立對Google儲存桶的訪問權限。 記住： </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">這可以通過Google集團來完成。 </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">將分配給服務帳戶的唯一電子郵件地址與儲存儲存桶關聯。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>您的Google廣告經理管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 5 </p> </td> 
   <td colname="col2"> <p>您的GoogleAd Manager管理員提供GoogleAd Manager網路ID。 這允許我們在調用API時傳入網路ID。 </p> </td> 
   <td colname="col3"> <p>您的Google廣告經理管理員 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>步驟 6 </p> </td> 
   <td colname="col2"> <p>按照詳細說明編譯先決條件並開啟支援票證 <a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html">這裡</a> 啟動日誌攝取過程。 </p> </td> 
   <td colname="col3"> <p>你 <span class="keyword"> Audience Manager</span> 代表您咨詢 </p> </td> 
  </tr> 
 </tbody> 
</table>
