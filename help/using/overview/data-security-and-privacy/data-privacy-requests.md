---
description: 本文件說明與 Audience Manager 資料隱私權法規遵循相關的技術細節。
seo-description: This document covers the technicalities related to data privacy regulations compliance for Audience Manager.
seo-title: Data Privacy Requests
solution: Audience Manager
keywords: GDPR UI、GDPR API、CCPA、隱私權
title: 資料隱私權請求
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
source-git-commit: 6b43885deddb0cdaeb3698051ea110f0a4eed44e
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 42%

---

# 資料隱私權請求 {#data-privacy-requests}

## 概述 {#overview}

本檔案概述如何管理您可透過[!DNL Audience Manager]Privacy Service UI[和](https://privacyui.cloud.adobe.io/)傳送給&#x200B;**[!DNL Privacy Service API]**&#x200B;的個別資料隱私權和選擇退出請求。

這些工具可讓您傳送在[!DNL GDPR]和[!DNL CCPA]下提出的消費者資料隱私權請求。

閱讀本文之前，建議您先閱讀 [GDPR 字彙表](../data-security-and-privacy/aam-gdpr-glossary.md)和[CCPA 字彙表](aam-ccpa-glossary.md)，更明確瞭解文中使用的術語。

您可以透過兩種方式提交個別請求，以從[!DNL Audience Manager]存取和刪除消費者資料：

* 透過 [Privacy Service UI](https://privacyui.cloud.adobe.io/)。請參閱[此處](https://docs.adobe.com/content/help/zh-Hant/experience-platform/privacy/home.translate.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)的文件。
* 透過 **[!DNL Privacy Service API]**。請參閱檔案[這裡](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hant)和[!DNL API]參考[這裡](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)。

傳送個人資料隱私權請求時，如[!DNL Audience Manager]Audience Manager識別碼&#x200B;**[一節所述，您可以提交任何](data-privacy-ids.md)**&#x200B;識別碼(ID)，以及其各自的名稱空間ID （資料來源ID）。

[Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hant) 支援兩種請求：資料存取和資料刪除請求。

## 資料存取請求 {#access-data}

您可以透過[Privacy Service UI](https://privacyui.cloud.adobe.io) （檔案[這裡](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=zh-Hant)）或呼叫Privacy Service API （檔案[這裡](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hant)和[!DNL API]參考[這裡](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)）來傳送個別資料存取請求。

[Privacy Service UI](https://privacyui.cloud.adobe.io/) 可讓您使用 [!UICONTROL Request Builder] 或上傳 [!DNL JSON] 檔案來建立新的工作請求。

若要查看有效的 [!DNL JSON] 檔案看起來是什麼樣子，您可以[下載範例 JSON](../data-security-and-privacy/assets/access_request.json)。

我們瞭解您承諾在法規所規範的期限內履行資料隱私權請求。

## 資料刪除請求 {#delete-data}

您可以透過[Privacy Service UI](https://privacyui.cloud.adobe.io) （檔案[在此](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=zh-Hant)）或呼叫Privacy Service API （檔案[在此](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hant)和[!DNL API]參考[在此](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)）傳送資料刪除請求。

[Privacy Service UI](https://privacyui.cloud.adobe.io/) 可讓您使用 [!UICONTROL Request Builder] 或上傳 [!DNL JSON] 檔案來建立新的工作請求。

若要查看有效的 [!DNL JSON] 檔案看起來是什麼樣子，您可以[下載範例 JSON](../data-security-and-privacy/assets/access_request.json)。

Adobe 瞭解您承諾會在 30 天內履行資料隱私權客戶請求。因此，[!DNL Adobe]已承諾儘快處理您的資料刪除請求。

回應您的消費者資料刪除請求，[!DNL Audience Manager]會刪除與請求中包含的[!DNL Audience Manager]識別碼相關的特徵和區段。 此外，個人已選擇[!DNL Audience Manager]退出進一步的資料收集，其個別[!DNL Audience Manager]識別碼與個別ID對應將會移除。

當您在資料隱私權請求中傳送宣告ID （例如跨裝置[!DNL CRM] ID或[!DNL cookie] ID）時，[!DNL Audience Manager]將在所有連結的裝置上執行必要的刪除（每個宣告ID最多100部裝置）。

[!DNL Audience Manager]會嘗試將資料主體請求刪除特定資料的取消細分資訊傳送給啟用合作夥伴，通知對方該刪除請求。 不過，有些啟用合作夥伴：

1. 無法支援來自[!DNL Audience Manager]的取消細分（或移除區段）請求，和/或
2. 無法以低於30天的頻率接收來自[!DNL Audience Manager]的更新。 在這些情況下，[!DNL Audience Manager]客戶無法透過[!DNL Audience Manager]以自動執行方式傳送刪除請求給啟用合作夥伴。

在這些情況下，您無法透過[!DNL Audience Manager]以自動執行方式傳送刪除請求給啟用合作夥伴。

請參閱我們的[以裝置為基礎的目的地清單檔案](assets/AAM-Partners-October2019.xlsx)，瞭解哪些[!DNL Audience Manager]啟用合作夥伴支援取消細分。

## 選擇退出請求 {#opt-out-requests}

[!DNL Audience Manager]支援有關選擇退出管理的業界標準。 請閱讀下文，瞭解[!DNL Audience Manager]支援的選擇退出型別的完整資訊。

雖然資料存取和刪除請求是透過[Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hant)處理，但目前是透過[!DNL DCS API]支援選擇退出請求。 請閱讀下文，瞭解選擇退出[!DNL API]呼叫看起來是什麼樣子。

### 全域選擇退出請求

全域選擇退出代表針對所有品牌選擇退出[!DNL Audience Manager]及其他[!DNL Adobe Experience Cloud]解決方案。 下表列出用於全域選擇退出的方法：

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要選擇退出的產品 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p><a href="https://www.adobe.com/tw/privacy/opt-out.html" format="http" scope="external">「您的隱私權選擇」頁面</a>提供一鍵式功能，可讓您的一般使用者控制和選擇退出 Adobe Experience Cloud 廣告解決方案 (包括 Audience Manager) 的資料收集。具體說明請參閱「隱私權選擇」頁面上的<a href="https://www.adobe.com/tw/privacy/opt-out.html" format="http" scope="external">企業客戶區段</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>向 Audience Manager 發出直接 API 呼叫 </p> </td> 
   <td colname="col2"> <p>您的使用者可以呼叫以下 DCS API，並加入 <a href="../../reference/ids-in-aam.md"> Audience Manager 使用者 ID </a>，以此方式選擇退出所有 Audience Manager 品牌的資料收集： </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>如此一來，我們會為已提交的 Audience Manager 使用者 ID 設定 <code>demdex=NOTARGET</code> 和 <code>dextp=NOTARGET</code> Cookie。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行動裝置 </p> </td> 
   <td colname="col2"> <p>請參閱以下裝置適用的選擇退出與隱私權設定： </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html?lang=zh-Hant" format="https" scope="external"> Android 裝置 </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html?lang=zh-Hant" format="https" scope="external"> iOS 裝置 </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

您的使用者也可以造訪我們業界標準合作夥伴的網站，選擇退出全域資料收集。

* [數位廣告聯盟 (DAA)](https://optout.aboutads.info/?c=2#! /)；
* [網路廣告聯盟 (NAI)](https://optout.networkadvertising.org/?c=1#! /)。

依上述方式處理選擇退出請求後：

* 只要使用者沒有清除其瀏覽器Cookie，[!DNL Audience Manager]就會停止所有資料收集、細分或啟用。
* 120 天後，歷史資料會從使用者設定檔中移除。

### 使用宣告 ID 呼叫的合作夥伴層級選擇退出

合作夥伴層級的選擇退出可讓您選擇退出特定[!DNL Audience Manager]合作夥伴的資料收集。 您可以針對跨裝置ID （包括[!DNL CRM] ID和雜湊電子郵件地址），傳送合作夥伴層級的選擇退出請求。

使用宣告 ID 呼叫執行合作夥伴層級選擇退出後：

* [CRM ID](../../reference/ids-in-aam.md) 會退出資料收集；
* 連結至 [CRM ID](../../reference/ids-in-aam.md) 的最後一個裝置 ID ([Audience Manager 不重複使用者 ID](../../reference/ids-in-aam.md)) 會退出資料收集。
* [!DNL Audience Manager]將對[!DNL CRM] ID和連結至[!DNL CRM] ID的最後一個裝置ID停止所有資料收集、細分或啟用；
* [!DNL Audience Manager]從所有區段中取消選擇退出的[!DNL CRM] ID和最後一個裝置ID的區段；
* [!UICONTROL Destination]合作夥伴會收到[!DNL CRM] ID和最後一個裝置ID的取消細分請求。 取消細分功能適用於[即時](data-privacy-requests.md#aam-partners-with-unsegmentation)和批次目的地。
* 系統不會刪除歷史資料。

當[!DNL Audience Manager]收到合作夥伴層級的選擇退出要求時，[!DNL JSON]傳回的[!DNL DCS]會包含[錯誤碼171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)，並包含訊息[!UICONTROL "Encountered opt out tag"]，而非[!DNL Audience Manager]使用者識別碼。

您可以使用 `d_cid` 和 `d_cid_ic` 索引鍵值配對，提出宣告 ID 選擇退出請求。舊版參數 (例如 `d_dpid` 和 `d_dpuuid`) 仍然有效，但被視為已過時。請參閱 [CID 取代 DPID 及 DPUUID](../../reference/cid.md)。在這些範例中，*斜體字*&#x200B;代表變數預留位置。

#### 透過[!DNL CID]和[!DNL CID_IC]選擇退出

如需說明和語法，請參閱 [URL 變數和宣告 ID 的語法](../../features/declared-ids.md#variables-and-syntax)。

| 使用以下項目執行選擇退出 | 程式碼範例 |
|--- |--- |
| 資料提供者 ID 和使用者 ID。 | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 整合程式碼和使用者 ID。 | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| 多個`d_cid`和`d_cid_ic`機碼值組。 | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### 使用裝置 ID 呼叫執行合作夥伴層級選擇退出

合作夥伴層級的選擇退出可讓您選擇退出特定[!DNL Audience Manager]合作夥伴的資料收集。 您可以藉由對 [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) 發出下列呼叫，選擇讓指定裝置 ID 退出某個品牌的資料收集：

| 使用以下項目執行選擇退出 | 程式碼範例 |
|--- |--- |
| [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`)。 | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

如需深入瞭解，請參閱 `uuid`、`mid`以及 [Audience Manager 內的 ID 索引](/help/using/reference/ids-in-aam.md)中的 `imsOrgId`。

使用裝置 ID 呼叫執行合作夥伴層級選擇退出後：

* 裝置 ID 會退出資料收集。
* [!DNL Audience Manager]將針對該裝置ID停止該合作夥伴的所有資料收集、細分或啟用。
* [!DNL Audience Manager]從所有區段中取消細分裝置ID；
* 目的地合作夥伴會收到該裝置 ID 的取消細分請求。取消細分功能適用於[即時](data-privacy-requests.md#aam-partners-with-unsegmentation)和批次目的地。
* 系統不會刪除歷史資料。

## [!DNL Audience Manager]個具有取消細分功能的合作夥伴 {#aam-partners-with-unsegmentation}

為了協助您自動處理消費者資料隱私權請求，[!DNL Audience Manager]會嘗試將取消細分（或移除區段）資訊傳送給啟用合作夥伴，通知對方資料主體提出刪除請求。

然而，有部分啟用合作夥伴：

1. 無法支援來自[!DNL Audience Manager]的取消細分請求，和/或
2. 無法以30天內多於一次的頻率接收來自[!DNL Audience Manager]的更新。

在這些情況下，您無法透過[!DNL Audience Manager]以自動執行方式傳送刪除請求給啟用合作夥伴。

請參閱[以裝置為基礎的目的地清單](/help/using/features/destinations/device-based-destinations-list.md)，瞭解哪些[!DNL Audience Manager]啟用合作夥伴支援取消細分。

## 資料更正請求 {#correction}

鑑於[!DNL Audience Manager]不是資料來源，[!DNL Audience Manager]中的資料更正角色有限。 更正可能表示消費者已要求取消不正確的[!UICONTROL trait]/[!UICONTROL segment]的資格，或符合所需[!UICONTROL trait]/[!UICONTROL segment]的資格。

[!DNL Audience Manager]客戶可選擇對使用者設定檔擷取相關的訊號/特徵/區段，並透過[離線資料擷取](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)將此資訊傳送至[!DNL Audience Manager]。 請注意，如果使用者重複原來的行為，將會繼續符合原始[!UICONTROL trait]和[!UICONTROL segments]的資格。
