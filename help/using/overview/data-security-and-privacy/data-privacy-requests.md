---
description: 本文件說明與 Audience Manager 資料隱私權法規遵循相關的技術細節。
seo-description: 本文件說明與 Audience Manager 資料隱私權法規遵循相關的技術細節。
seo-title: 資料隱私權請求
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA，隱私權
title: 資料隱私權請求
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: 資料控管與隱私權
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 61%

---

# 資料隱私權請求 {#data-privacy-requests}

## 概述 {#overview}

本檔案概述如何管理個人資料隱私權和選擇退出請求，您可透過[Privacy ServiceUI](https://privacyui.cloud.adobe.io/)和&#x200B;**[!DNL Privacy Service API]**&#x200B;將這些請求傳送至[!DNL Audience Manager]。

這些工具可讓您傳送在[!DNL GDPR]和[!DNL CCPA]下提出的消費者資料隱私權請求。

閱讀本文之前，建議您先閱讀 [GDPR 字彙表](../data-security-and-privacy/aam-gdpr-glossary.md)和[CCPA 字彙表](aam-ccpa-glossary.md)，更明確瞭解文中使用的術語。

您可以以兩種方式提交個別請求，以從[!DNL Audience Manager]存取和刪除消費者資料：

* 透過 [Privacy Service UI](https://privacyui.cloud.adobe.io/)。請參閱[此處](https://docs.adobe.com/content/help/zh-Hant/experience-platform/privacy/home.translate.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)的文件。
* 透過 **[!DNL Privacy Service API]**。請參閱檔案[here](https://docs.adobe.com/content/help/zh-Hant/experience-platform/privacy/home.translate.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)和[!DNL API]參考[here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)。

傳送個別資料隱私權請求時，如&#x200B;**[Audience Manager識別碼](data-privacy-ids.md)**&#x200B;一節所述，您可以提交任何[!DNL Audience Manager]識別碼(ID)，及其各自的命名空間ID（資料來源ID）。

[Privacy Service](https://docs.adobe.com/content/help/zh-Hant/experience-platform/privacy/home.translate.html) 支援兩種請求：資料存取和資料刪除請求。

## 資料存取請求 {#access-data}

您可以透過[Privacy ServiceUI](https://privacyui.cloud.adobe.io)（說明檔案[此處](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)），或呼叫Privacy ServiceAPI（說明檔案[此處](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)及[!DNL API]參考[此處](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)），傳送個別資料存取請求。

[Privacy Service UI](https://privacyui.cloud.adobe.io/) 可讓您使用 [!UICONTROL Request Builder] 或上傳 [!DNL JSON] 檔案來建立新的工作請求。

若要查看有效的 [!DNL JSON] 檔案看起來是什麼樣子，您可以[下載範例 JSON](../data-security-and-privacy/assets/access_request.json)。

我們瞭解您承諾在法規所規範的期限內履行資料隱私權請求。

## 資料刪除請求 {#delete-data}

您可以透過[Privacy ServiceUI](https://privacyui.cloud.adobe.io)（說明檔案[here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)）或呼叫Privacy ServiceAPI（說明檔案[here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)及[!DNL API]參考[here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)）來傳送資料刪除請求。

[Privacy Service UI](https://privacyui.cloud.adobe.io/) 可讓您使用 [!UICONTROL Request Builder] 或上傳 [!DNL JSON] 檔案來建立新的工作請求。

若要查看有效的 [!DNL JSON] 檔案看起來是什麼樣子，您可以[下載範例 JSON](../data-security-and-privacy/assets/access_request.json)。

Adobe 瞭解您承諾會在 30 天內履行資料隱私權客戶請求。因此，[!DNL Adobe]承諾會盡快處理您的資料刪除請求。

為了回應您的消費者資料刪除請求，[!DNL Audience Manager]會刪除與請求中包含之[!DNL Audience Manager]識別碼相關聯的特徵和區段。 此外，將移除該個人選擇退出[!DNL Audience Manager]的進一步資料收集的個別[!DNL Audience Manager]識別碼，以及各自的ID對應。

您在資料隱私權請求中傳送宣告 ID (例如跨裝置 [!DNL CRM] ID 或 ID) 時， 會對所有連結的裝置執行必要的刪除 (每個宣告 ID 最多 100 部裝置)。[!DNL cookie][!DNL Audience Manager]

[!DNL Audience Manager] 會嘗試將資料主體請求刪除特定資料的取消細分資訊傳送給啟用合作夥伴，通知對方該刪除請求。不過，有些啟用合作夥伴：

1. 無法支援[!DNL Audience Manager]和/或的取消細分（或移除區段）請求
2. 無法以少於30天的頻率從[!DNL Audience Manager]接收更新。 在這些情況下，[!DNL Audience Manager]客戶無法透過[!DNL Audience Manager]以自動方式傳送刪除請求給啟用合作夥伴。

在這些情況下，您無法透過[!DNL Audience Manager]以自動方式傳送刪除請求給啟用合作夥伴。

請下載[合作夥伴 Excel 工作表](assets/AAM-Partners-October2019.xlsx)，瞭解哪些 啟用合作夥伴支援取消細分。[!DNL Audience Manager]

## 選擇退出請求 {#opt-out-requests}

[!DNL Audience Manager] 支援有關選擇退出管理的業界標準。請閱讀以了解[!DNL Audience Manager]所支援選擇退出類型的完整資訊。

雖然資料存取和刪除請求是透過 [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 處理，但目前是透過 [!DNL DCS API] 支援選擇退出請求。請閱讀以了解選擇退出[!DNL API]呼叫看起來是什麼樣子。

### 全域選擇退出請求

全域選擇退出代表所有品牌在[!DNL Audience Manager]和其他[!DNL Adobe Experience Cloud]解決方案中的選擇退出。 下表列出用於全域選擇退出的方法：

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
   <td colname="col2"> <p><a href="https://www.adobe.com/tw/privacy/opt-out.html" format="http" scope="external">「您的隱私權選擇」頁面</a>提供一鍵式功能，可讓您的一般使用者控制和選擇退出 Adobe Experience Cloud 廣告解決方案 (包括 Audience Manager) 的資料收集。具體說明請參閱「隱私權選擇」頁面上的<a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external">企業客戶區段</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>向 Audience Manager 發出直接 API 呼叫 </p> </td> 
   <td colname="col2"> <p>您的使用者可以呼叫以下 DCS API，並加入 <a href="../../reference/ids-in-aam.md"> Audience Manager 使用者 ID </a>，以此方式選擇退出所有 Audience Manager 品牌的資料收集： </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>如此一來，我們會為已提交的 Audience Manager 使用者 ID 設定 <code>demdex=NOTARGET</code> 和 <code>dextp=NOTARGET</code> Cookie。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行動裝置 </p> </td> 
   <td colname="col2"> <p>請參閱以下裝置適用的選擇退出與隱私權設定： </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/zh-Hant/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android 裝置 </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/zh-Hant/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS 裝置 </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

您的使用者也可以造訪我們業界標準合作夥伴的網站，選擇退出全域資料收集。

* [數位廣告聯盟 (DAA)](https://optout.aboutads.info/?c=2#! /)；
* [網路廣告聯盟 (NAI)](https://optout.networkadvertising.org/?c=1#! /)。

依上述方式處理選擇退出請求後：

* [!DNL Audience Manager]只要使用者沒有清除其瀏覽器 Cookie， 就會停止所有資料收集、細分或啟用。
* 120 天後，歷史資料會從使用者設定檔中移除。

### 使用宣告 ID 呼叫的合作夥伴層級選擇退出

合作夥伴層級的選擇退出可讓您選擇讓您的使用者退出特定[!DNL Audience Manager]合作夥伴的資料收集。 您可以傳送跨裝置ID（包括[!DNL CRM] ID和雜湊電子郵件地址）的合作夥伴層級選擇退出請求。

使用宣告 ID 呼叫執行合作夥伴層級選擇退出後：

* [CRM ID](../../reference/ids-in-aam.md) 會退出資料收集；
* 連結至 [CRM ID](../../reference/ids-in-aam.md) 的最後一個裝置 ID ([Audience Manager 不重複使用者 ID](../../reference/ids-in-aam.md)) 會退出資料收集。
* [!DNL Audience Manager] 將對 ID 和連結至 ID 的最後一個裝置 ID 停止所有資料收集、細分或啟用；[!DNL CRM][!DNL CRM]
* [!DNL Audience Manager] 從所有區段中取消選 [!DNL CRM] 擇退出的ID和最後一個裝置ID的區段；
* [!UICONTROL Destination] 合作夥伴會收到ID和最後一個 [!DNL CRM] 裝置ID的取消細分請求。取消細分功能適用於[即時](data-privacy-requests.md#aam-partners-with-unsegmentation)和批次目的地。
* 系統不會刪除歷史資料。

當[!DNL Audience Manager]收到合作夥伴級別的選擇退出請求時，[!DNL DCS]返回的[!DNL JSON]包含[錯誤代碼171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)，其中包含消息[!UICONTROL "Encountered opt out tag"]，而不是[!DNL Audience Manager]用戶ID。

您可以使用 `d_cid` 和 `d_cid_ic` 索引鍵值配對，提出宣告 ID 選擇退出請求。舊版參數 (例如 `d_dpid` 和 `d_dpuuid`) 仍然有效，但被視為已過時。請參閱 [CID 取代 DPID 及 DPUUID](../../reference/cid.md)。在這些範例中，*斜體字*&#x200B;代表變數預留位置。

#### 使用[!DNL CID]和[!DNL CID_IC]選擇退出

如需說明和語法，請參閱 [URL 變數和宣告 ID 的語法](../../features/declared-ids.md#variables-and-syntax)。

| 使用以下項目執行選擇退出 | 程式碼範例 |
|--- |--- |
| 資料提供者 ID 和使用者 ID。 | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 整合程式碼和使用者 ID。 | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| 多個`d_cid`和`d_cid_ic`鍵值配對。 | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### 使用裝置 ID 呼叫執行合作夥伴層級選擇退出

合作夥伴層級的選擇退出可讓您選擇讓您的使用者退出特定[!DNL Audience Manager]合作夥伴的資料收集。 您可以藉由對 [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) 發出下列呼叫，選擇讓指定裝置 ID 退出某個品牌的資料收集：

| 使用以下項目執行選擇退出 | 程式碼範例 |
|--- |--- |
| [!DNL Audience Manager] [!DNL Unique User ID](`uuid`)。 | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| [!DNL Experience Cloud] ID(`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

如需深入瞭解，請參閱 `uuid`、`mid`以及 [Audience Manager 內的 ID 索引](/help/using/reference/ids-in-aam.md)中的 `imsOrgId`。

使用裝置 ID 呼叫執行合作夥伴層級選擇退出後：

* 裝置 ID 會退出資料收集。
* [!DNL Audience Manager] 往後會針對該裝置 ID 停止該合作夥伴的所有資料收集、細分或啟用。
* [!DNL Audience Manager] 從所有區段中取消區段裝置ID;
* 目的地合作夥伴會收到該裝置 ID 的取消細分請求。取消細分功能適用於[即時](data-privacy-requests.md#aam-partners-with-unsegmentation)和批次目的地。
* 系統不會刪除歷史資料。

## [!DNL Audience Manager] 具有取消細分功能的合作夥伴  {#aam-partners-with-unsegmentation}

為協助您自動處理消費者資料隱私權請求，[!DNL Audience Manager]會嘗試將取消細分（或移除區段）資訊傳送給啟用合作夥伴，通知對方資料主體提出刪除請求。

然而，有部分啟用合作夥伴：

1. 無法支援來自[!DNL Audience Manager]和/或的取消細分請求
2. 無法以30天內超過一次的頻率接收來自[!DNL Audience Manager]的更新。

在這些情況下，您無法透過[!DNL Audience Manager]以自動方式傳送刪除請求給啟用合作夥伴。

請參閱[以裝置為基礎的目的地清單](/help/using/features/destinations/device-based-destinations-list.md)，瞭解哪些 啟用合作夥伴支援取消細分功能。[!DNL Audience Manager]

## 資料更正請求 {#correction}

由於[!DNL Audience Manager]不是資料源，因此[!DNL Audience Manager]中的資料更正作用有限。 更正可能意味著消費者已請求取消不正確的[!UICONTROL trait]/[!UICONTROL segment]的資格，或符合所需的[!UICONTROL trait]/[!UICONTROL segment]的資格。

[!DNL Audience Manager] 客戶可選擇對使用者設定檔擷取相關的訊號/特徵/區段，並透過離線資料 [擷取](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 將這些 [!DNL Audience Manager]資訊傳送至。請注意，如果使用者重複其行為，將繼續符合原始[!UICONTROL trait]和[!UICONTROL segments]的資格。
