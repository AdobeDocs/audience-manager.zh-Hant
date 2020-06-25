---
description: 請參閱本檔案以取得Adobe Audience Manager ID的完整清單。
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: 請參閱本檔案以取得Adobe Audience Manager ID的完整清單。
seo-title: Audience Manager 內的 ID 索引
solution: Audience Manager
title: Audience Manager 內的 ID 索引
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 5%

---


# Index of IDs in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## 概述 {#overview}

[!DNL Audience Manager] 使用多個ID來識別並管理您傳送給它的資料。 請參閱本文以取得完整的ID [!DNL Audience Manager] 清單，以及您應搭配使用的字首範例。

## ID預檢 {#prefixing}

雖然您可以透過其獨立名稱來參考這些ID中的大部分，但大部分ID在透過呼叫傳入資料時，應與各種字首搭配使 [!DNL DCS] 用。 有些ID可供使用者使 [!DNL Audience Manager] 用，但不會暴露給使用者，而其他ID也可在使用者介面(UI)中顯示。

若要瞭解下列範例中使用的字首，請參 [閱DCS API呼叫的支援屬性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)。

## [!DNL Audience Manager] ID 清單 {#id-list}

| ID | 名稱和說明 | 使用與範例 | 使用者介面位置 |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID]，也稱為 [!UICONTROL Device ID]。 一個38位數的數值裝置ID，與它與之互 [!DNL Audience Manager] 動的每個裝置相關聯。 每當您在UI中看到提及獨特使用者時，請考慮這個 [!DNL Audience Manager] ID。 Audience Manager會將此ID儲存 [!DNL cookie] 為第 `demdex.net` 三方網域。 | 在呼 [!DNL DCS] 叫中， `uuid` 前面有前置詞 `d_` 。 <br>範例: `d_uuid = 07955261652886032950143702505894272138` | 您可以在建 [!DNL traits] 立類似 [!UICONTROL Device ID] 模型 [和建立區段時進](../features/algorithmic-models/create-model.md)行篩選 [](../features/segments/segment-builder.md)。 您也可以在執行特徵的一般報 [!UICONTROL Device ID] 表和特 [徵的趨勢報表時，](../reporting/general-reports.md) 依據篩選結果 [](../reporting/trend-reports.md)。 |
| [!DNL ImsOrgId] | [!DNL Organization ID]。這是公司在註冊帳戶時所提供的ID [!DNL Experience Cloud] 。 | `5DC5123F5245B1D20A490D46@AdobeOrg` | 使用者介面中 [!DNL Audience Manager] 不顯示。 若要瞭解如何找到您公司的資訊，請閱 [!DNL Organization ID]讀「尋 [找您的組織ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)」。 |
| [!DNL PID] | [!DNL Partner ID]。是 [!DNL PID] 公司的ID [!DNL Audience Manager]。 Audience Manager會將 [!DNL imsOrgId] 與關聯 [!DNL PID]。 | `1352` | 使用者介面中 [!DNL Audience Manager] 不顯示。 |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. ID( [!DNL Experience Cloud] 舊式縮寫[!DNL ECID]或 [!DNL MID] )是從您和的數學上 [!DNL MCID]衍生 [!DNL Organization ID][!DNL Audience Manager][!UICONTROL Unique User ID]得。 As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same [!DNL Organization ID] and [!DNL Audience Manager] [!DNL UUID] you get the same [!DNL ECID] value every time. 您可以閱讀更多有關 [!DNL ECID] Cookie和 [Experience Cloud ID檔案的資訊](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) 。 | `mid = 08382830887934830189014177072406221371` | 使用者介面中 [!DNL Audience Manager] 不顯示。 |
| [!DNL SID] | [!UICONTROL Trait ID]。在環 [!UICONTROL Trait ID] 境中唯 [!DNL traits] 一地標 [!DNL Audience Manager] 識。 | 在呼 [!DNL DCS] 叫中， `SID` 前面有前置詞 `d_` 。 <br>範例 `d_sid=289983`. | 系統會 [!UICONTROL Trait ID] 為每個特徵指 [!DNL trait]派一個，並在「特徵」頁面的使用者介面中 [顯示](../features/traits/trait-details-page.md) 。 |
| [!DNL SID] | [!UICONTROL Segment ID]。在環 [!UICONTROL Segment ID] 境中唯 [!DNL segments] 一地標 [!DNL Audience Manager] 識。 | 在呼 [!DNL DCS] 叫中， `SID` 前面有前置詞 `d_` 。 <br>範例 `d_sid=4798574`. | 系統會 [!UICONTROL Segment ID] 為每個區段指 [!DNL segment]派一個，並在「區段」頁面的使用者介面中 [顯示](../features/segments/segment-summary-view.md) 。 |
| [!DNL csegID] | [!DNL Legacy Segment ID]。此ID可唯一識別環境中的 [!DNL Audience Manager] 區段。 | `741232` | 系統會 [!UICONTROL Legacy Segment ID] 將區段指派給每個區段，並在「區段」頁面的使用者介面中 [顯示](../features/segments/segment-summary-view.md) 。 |
| [!DNL destID] | [!UICONTROL Destination ID]。在環 [!UICONTROL Destination ID] 境中唯 [!DNL destinations] 一地標 [!DNL Audience Manager] 識。 ID會指派給使用者介 [!DNL destination] 面中的每個人。 | `2523` | 系統會 [!UICONTROL Destination ID] 為每個目標指 [!DNL destination]派一個，並在「目標」頁面的使用者介面中 [顯示](../features/destinations/destinations-home.md) 。 |
| [!DNL DPID] | [!UICONTROL Data Source ID] (亦稱為 [!UICONTROL Data Provider ID])。 是 [!UICONTROL Data Source ID] ID或的命名空間 [!DNL traits]。 ID會指派給使用者介 [!DNL data source] 面中的每個（資料提供者）。 | 在呼 [!DNL DCS] 叫中， `dpid` 前面有前置詞 `d_` 。 <br>範例: `d_dpid=39217`. | 系統會 [!UICONTROL Data Provider ID] 為每個使用者 [!DNL data source]介面指派一個，並在「資料來源」頁面 [中顯示](../features/datasources-list-and-settings.md) 。 |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID]，也稱為 [!DNL CRM ID] 或 [!UICONTROL Cross-Device ID]。 第三方ID。 這是您用來識別自己系統中使用者的 [!DNL CRM] ID。 您可以與同 [!DNL DPUUIDs] 步， [!DNL Audience Manager] 也可以在ID同步 [!DNL UUIDs] 程式中從不同 [!DNL DPUUIDs] ( [!UICONTROL Data Sources][!DNL DPIDs])進行同步。 | 在呼 [!DNL DCS] 叫中， `dpuuid` 前面有前置詞 `d_` 。 <br> 範例 `d_dpuuid=2132-3423vn-343fds-3432r`. | 您可以在建 [!DNL traits] 立類似 [!UICONTROL Cross-Device ID] 模型 [和建立區段時進](../features/algorithmic-models/create-model.md)行篩選 [](../features/segments/segment-builder.md)。 您也可以在執行特徵的一般報 [!UICONTROL Cross-Device ID] 表和特 [徵的趨勢報表時，](../reporting/general-reports.md) 依據篩選結果 [](../reporting/trend-reports.md)。 |
| [!DNL CRM ID] | 請參閱「`DPUUID`」。 | 請參閱「`DPUUID`」。 | 請參閱「`DPUUID`」。 |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. 和 [!DNL CID] 鍵 [!DNL CID_IC] 值對將替換 [!DNL DPID] 和 [!DNL DPUUID]。 它們提供與和相同的功 [!DNL DPID] 能 [!DNL DPUUID]，但效率更高，因為它們在單一索引鍵值對中包含資料提供者ID和使用者ID（或整合程式碼）。 | 在呼 [!DNL DCS] 叫中，這些ID前面有首 `d_` 碼。 <br>範例: `d_cid_ic=39217_myIntegrationCode`. | 請參閱 `DPID` 和 `DPUUID`。 |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]。要用於廣告目的的每個硬體裝置特有的識別碼。通常由裝置或裝置作業系統的製造商提供。 | 請參 [閱全域裝置ID](#global-device-ids)。 |  |

## [!DNL Global Device IDs] {#global-device-ids}

全域裝置ID是裝置廣告ID，是裝置製造商或作業系統所提供之每個裝置專屬的裝置廣告ID。 下表說明這些ID是什麼及其格式。 如需全域裝置ID的詳細資訊，以及如何在中使 [!DNL Audience Manager]用，請 [閱讀全域資料來源](/help/using/features/global-data-sources.md)。

| ID | [!DNL Global Data Source ID] | 名稱和說明 | 範例 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID是裝置製造商提供的行動裝置識別碼。 這些ID代表執行作業系統 [!DNL iOS] 的裝置。 | 格式嚴格由32個大寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。<br> 範例: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s是Android裝置製造商提供的行動裝置識別碼。 這些ID代表執行作業系統 [!DNL Android] 的裝置。 | 格式嚴格由32個小寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 <br>範例: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] 代表串 [!DNL Roku] 流裝置。 | 格式嚴格由32個小寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 <br>範例: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s是每個裝置、每個 [!DNL Windows 10] 使用者產生的裝置識別碼。 | [!DNL MAID]s的格式為英數字串。 |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]s是由智慧型電視提供的裝 [!DNL Samsung] 置識別碼。 | [!DNL Samsung] [!DNL DUID]s的格式為英數字串。 |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | 代表執行作業系統之裝置的裝 [!DNL Fire OS] 置識別碼。 | 格式嚴格由32個小寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 <br>範例: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |