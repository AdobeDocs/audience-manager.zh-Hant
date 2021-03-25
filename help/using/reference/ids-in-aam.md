---
description: 請參閱本檔案以取得Adobe Audience ManagerID的完整清單。
keywords: DPID;DPUUID;CID;UUID;uid;uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuid
seo-description: 請參閱本檔案以取得Adobe Audience ManagerID的完整清單。
seo-title: Audience Manager 內的 ID 索引
solution: Audience Manager
title: Audience Manager 內的 ID 索引
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: 參考
translation-type: tm+mt
source-git-commit: 348881dd2f880ca50140dbe5935cff138944003e
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 5%

---


# [!DNL Audience Manager] {#index-of-ids-in-audience-manager}中ID的索引

## 概述 {#overview}

[!DNL Audience Manager] 使用多個ID來識別並管理您傳送給它的資料。有關[!DNL Audience Manager] ID的完整清單，請參閱本文，以及您應搭配使用的字首範例。

## ID前置詞{#prefixing}

雖然您可以透過其獨立名稱來參考這些ID中的大部分，但在透過[!DNL DCS]呼叫傳入資料時，其中大部份的ID應用於各種字首。 其中有些ID由[!DNL Audience Manager]使用，但不會暴露給使用者，而其他ID也會顯示在使用者介面(UI)中。

要瞭解以下示例中使用的前置詞，請參閱[DCS API調用的支援屬性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)。

## [!DNL Audience Manager] ID 清單 {#id-list}

| ID | 名稱和說明 | 使用與範例 | 使用者介面位置 |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID]，也稱為 [!UICONTROL Device ID]。[!DNL Audience Manager]與其互動的每個裝置相關聯的38位數數字裝置ID。 每當您在[!DNL Audience Manager] UI中看到提及獨特使用者時，請考慮這個ID。 Audience Manager將此ID儲存為`demdex.net`第三方網域中的[!DNL cookie]。 | 在[!DNL DCS]呼叫中，`uuid`前面有`d_`首碼。 <br>範例: `d_uuid = 07955261652886032950143702505894272138` | 建立[相似模型](../features/algorithmic-models/create-model.md)時，您可依[!UICONTROL Device ID]篩選[!DNL traits]，建立區段](../features/segments/segment-builder.md)。 [您也可以在執行[特徵的一般報表](../reporting/general-reports.md)和[特徵的趨勢報表](../reporting/trend-reports.md)時，依[!UICONTROL Device ID]篩選結果。 |
| [!DNL ImsOrgId] | [!DNL Organization ID]。這是公司在註冊[!DNL Experience Cloud]帳戶時提供的ID。 | `5DC5123F5245B1D20A490D46@AdobeOrg` | 在[!DNL Audience Manager]使用者介面中未顯示。 要瞭解如何查找公司的[!DNL Organization ID]，請閱讀[查找組織ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)。 |
| [!DNL PID] | [!DNL Partner ID]。[!DNL PID]是[!DNL Audience Manager]中的公司ID。 Audience Manager將[!DNL imsOrgId]關聯到[!DNL PID]。 | `1352` | 在[!DNL Audience Manager]使用者介面中未顯示。 |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. [!DNL Experience Cloud] ID（[!DNL ECID]，舊式縮寫[!DNL MID]或[!DNL MCID]）是從您的[!DNL Organization ID]和[!DNL Audience Manager] [!UICONTROL Unique User ID]以數學方式推導而得。 只要這些ID保持不變，為特定使用者產生右[!DNL ECID]只是數學問題。 使用相同的[!DNL Organization ID]和[!DNL Audience Manager] [!DNL UUID]，您每次都會獲得相同的[!DNL ECID]值。 您可以閱讀[Cookie和Experience CloudID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17)檔案中的[!DNL ECID]。 | `mid = 08382830887934830189014177072406221371` | 在[!DNL Audience Manager]使用者介面中未顯示。 |
| [!DNL SID] | [!UICONTROL Trait ID]。[!UICONTROL Trait ID]在[!DNL Audience Manager]環境中唯一標識[!DNL traits]。 | 在[!DNL DCS]呼叫中，`SID`前面有`d_`首碼。 <br>範例 `d_sid=289983`. | [!UICONTROL Trait ID]會指派給每個[!DNL trait]，並在使用者介面中顯示在[Traits](../features/traits/trait-details-page.md)頁面中。 |
| [!DNL SID] | [!UICONTROL Segment ID]。[!UICONTROL Segment ID]在[!DNL Audience Manager]環境中唯一標識[!DNL segments]。 | 在[!DNL DCS]呼叫中，`SID`前面有`d_`首碼。 <br>範例 `d_sid=4798574`. | [!UICONTROL Segment ID]會指派給每個[!DNL segment]，並在使用者介面中顯示在[區段](../features/segments/segment-summary-view.md)頁面中。 |
| [!DNL csegID] | [!DNL Legacy Segment ID]。此ID可唯一識別[!DNL Audience Manager]環境中的區段。 | `741232` | [!UICONTROL Legacy Segment ID]會指派給每個區段，並顯示在[區段](../features/segments/segment-summary-view.md)頁面的使用者介面中。 |
| [!DNL destID] | [!UICONTROL Destination ID]。[!UICONTROL Destination ID]在[!DNL Audience Manager]環境中唯一標識[!DNL destinations]。 ID會指派給使用者介面中的每個[!DNL destination]。 | `2523` | [!UICONTROL Destination ID]被指派給每個[!DNL destination]，並在用戶介面中顯示在[目標](../features/destinations/destinations-home.md)頁面中。 |
| [!DNL DPID] | [!UICONTROL Data Source ID] (亦稱為 [!UICONTROL Data Provider ID])。[!UICONTROL Data Source ID]是ID或[!DNL traits]的命名空間。 ID會指派給使用者介面中的每個[!DNL data source]（資料提供者）。 | 在[!DNL DCS]呼叫中，`dpid`前面有`d_`首碼。 <br>範例: `d_dpid=39217`. | [!UICONTROL Data Provider ID]會指派給每個[!DNL data source]，並在使用者介面中顯示在[資料來源](../features/datasources-list-and-settings.md)頁面中。 |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID]，也稱為 [!DNL CRM ID] 或 [!UICONTROL Cross-Device ID]。第三方ID。 這是您用來識別[!DNL CRM]系統中使用者的ID。 您可以將[!DNL DPUUIDs]與[!DNL Audience Manager] [!DNL UUIDs]同步，並且可以在ID同步過程中從不同的[!UICONTROL Data Sources]([!DNL DPIDs])同步[!DNL DPUUIDs]。 | 在[!DNL DCS]呼叫中，`dpuuid`前面有`d_`前置詞。 <br> 範例 `d_dpuuid=2132-3423vn-343fds-3432r`. | 建立[相似模型](../features/algorithmic-models/create-model.md)時，您可依[!UICONTROL Cross-Device ID]篩選[!DNL traits]，建立區段](../features/segments/segment-builder.md)。 [您也可以在執行[特徵的一般報表](../reporting/general-reports.md)和[特徵的趨勢報表](../reporting/trend-reports.md)時，依[!UICONTROL Cross-Device ID]篩選結果。 |
| [!DNL CRM ID] | 請參閱「`DPUUID`」。 | 請參閱「`DPUUID`」。 | 請參閱「`DPUUID`」。 |
| [!DNL CID]的  [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. [!DNL CID]和[!DNL CID_IC]鍵值對替換[!DNL DPID]和[!DNL DPUUID]。 它們提供與[!DNL DPID]和[!DNL DPUUID]相同的函式，但效率更高，因為它們將資料提供者ID和使用者ID（或整合程式碼）納入單一索引鍵值對。 | 在[!DNL DCS]呼叫中，這些ID前面有`d_`首碼。 <br>範例: `d_cid_ic=39217_myIntegrationCode`. | 請參閱`DPID`和`DPUUID`。 |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]。要用於廣告目的的每個硬體裝置特有的識別碼。通常由裝置或裝置作業系統的製造商提供。 | 請參閱[全域裝置ID](#global-device-ids)。 |  |

{style=&quot;table-layout:auto&quot;}

## [!DNL Global Device IDs] {#global-device-ids}

全域裝置ID是裝置廣告ID，是裝置製造商或作業系統所提供之每個裝置專屬的裝置廣告ID。 下表說明這些ID是什麼及其格式。 如需全域裝置ID的詳細資訊，以及如何在[!DNL Audience Manager]中使用這些ID，請閱讀[全域資料來源](/help/using/features/global-data-sources.md)。

| ID | [!DNL Global Data Source ID] | 名稱和說明 | 範例 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 二零九一五年 | [!DNL Identifier for Advertisers] ID是裝置製造商提供的行動裝置識別碼。這些ID代表執行[!DNL iOS]作業系統的裝置。 | 格式嚴格由32個大寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。<br> 範例: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 二零九一四年 | [!DNL Google Advertising ID]s是Android裝置製造商提供的行動裝置識別碼。這些ID代表執行[!DNL Android]作業系統的裝置。 | 格式嚴格由32個小寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 <br>範例: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 郵編：121963 | [!DNL Roku IDs for Advertising] 代表串 [!DNL Roku] 流裝置。 | 格式嚴格由32個小寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 <br>範例: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 郵編：389146 | [!DNL Microsoft Advertising ID]s是每個裝置、每 [!DNL Windows 10] 個使用者產生的裝置識別碼。 | [!DNL MAID]s的格式為英數字串。 |
| [!DNL TIFA] | 郵編：963906 | [!DNL Samsung Tizen IDs for Advertising] 是由智慧型電視提供的 [!DNL Samsung] 裝置識別碼。 | [!DNL Samsung] [!DNL TIFA] ID的格式為英數字串。 |
| [!DNL Amazon Fire TV Advertising ID] | 郵編488258 | 代表運行[!DNL Fire OS]作業系統的設備的設備標識符。 | 格式嚴格由32個小寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 <br>範例: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |