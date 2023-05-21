---
description: 有關Adobe Audience ManagerID的完整清單，請參閱本文檔。
keywords: DPID;DPUUID;CID;UUID;uuid;uuiduuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuid, uuid, uuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Audience Manager 內的 ID 索引
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: Reference
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
source-git-commit: e408c118870fb331c40758be8a7e6b38690aeb5f
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 5%

---

# 中ID的索引 [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## 概述 {#overview}

[!DNL Audience Manager] 使用多個ID來標識和管理您發送給它的資料。 請參閱本文，瞭解 [!DNL Audience Manager] ID，以及應使用前置詞的示例。

## ID前置詞 {#prefixing}

雖然您可以通過這些ID的獨立名稱來引用其中的大多數ID，但大多數ID在通過資料傳遞時應與各種前置詞一起使用 [!DNL DCS] 呼叫。 其中一些ID由 [!DNL Audience Manager] 而其他內容也可在用戶介面(UI)中看到。

要瞭解以下示例中使用的前置詞，請參見 [DCS API調用的支援屬性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)。

## [!DNL Audience Manager] ID 清單 {#id-list}

| ID | 名稱和說明 | 用法和示例 | 用戶介面位置 |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID]，也稱為 [!UICONTROL Device ID]。 38位數字設備ID [!DNL Audience Manager] 與其交互的每個設備相關聯。 每當您在中看到提到唯一用戶時，請考慮此ID [!DNL Audience Manager] UI。 Audience Manager將此ID另存為 [!DNL cookie] 的 `demdex.net` 第三方域。 | 在 [!DNL DCS] 呼叫， `uuid` 前面是 `d_` 前置詞。 <br>範例: `d_uuid = 07955261652886032950143702505894272138` | 可以篩選 [!DNL traits] 按 [!UICONTROL Device ID] 建立 [長相相似的模型](../features/algorithmic-models/create-model.md), [建築物](../features/segments/segment-builder.md)。 也可以按 [!UICONTROL Device ID] 運行 [特徵的一般報告](../reporting/general-reports.md) 和 [特徵趨勢報告](../reporting/trend-reports.md)。 |
| [!DNL ImsOrgId] | [!DNL Organization ID]。這是公司在註冊時提供的ID [!DNL Experience Cloud] 帳戶。 | `5DC5123F5245B1D20A490D46@AdobeOrg` | 在中不可見 [!DNL Audience Manager] 用戶介面。 瞭解如何查找公司 [!DNL Organization ID]，閱讀 [查找您的組織ID](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)。 |
| [!DNL PID] | [!DNL Partner ID]。的 [!DNL PID] 是公司的ID [!DNL Audience Manager]。 Audience Manager聯營公司及 [!DNL imsOrgId] 到 [!DNL PID]。 | `1352` | 在中不可見 [!DNL Audience Manager] 用戶介面。 |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. 的 [!DNL Experience Cloud] ID([!DNL ECID]，舊縮寫 [!DNL MID] 或 [!DNL MCID])從你的 [!DNL Organization ID] 和 [!DNL Audience Manager] [!UICONTROL Unique User ID]。 只要這些ID保持不變，就生成右 [!DNL ECID] 對於特定用戶來說，這只是個數學問題。 相同 [!DNL Organization ID] 和 [!DNL Audience Manager] [!DNL UUID] 你得到的 [!DNL ECID] 值。 您可以閱讀有關 [!DNL ECID] 的 [Cookie和Experience CloudID](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) 文檔。 | `mid = 08382830887934830189014177072406221371` | 在中不可見 [!DNL Audience Manager] 用戶介面。 |
| [!DNL SID] | [!UICONTROL Trait ID]。的 [!UICONTROL Trait ID] 唯一標識 [!DNL traits] 的 [!DNL Audience Manager] 環境。 | 在 [!DNL DCS] 呼叫， `SID` 前面是 `d_` 前置詞。 <br>範例 `d_sid=289983`. | A [!UICONTROL Trait ID] 分配給每個 [!DNL trait]，在用戶介面中可見 [性狀](../features/traits/trait-details-page.md) 的子菜單。 |
| [!DNL SID] | [!UICONTROL Segment ID]。的 [!UICONTROL Segment ID] 唯一標識 [!DNL segments] 的 [!DNL Audience Manager] 環境。 | 在 [!DNL DCS] 呼叫， `SID` 前面是 `d_` 前置詞。 <br>範例 `d_sid=4798574`. | A [!UICONTROL Segment ID] 分配給每個 [!DNL segment]，在用戶介面中可見 [段](../features/segments/segment-summary-view.md) 的子菜單。 |
| [!DNL csegID] | [!DNL Legacy Segment ID]。此ID唯一地標識 [!DNL Audience Manager] 環境。 | `741232` | A [!UICONTROL Legacy Segment ID] 分配給每個段，在用戶介面中顯示 [段](../features/segments/segment-summary-view.md) 的子菜單。 |
| [!DNL destID] | [!UICONTROL Destination ID]。的 [!UICONTROL Destination ID] 唯一標識 [!DNL destinations] 的 [!DNL Audience Manager] 環境。 ID分配給每個 [!DNL destination] 的子菜單。 | `2523` | A [!UICONTROL Destination ID] 分配給每個 [!DNL destination]，在用戶介面中可見 [目標](../features/destinations/destinations-home.md) 的子菜單。 |
| [!DNL DPID] | [!UICONTROL Data Source ID] (亦稱： [!UICONTROL Data Provider ID])。 的 [!UICONTROL Data Source ID] 是ID或 [!DNL traits]。 ID分配給每個 [!DNL data source] （資料提供程式）。 | 在 [!DNL DCS] 呼叫， `dpid` 前面是 `d_` 前置詞。 <br>範例: `d_dpid=39217`. | A [!UICONTROL Data Provider ID] 分配給每個 [!DNL data source]，在用戶介面中可見 [資料源](../features/datasources-list-and-settings.md) 的子菜單。 |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID]，也稱為 [!DNL CRM ID] 或 [!UICONTROL Cross-Device ID]。 第三方ID。 這是標識您自己的最終用戶的ID [!DNL CRM] 系統。 可以同步 [!DNL DPUUIDs] 與 [!DNL Audience Manager] [!DNL UUIDs] 你可以同步 [!DNL DPUUIDs] 你的不同 [!UICONTROL Data Sources] ([!DNL DPIDs])。 | 在 [!DNL DCS] 呼叫， `dpuuid` 前面是 `d_` 前置詞。 <br> 範例 `d_dpuuid=2132-3423vn-343fds-3432r`. | 可以篩選 [!DNL traits] 按 [!UICONTROL Cross-Device ID] 建立 [長相相似的模型](../features/algorithmic-models/create-model.md), [建築物](../features/segments/segment-builder.md)。 也可以按 [!UICONTROL Cross-Device ID] 運行 [特徵的一般報告](../reporting/general-reports.md) 和 [特徵趨勢報告](../reporting/trend-reports.md)。 |
| [!DNL CRM ID] | 請參閱「`DPUUID`」。 | 請參閱「`DPUUID`」。 | 請參閱「`DPUUID`」。 |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. 的 [!DNL CID] 和 [!DNL CID_IC] 鍵值對替換 [!DNL DPID] 和 [!DNL DPUUID]。 它們提供與 [!DNL DPID] 和 [!DNL DPUUID]，但效率更高，因為它們將資料提供程式ID和用戶ID（或整合代碼）包含在單個鍵值對中。 | 在 [!DNL DCS] 調用，這些ID前面 `d_` 前置詞。 <br>範例: `d_cid_ic=39217_myIntegrationCode`. | 請參閱 `DPID` 和 `DPUUID`。 |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]。要用於廣告目的的每個硬體裝置特有的識別碼。通常由設備或設備作業系統的製造商提供。 | 請參閱 [全局設備ID](#global-device-ids)。 |  |

## [!DNL Global Device IDs] {#global-device-ids}

全局設備ID是設備廣告ID，是設備製造商或作業系統提供的每個設備所特有的。 下表說明了這些ID的類型和格式。 有關全局設備ID以及如何在中使用它們的詳細資訊 [!DNL Audience Manager]，閱讀 [全局資料源](/help/using/features/global-data-sources.md)。

| ID | [!DNL Global Data Source ID] | 名稱和說明 | 範例 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID是由設備製造商提供的移動設備標識符。 這些ID表示運行 [!DNL iOS] 作業系統。 | 格式嚴格由32個大寫的十六進位數字組成，以8-4-4-4-12的形式顯示，分為五組，用連字元分隔，共36個字元。<br> 範例: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s是Android設備製造商提供的移動設備標識符。 這些ID表示運行 [!DNL Android] 作業系統。 | 格式嚴格由32個小寫十六進位數字組成，以8-4-4-4-12格式顯示，分為五組，用連字元分隔，共36個字元。 <br>範例: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] 代表 [!DNL Roku] 流式傳輸設備。 | 格式嚴格由32個小寫十六進位數字組成，以8-4-4-4-12格式顯示，分為五組，用連字元分隔，共36個字元。 <br>範例: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s是由 [!DNL Windows 10] 按設備、按用戶計算。 | [!DNL MAID]s的格式為字母數字字串。 |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] 是設備標識符 [!DNL Samsung] 智慧電視。 | [!DNL Samsung] [!DNL TIFA] ID的格式為字母數字字串。 |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | 代表運行該設備的設備的設備標識符 [!DNL Fire OS] 作業系統。 | 格式嚴格由32個小寫十六進位數字組成，以8-4-4-4-12格式顯示，分為五組，用連字元分隔，共36個字元。 <br>範例: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | 代表運行該設備的設備的設備標識符 [!DNL LG webOS] 作業系統。 | 格式嚴格由32個小寫十六進位數字組成，以8-4-4-4-12格式顯示，分為五組，用連字元分隔，共36個字元。 <br>範例: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | 代表運行Vizio智慧電視作業系統的設備的設備標識符。 | [!DNL Vizio IFA] ID的格式為字母數字字串。 <br>範例: `7XCBNROQJQPYW`. |
