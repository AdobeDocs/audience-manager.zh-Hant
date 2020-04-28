---
description: 請參閱本檔案以取得Adobe Audience Manager ID的完整清單。
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: 請參閱本檔案以取得Adobe Audience Manager ID的完整清單。
seo-title: Audience Manager中ID的索引
solution: Audience Manager
title: Audience Manager中ID的索引
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 723c75e8946c42779b4c27727ff9e6398b5fc9b1

---


# Audience Manager中ID的索引{#index-of-ids-in-audience-manager}

## 概述 {#overview}

Audience Manager使用多個ID來識別並管理您傳送給它的資料。 如需Adobe Audience Manager ID的完整清單，以及您應搭配使用的字首範例，請參閱本文。

## ID預檢 {#prefixing}

雖然您可以透過其獨立名稱來參照大部分的ID，但大部分ID在透過DCS呼叫傳入資料時，應與各種字首搭配使用。 Audience Manager會使用其中一些ID，而不會暴露給使用者，而使用者介面(UI)中也會顯示其他ID。

若要瞭解下列範例中使用的字首，請參 [閱DCS API呼叫的支援屬性](../api/dcs-intro/dcs-api-reference/dcs-keys.md)。

## Audience ManagerID清單 {#id-list}

| ID | 名稱和說明 | 使用與範例 | UI位置 |
|---|---|---|---|
| [!DNL AAM UUID] | Audience Manager唯一使用者ID，也稱為 [!UICONTROL Device ID]。 Audience Manager會將38位數的數位裝置ID關聯至與之互動的每個裝置。 每當您在Audience Manager UI中看到提及獨特使用者時，請考慮這個ID。 Audience Manager會將此ID儲存為第三方網 `demdex.net` 域中的Cookie。 | 在呼 [!DNL DCS] 叫中， `uuid` 前面有前置詞 `d_` 。 <br>範例: `d_uuid = 07955261652886032950143702505894272138` | 您可以在建立相似 [!UICONTROL Device ID] 模型 [和建立區段時，篩](../features/algorithmic-models/create-model.md)選特徵 [](../features/segments/segment-builder.md)。 您也可以在執行特徵的一般報 [!UICONTROL Device ID] 表和特 [徵的趨勢報表時，](../reporting/general-reports.md) 依據篩選結果 [](../reporting/trend-reports.md)。 |
| [!DNL ImsOrgId] | 組織 ID. 這是公司在註冊Experience Cloud帳戶時所提供的ID。 | `5DC5123F5245B1D20A490D46@AdobeOrg` | 在Audience Manager UI中不可見。 若要瞭解如何尋找公司的組織ID，請閱讀「尋找 [您的組織ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)」。 |
| PID | 合作夥伴ID。 PID是Audience Manager中的公司ID。 Audience Manager會將 [!DNL imsOrgId] 與關聯 [!DNL PID]。 | `1352` | 在Audience Manager UI中不可見。 |
| [!DNL ECID], [!DNL MID] | Experience Cloud ID。Experience Cloud ID(舊[!DNL ECID]有縮寫 [!DNL MID] 或 [!DNL MCID])是從您的組織ID和Audience Manager唯一使用者ID以數學方式衍生而來。 As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. 您可以在 [Cookies和Experience Cloud ID檔案中閱讀更多有關ECID的資訊](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) 。 | `mid = 08382830887934830189014177072406221371` | 在Audience Manager UI中不可見。 |
| [!DNL SID] | 特徵ID。 特徵ID可唯一識別Audience Manager環境中的特徵。 | 在呼 [!DNL DCS] 叫中， `SID` 前面有前置詞 `d_` 。 <br>範例 `d_sid=289983`. | 「特徵ID」會指派給每個特徵，並在「特徵」頁面的UI中 [顯示](../features/traits/trait-details-page.md) 。 |
| [!DNL SID] | 區段ID。 區段ID可唯一識別Audience Manager環境中的區段。 | 在呼 [!DNL DCS] 叫中， `SID` 前面有前置詞 `d_` 。 <br>範例 `d_sid=4798574`. | 區段ID會指派給每個區段，並在「區段」頁面的UI中 [顯示](../features/segments/segment-summary-view.md) 。 |
| [!DNL csegID] | 舊有區段ID。 此ID可唯一識別Audience Manager環境中的區段。 | `741232` | 「舊有區段ID」會指派給每個區段，並顯示在「區段」頁面的UI [中](../features/segments/segment-summary-view.md) 。 |
| [!DNL destID] | 目標ID。 目標ID可唯一識別Audience Manager環境中的目標。 ID會指派給UI中的每個目標。 | `2523` | 目標ID會指派給每個目標，並在「目標」頁面的UI中 [顯示](../features/destinations/destinations-home.md) 。 |
| [!DNL DPID] | 資料來源ID（也稱為資料提供者ID）。 「資料來源ID」是ID或特徵的命名空間。 ID會指派給UI中的每個資料來源（資料提供者）。 | 在呼 [!DNL DCS] 叫中， `dpid` 前面有前置詞 `d_` 。 <br>範例: `d_dpid=39217`. | 資料提供者ID會指派給每個資料來源，並在「資料來源」頁面的UI中 [顯示](../features/datasources-list-and-settings.md) 。 |
| [!DNL DPUUID] | 資料提供者唯一使用者ID，也稱為 [!DNL CRM ID] 或 [!UICONTROL Cross-Device ID]。 第三方ID。 這是您用來識別自己系統中使用者的 [!DNL CRM] ID。 您可以與 [!DNL DPUUIDs] Audience Manager同 [!DNL UUIDs] 步，也可以在ID同 [!DNL DPUUIDs] 步程式中從不同的資料來源([!DNL DPIDs])同步。 | 在DCS呼叫中， `dpuuid` 前面有首 `d_` 碼。 <br> 範例 `d_dpuuid=2132-3423vn-343fds-3432r`. | 您可以在建立相似 [!UICONTROL Cross-Device ID] 模型 [和建立區段時，篩](../features/algorithmic-models/create-model.md)選特徵 [](../features/segments/segment-builder.md)。 您也可以在執行特徵的一般報 [!UICONTROL Cross-Device ID] 表和特 [徵的趨勢報表時，](../reporting/general-reports.md) 依據篩選結果 [](../reporting/trend-reports.md)。 |
| [!DNL CRM ID] | 請參閱「`DPUUID`」。 | 請參閱「`DPUUID`」。 | 請參閱「`DPUUID`」。 |
| [!DNL CID], [!DNL CID_IC] | 客戶ID、客戶ID整合代碼。 和 [!DNL CID] 鍵 [!DNL CID_IC] 值對將替換 [!DNL DPID] 和 [!DNL DPUUID]。 它們提供與和相同的功 [!DNL DPID] 能 [!DNL DPUUID]，但效率更高，因為它們在單一索引鍵值對中包含資料提供者ID和使用者ID（或整合程式碼）。 | 在DCS呼叫中，這些ID前面有首 `d_` 碼。 <br>範例: `d_cid_ic=39217_myIntegrationCode`. | 請參閱 `DPID` 和 `DPUUID`。 |
| [!DNL DAID] | 裝置廣告ID。 要用於廣告目的的每個硬體裝置特有的識別碼。通常由裝置或裝置作業系統的製造商提供。 | 請參 [閱全域裝置ID](#global-device-ids)。 |  |

## 全域裝置ID {#global-device-ids}

全域裝置ID是裝置廣告ID，是裝置製造商或作業系統所提供之每個裝置專屬的裝置廣告ID。 下表說明這些ID是什麼及其格式。 如需全域裝置ID以及如何在Audience Manager中使用這些ID的詳細資訊，請閱讀全 [域資料來源](/help/using/features/global-data-sources.md)。

| ID | 全域資料來源ID | 名稱和說明 | 範例 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID是裝置製造商提供的行動裝置識別碼。 這些ID代表執行iOS作業系統的裝置。 | 格式嚴格由32個大寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。<br> 範例: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s是Android裝置製造商提供的行動裝置識別碼。 這些ID代表執行作業系統 [!DNL Android] 的裝置。 | 格式嚴格由32個小寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 <br>範例: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] 代表串 [!DNL Roku] 流裝置。 | 格式嚴格由32個小寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 <br>範例: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s是每個裝置、每個 [!DNL Windows 10] 使用者產生的裝置識別碼。 | [!DNL MAID]s的格式為英數字串。 |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]s是由Samsung Smart TV提供的裝置識別碼。 | Samsung的 [!DNL DUID]格式為英數字串。 |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | 代表執行作業系統之裝置的裝 [!DNL Fire OS] 置識別碼。 | 格式嚴格由32個小寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 <br>範例: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |

