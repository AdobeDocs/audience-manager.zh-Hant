---
description: 本檔案涵蓋與Audience Manager資料隱私權法規遵循相關的技術細節。
seo-description: 本檔案涵蓋與Audience Manager資料隱私權法規遵循相關的技術細節。
seo-title: 資料隱私權要求
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: 資料隱私權要求
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# 資料隱私權要求 {#data-privacy-requests}

## 概述 {#overview}

本檔案提供管理個別資料隱私權和退出要求的概述，您可透過 [Privacy Service UI和](https://privacyui.cloud.adobe.io/) ，將這些要求傳送至Audience Manager **[!DNL Privacy Service API]**。

這些工具可讓您傳送根據GDPR和CCPA提出的消費者資料隱私權要求。

在閱讀本文之前，我們建議先閱讀 [GDPR辭彙表](../data-security-and-privacy/aam-gdpr-glossary.md)[和CCPA辭彙表](aam-ccpa-glossary.md)，以深入瞭解此處使用的術語。

您可以以兩種方式提交個別請求，以便從Audience Manager存取和刪除消費者資料：

* 透過隱 [私服務UI](https://privacyui.cloud.adobe.io/)。 請參閱此處的 [檔案](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)。
* 通過 **[!DNL Privacy Service API]**。 請參閱此處 [的檔案](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) ，以及API [參考](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)。

傳送個別資料隱私權要求時，您可以提交任何Audience Manager識別碼(ID)，如 **[Audience Manager識別碼區段所述](data-privacy-ids.md)**，以及其各自的命名空間ID（資料來源ID）。

隱私 [權服務](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) (Privacy Service)支援兩種請求： 資料存取和資料刪除要求。

## 資料存取請求 {#access-data}

您可以透過隱私權服務UI [(說明檔案](https://privacyui.cloud.adobe.io/)[)，或呼叫](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)( [!DNL Privacy Service API][](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)[!DNL API][](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)此處說明檔案和參考說明檔案)，傳送個別存取要求。

隱 [私服務UI](https://privacyui.cloud.adobe.io/) 允許您使用或上傳檔案來建立 [!UICONTROL Request Builder] 新的工作請 [!DNL JSON] 求。

若要查看有效檔 [!DNL JSON] 案的外觀，您可 [以下載範例JSON](../data-security-and-privacy/assets/access_request.json)。

我們瞭解您在法規所設定的期限內，遵守您的資料隱私權要求的承諾。

## 資料刪除請求{#delete-data}

您可以透過Privacy Service UI [(](https://privacyui.cloud.adobe.io/) 此處說明檔案 [)或呼叫](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)( [!DNL Privacy Service API] 此處說明檔案和 [REFERENCE API](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)[](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)here Reference)來傳送資料。

隱 [私服務UI](https://privacyui.cloud.adobe.io/) 允許您使用或上傳檔案來建立 [!UICONTROL Request Builder] 新的工作請 [!DNL JSON] 求。

若要查看有效檔 [!DNL JSON] 案的外觀，您可 [以下載範例JSON](../data-security-and-privacy/assets/access_request.json)。

Adobe瞭解您承諾在30天內履行您的資料隱私權客戶要求。 因此，Adobe承諾會盡快處理您的資料刪除要求。

回應您的消費者資料刪除請求，Audience Manager會刪除與請求中包含的Audience Manager識別碼相關的特徵和區段。 此外，個人的Audience Manager識別碼已選擇退出Audience Manager進一步收集資料，且將移除個別ID對應。

當您在資料隱私權要求中傳送宣告的ID(例如跨裝置 [!DNL CRM] ID或Cookie ID)時，Audience Manager會對所有連結的裝置執行必要的刪除（每個宣告的ID最多100個裝置）。

Audience Manager會嘗試透過傳送資料主體的取消區段資訊以要求刪除特定資料，通知啟動合作夥伴有關刪除要求。 不過，有些啟動合作夥伴：

1. 無法支援從Audience Manager和／或取消區隔（或移除區隔）請求
2. 無法從Audience Manager接收頻率低於30天的更新。 在這些情況下，Audience Manager客戶無法透過Audience Manager以自動方式傳送刪除要求給啟動合作夥伴。

在這些情況下，您無法透過Audience Manager以自動方式傳送刪除要求給啟動合作夥伴。

下載我們 [的Partner Excel表單](assets/AAM-Partners-October2019.xlsx) ，以瞭解哪些Audience Manager啟動合作夥伴支援取消細分。

## 退出請求 {#opt-out-requests}

Audience Manager支援有關退出管理的業界標準。 閱讀以取得Audience Manager支援之退出類型的完整資訊。

雖然資料存取和刪除要求是透過 [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)，但目前DCS API支援退出要求。 閱讀以瞭解退出API呼叫的外觀。

### 全域退出請求

全域退出代表所有品牌的Audience Manager和其他Adobe Experience Cloud解決方案都可選擇退出。 下表列出全域退出使用的方法：

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 退出 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>「您 <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> 的隱私權選 </a> 擇」頁面提供單鍵功能，讓您的使用者能夠控制Adobe Experience Cloud廣告解決方案（包括Audience Manager）收集和選擇退出資料。 具體而言，請參 <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> 閱「隱私權選 </a> 擇」頁面的商業客戶區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>直接API呼叫Audience Manager </p> </td> 
   <td colname="col2"> <p>您的使用者可以透過呼叫以下DCS API並加入 <a href="../../reference/ids-in-aam.md"> Audience Manager使用者ID，選擇退出所有Audience Manager品牌的資料收集 </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>因此，我們將為已提交 <code>demdex=NOTARGET</code> 的Audience Manager使 <code>dextp=NOTARGET</code> 用者ID設定和Cookie。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行動裝置 </p> </td> 
   <td colname="col2"> <p>請參閱下列的退出與隱私權設定： </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android裝置 </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS 裝置 </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

您的使用者也可以造訪我們業界標準合作夥伴的網站，選擇退出全球資料收集。

* [數位廣告聯盟(DAA)](https://optout.aboutads.info/?c=2#!/);
* [網路廣告計畫(NAI)](https://optout.networkadvertising.org/?c=1#!/)。

遵循上述的退出要求：

* 只要使用者未清除其瀏覽器Cookie,Audience Manager就會停止所有資料收集、分段或啟動。
* 120天後，歷史資料會從使用者描述檔中移除。

### 具有已宣告ID呼叫的合作夥伴層級選擇退出

合作夥伴層級的退出可讓您從特定Audience Manager合作夥伴收集的資料中選擇退出您的使用者。 您可以傳送合作夥伴層級的跨裝置ID退出要求，包括CRM ID和雜湊的電子郵件地址。

使用宣告的ID呼叫，在合作夥伴層級選擇退出後：

* [CRM ID](../../reference/ids-in-aam.md) 被選擇不收集資料；
* 連結至[CRM ID的最後一個裝置ID(](../../reference/ids-in-aam.md)Audience Manager唯一使用者ID [](../../reference/ids-in-aam.md) )已選擇退出資料收集。
* Audience Manager將停止CRM ID和最後一個連結至CRM ID的裝置ID的所有資料收集、分段或啟動；
* Audience Manager會從所有區段中取消區隔選擇退出的CRM ID和最後一個裝置ID;
* 目標合作夥伴會收到CRM ID和最後一個裝置ID的取消分段請求。 取消分段功能可同 [時適用於即時](data-privacy-requests.md#aam-partners-with-unsegmentation) 和批次目的地。
* 不會刪除歷史資料。

當Audience Manager收到合作夥伴層級的退出請求時，DCS傳回的JSON會包含錯誤碼171 [，加上訊息](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)[!UICONTROL "Encountered opt out tag"]，而非Audience Manager使用者ID。

您可以使用和金鑰值配對，提出宣告 `d_cid` 的ID `d_cid_ic` 退出要求。 舊有參數(例如 `d_dpid` 和) `d_dpuuid` 仍然有效，但被視為已過時。 請參閱 [CID 取代 DPID 及 DPUUID](../../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

#### 選擇退出CID和CID_IC

如需說明和語法，請參 [閱URL變數和Declared ID的語法](../../features/declared-ids.md#variables-and-syntax)。

| 選擇退出使用 | 程式碼範例 |
|--- |--- |
| 資料提供者ID和使用者ID。 | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 整合程式碼和使用者ID。 | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| 多個d_cid和d_cid_ic鍵值對。 | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### 使用裝置ID呼叫的合作夥伴層級選擇退出

合作夥伴層級的退出可讓您從特定Audience Manager合作夥伴收集的資料中選擇退出您的使用者。 您可以透過對 [DCS API進行下列呼叫，選擇退出品牌之指定裝置ID上的資料收集](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| 選擇退出使用 | 程式碼範例 |
|--- |--- |
| Audience Manager唯一使用者ID(`uuid`)。 | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Experience Cloud ID(`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

閱讀更多 `uuid`相關資 `mid` 訊， `imsOrgId` 以及Audience Manager [中的ID索引](/help/using/reference/ids-in-aam.md)。

透過裝置ID呼叫，在合作夥伴層級選擇退出後：

* 裝置ID已選擇退出資料收集。
* Audience Manager將停止針對合作夥伴的所有資料收集、區段或啟動，而後會針對裝置ID進行。
* Audience Manager會從所有區段中取消區隔裝置ID;
* 目標合作夥伴會收到裝置ID的取消分段要求。 取消分段功能可同 [時適用於即時](data-privacy-requests.md#aam-partners-with-unsegmentation) 和批次目的地。
* 不會刪除歷史資料。

## Audience Manager合作夥伴具備取消細分功能 {#aam-partners-with-unsegmentation}

為協助您自動化消費者資料隱私權要求，Audience Manager會嘗試透過傳送取消區段（或移除區段）資訊，通知啟動合作夥伴有關資料主體的刪除要求。

不過，我們的部分啟動合作夥伴：

1. 無法支援Audience Manager和／或的取消分段請求
2. 無法在30天內以多於一次的頻率從Audience Manager接收更新。

在這些情況下，您無法透過Audience Manager以自動方式傳送刪除要求給啟動合作夥伴。

請參閱 [裝置型目的地清單](/help/using/features/destinations/device-based-destinations-list.md) ，以瞭解哪些Audience Manager啟動合作夥伴支援取消區隔。

## 資料更正請求 {#correction}

鑑於Audience Manager不是資料來源，Audience Manager中資料修正的角色有限。 修正可能表示消費者已要求取消不正確的特徵／區段，或符合所需特徵／區段的資格。

Audience Manager客戶可選擇針對使用者個人檔案擷取相關訊號／特徵／區段，並透過離線資料擷取 [將此資訊傳送](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 至Audience Manager。 請注意，如果使用者重複其行為，將會繼續符合原始特徵和區段的資格。
