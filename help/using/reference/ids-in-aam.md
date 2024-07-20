---
description: 如需Adobe Audience Manager ID的完整清單，請參閱本檔案。
keywords: DPID； DPUUID； CID； UUID； uuid； uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuid， uuuid， uuuid， uuuid， uuuid， uuuid， uuuid， uuuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Audience Manager內的ID索引
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: Reference
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
source-git-commit: e408c118870fb331c40758be8a7e6b38690aeb5f
workflow-type: tm+mt
source-wordcount: '1001'
ht-degree: 3%

---

# [!DNL Audience Manager]中ID的索引 {#index-of-ids-in-audience-manager}

## 概述 {#overview}

[!DNL Audience Manager]使用多個ID來識別和管理您傳送給它的資料。 請參閱本文章，以取得[!DNL Audience Manager] ID的完整清單，以及您應搭配使用的首碼範例。

## ID前置詞 {#prefixing}

雖然您可以透過其獨立名稱參照這些識別碼，但其中大多數識別碼旨在透過[!DNL DCS]呼叫傳入資料時搭配各種首碼使用。 這些ID中有些是由[!DNL Audience Manager]使用，但未公開給使用者，而其他則顯示在使用者介面(UI)中。

若要瞭解下列範例中使用的字首，請參閱[DCS API呼叫的支援屬性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)。

## [!DNL Audience Manager]個ID清單 {#id-list}

| ID | 名稱和說明 | 使用方式和範例 | 使用者介面位置 |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID]，也稱為[!UICONTROL Device ID]。 [!DNL Audience Manager]與其互動的每個裝置相關聯的數字38位數裝置ID。 每當您在[!DNL Audience Manager] UI中看到提及不重複使用者時，請思考此ID。 Audience Manager將此ID儲存為`demdex.net`第三方網域中的[!DNL cookie]。 | 在[!DNL DCS]個呼叫中，`uuid`的前置詞為`d_`首碼。 <br>範例: `d_uuid = 07955261652886032950143702505894272138` | 建立[相似模型](../features/algorithmic-models/create-model.md)和[建立區段](../features/segments/segment-builder.md)時，您可以依[!UICONTROL Device ID]篩選[!DNL traits]。 執行[特徵的一般報表](../reporting/general-reports.md)和[特徵的趨勢報表](../reporting/trend-reports.md)時，您也可以依[!UICONTROL Device ID]篩選結果。 |
| [!DNL ImsOrgId] | [!DNL Organization ID]。這是公司註冊[!DNL Experience Cloud]帳戶時所提供的ID。 | `5DC5123F5245B1D20A490D46@AdobeOrg` | 在[!DNL Audience Manager]使用者介面中不可見。 若要瞭解如何尋找您公司的[!DNL Organization ID]，請閱讀[尋找組織ID](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)。 |
| [!DNL PID] | [!DNL Partner ID]。[!DNL PID]是[!DNL Audience Manager]中的公司ID。 Audience Manager將[!DNL imsOrgId]與[!DNL PID]建立關聯。 | `1352` | 在[!DNL Audience Manager]使用者介面中不可見。 |
| [!DNL ECID]，[!DNL MID] | [!DNL Experience Cloud] ID。 [!DNL Experience Cloud] ID （[!DNL ECID]，舊式縮寫[!DNL MID]或[!DNL MCID]）是從您的[!DNL Organization ID]和[!DNL Audience Manager] [!UICONTROL Unique User ID]以數學方式所衍生。 只要這些ID保持不變，為特定使用者產生正確的[!DNL ECID]就只是數學問題。 使用相同的[!DNL Organization ID]和[!DNL Audience Manager] [!DNL UUID]，您每次都會獲得相同的[!DNL ECID]值。 您可以在[Cookie和Experience CloudID](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17)檔案中深入閱讀[!DNL ECID]。 | `mid = 08382830887934830189014177072406221371` | 在[!DNL Audience Manager]使用者介面中不可見。 |
| [!DNL SID] | [!UICONTROL Trait ID]。[!UICONTROL Trait ID]在[!DNL Audience Manager]環境中唯一識別[!DNL traits]。 | 在[!DNL DCS]個呼叫中，`SID`的前置詞為`d_`首碼。 <br>範例`d_sid=289983`。 | [!UICONTROL Trait ID]會指派給每個[!DNL trait]，並顯示在[特徵](../features/traits/trait-details-page.md)頁面的使用者介面中。 |
| [!DNL SID] | [!UICONTROL Segment ID]。[!UICONTROL Segment ID]在[!DNL Audience Manager]環境中唯一識別[!DNL segments]。 | 在[!DNL DCS]個呼叫中，`SID`的前置詞為`d_`首碼。 <br>範例`d_sid=4798574`。 | [!UICONTROL Segment ID]已指派給每個[!DNL segment]，並顯示在[區段](../features/segments/segment-summary-view.md)頁面的使用者介面中。 |
| [!DNL csegID] | [!DNL Legacy Segment ID]。此ID可唯一識別[!DNL Audience Manager]環境中的區段。 | `741232` | [!UICONTROL Legacy Segment ID]已指派給每個區段，且顯示在[區段](../features/segments/segment-summary-view.md)頁面的使用者介面中。 |
| [!DNL destID] | [!UICONTROL Destination ID]。[!UICONTROL Destination ID]在[!DNL Audience Manager]環境中唯一識別[!DNL destinations]。 使用者介面中的每個[!DNL destination]都會指派一個ID。 | `2523` | [!UICONTROL Destination ID]已指派給每個[!DNL destination]，並顯示在[目的地](../features/destinations/destinations-home.md)頁面的使用者介面中。 |
| [!DNL DPID] | [!UICONTROL Data Source ID] （也稱為[!UICONTROL Data Provider ID]）。 [!UICONTROL Data Source ID]是ID或[!DNL traits]的名稱空間。 使用者介面中的每個[!DNL data source] （資料提供者）都會被指派一個ID。 | 在[!DNL DCS]個呼叫中，`dpid`的前置詞為`d_`首碼。 <br>範例： `d_dpid=39217`。 | [!UICONTROL Data Provider ID]已指派給每個[!DNL data source]，並顯示在[資料來源](../features/datasources-list-and-settings.md)頁面的使用者介面中。 |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID]，也稱為[!DNL CRM ID]或[!UICONTROL Cross-Device ID]。 協力廠商ID。 這是識別您自己[!DNL CRM]系統中一般使用者的識別碼。 您可以將[!DNL DPUUIDs]與[!DNL Audience Manager] [!DNL UUIDs]同步，也可以在ID同步處理中，從您不同的[!UICONTROL Data Sources] ([!DNL DPIDs])同步[!DNL DPUUIDs]。 | 在[!DNL DCS]個呼叫中，`dpuuid`的前置詞為`d_`首碼。 <br>範例`d_dpuuid=2132-3423vn-343fds-3432r`。 | 建立[相似模型](../features/algorithmic-models/create-model.md)和[建立區段](../features/segments/segment-builder.md)時，您可以依[!UICONTROL Cross-Device ID]篩選[!DNL traits]。 執行[特徵的一般報表](../reporting/general-reports.md)和[特徵的趨勢報表](../reporting/trend-reports.md)時，您也可以依[!UICONTROL Cross-Device ID]篩選結果。 |
| [!DNL CRM ID] | 請參閱「`DPUUID`」。 | 請參閱「`DPUUID`」。 | 請參閱「`DPUUID`」。 |
| [!DNL CID]，[!DNL CID_IC] | [!UICONTROL Customer ID]，[!UICONTROL Customer ID Integration Code]。 [!DNL CID]和[!DNL CID_IC]機碼值組會取代[!DNL DPID]和[!DNL DPUUID]。 它們提供與[!DNL DPID]和[!DNL DPUUID]相同的函式，但效率較高，因為它們包含資料提供者ID和使用者ID （或整合代碼）在單一索引鍵/值組中。 | 在[!DNL DCS]個呼叫中，這些ID的前置詞為`d_`首碼。 <br>範例： `d_cid_ic=39217_myIntegrationCode`。 | 請參閱`DPID`和`DPUUID`。 |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]。要用於廣告目的的每個硬體裝置特有的識別碼。通常由裝置或裝置作業系統的製造商提供。 | 請參閱[全域裝置識別碼](#global-device-ids)。 |  |

## [!DNL Global Device IDs] {#global-device-ids}

全域裝置ID是裝置製造商或作業系統提供的裝置廣告ID，每個裝置都有專屬的ID。 下表說明這些ID及其格式。 如需有關全域裝置ID以及如何在[!DNL Audience Manager]中使用它們的詳細資訊，請閱讀[全域資料來源](/help/using/features/global-data-sources.md)。

| ID | [!DNL Global Data Source ID] | 名稱和說明 | 範例 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers]識別碼是裝置製造商提供的行動裝置識別碼。 這些ID代表執行[!DNL iOS]作業系統的裝置。 | 格式必須由32個大寫十六進位數字組成，以5個群組顯示，並以連字型大小分隔，格式為8-4-4-4-12，總共36個字元。<br>範例： `AEBE52E7-03EE-455A-B3C4-E57283966239`。 |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]是Android裝置製造商提供的行動裝置識別碼。 這些ID代表執行[!DNL Android]作業系統的裝置。 | 格式必須由32個小寫十六進位數字組成，以5個群組顯示，並以連字型大小分隔，格式為8-4-4-4-12，總共36個字元。 <br>範例： `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`。 |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising]代表[!DNL Roku]個串流裝置。 | 格式必須由32個小寫十六進位數字組成，以5個群組顯示，並以連字型大小分隔，格式為8-4-4-4-12，總共36個字元。 <br>範例： `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`。 |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]是[!DNL Windows 10]以每個裝置、每個使用者為基礎的裝置識別碼。 | [!DNL MAID]的格式為英數字串。 |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising]是由[!DNL Samsung]部智慧型電視提供的裝置識別碼。 | [!DNL Samsung] [!DNL TIFA] ID的格式為英數字串。 |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | 代表執行[!DNL Fire OS]作業系統之裝置的裝置識別碼。 | 格式必須由32個小寫十六進位數字組成，以5個群組顯示，並以連字型大小分隔，格式為8-4-4-4-12，總共36個字元。 <br>範例: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | 代表執行[!DNL LG webOS]作業系統之裝置的裝置識別碼。 | 格式必須由32個小寫十六進位數字組成，以5個群組顯示，並以連字型大小分隔，格式為8-4-4-4-12，總共36個字元。 <br>範例: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | 代表執行Vizio智慧型電視作業系統之裝置的裝置識別碼。 | [!DNL Vizio IFA]個ID的格式為英數字串。 <br>範例： `7XCBNROQJQPYW`。 |
