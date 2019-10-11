---
description: 請參閱本檔案以取得Adobe Audience Manager ID的完整清單。
keywords: DPID;DPUUID;CID;UUID;uid;uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuid
seo-description: 請參閱本檔案以取得Adobe Audience Manager ID的完整清單。
seo-title: Audience Manager中ID的索引
solution: Audience Manager
title: Audience Manager中ID的索引
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 10f06885a803238bf8f5a6bbc2b864c982a2f909

---


# Audience Manager中ID的索引{#index-of-ids-in-audience-manager}

請參閱本檔案以取得Adobe Audience Manager ID的完整清單。

|ID|名稱與說明|範例||—|—|—|—||[!DNL AAM UUID]| Audience manager唯一使用者ID。 Audience manager會將38位數的數位裝置ID關聯至與之互動的每個裝置。 每當您在Audience Manager UI中看到提及獨特使用者時，請考慮這個ID。 Audience manager會將此ID儲存為第三方網 `demdex.net` 域中的Cookie。 Audience Manager UUID會在事件呼叫中傳送為 `d_uuid` 訊號。 |`demdex = 07955261652886032950143702505894272138`|
|[!DNL ImsOrgId]|組織 ID. 這是公司在註冊Experience cloud時所提供的ID。 若要瞭解如何尋找公司的組織ID，請閱讀「尋找 [您的組織ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)」。 |`5DC5123F5245B1D20A490D46@AdobeOrg`||PID|合作夥伴ID。 PID是Audience manager中的公司ID。 Audience manager會將 [!DNL imsOrgId] 與關聯 [!DNL PID]。 |`1352`|
|[!DNL ECID], [!DNL MID]|Experience Cloud ID. Experience Cloud ID(舊[!DNL ECID]有縮寫 [!DNL MID] 或 [!DNL MCID])是從您的組織ID和Audience Manager唯一使用者ID以數學方式衍生而來。 As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. 您可以在 [Cookies和Experience Cloud ID檔案中閱讀更多有關ECID的資訊](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html) 。 |`mid = 08382830887934830189014177072406221371` ||[!DNL SID]|特徵ID。 特徵ID可唯一識別Audience manager環境中的特徵。 「特徵ID」會指派給使用者介面(UI)中的每個特徵。 |`289983`||SID|區段ID。 區段ID可唯一識別Audience manager環境中的區段。 區段ID會指派給UI中的每個區段。 |`4798574`||[!DNL csegID]|舊區段ID。 此ID可唯一識別Audience manager環境中的區段。 舊有區段ID會指派給UI中的每個區段。 |`741232`|
|[!DNL destID]|Destination ID. 目標ID可唯一識別Audience Manager環境中的目標。 ID會指派給UI中的每個目標。 |`2523`||[!DNL DPID]|資料來源ID（也稱為資料提供者ID）。 「資料來源ID」是ID或特徵的命名空間。 ID會指派給UI中的每個資料來源（資料提供者）。 | `39217` ||[!DNL DPUUID]|資料提供者唯一使用者ID(也稱為 [!DNL CRM ID])。 第三方ID。 這是您用來識別自己系統中使用者的 [!DNL CRM] ID。 您可以與 [!DNL DPUUIDs] Audience Manager同 [!DNL UUIDs] 步，也可以在ID同 [!DNL DPUUIDs] 步程式中從不同的資料來源([!DNL DPIDs])同步。 |`2132-3423vn-343fds-3432r`||[!DNL CRM ID]|請參閱DPUUID。`2132-3423vn-343fds-3432r`|[!DNL CID]||[!DNL CID_IC],|客戶ID，客戶ID整合代碼。 和 [!DNL CID] 鍵 [!DNL CID_IC] 值對將替換 [!DNL DPID] 和 [!DNL DPUUID]。 它們提供與和相同的功 [!DNL DPID] 能 [!DNL DPUUID]，但效率更高，因為它們在單一索引鍵值對中包含資料提供者ID和使用者ID（或整合程式碼）。 ||
|[!DNL DAID]|Device Advertising ID. 要用於廣告目的的每個硬體裝置特有的識別碼。通常由裝置或裝置作業系統的製造商提供。 |請參閱 [全域裝置ID](#global-device-ids)。 |

## 全域裝置ID {#global-device-ids}

全域裝置ID是裝置廣告ID，是裝置製造商或作業系統所提供之每個裝置專屬的裝置廣告ID。 下表說明這些ID是什麼及其格式。

| ID | 名稱和說明 | 範例 |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [!DNL IDFA] | [!DNL Identifier for Advertisers] ID是裝置製造商提供的行動裝置識別碼。 這些ID代表執行iOS作業系統的裝置。 | 格式嚴格由32個大寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 範例: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | [!DNL Google Advertising ID]s是Android裝置製造商提供的行動裝置識別碼。 這些ID代表執行作業系統 [!DNL Android] 的裝置。 | 格式嚴格由32個小寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 範例: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | [!DNL Roku IDs for Advertising] 代表串 [!DNL Roku] 流裝置。 | 格式嚴格由32個小寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 範例: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | [!DNL Microsoft Advertising ID]s是每個裝置、每個 [!DNL Windows 10] 使用者產生的裝置識別碼。 | [!DNL MAID]s的格式為英數字串。 |
| [!DNL DUID] | [!DNL Samsung DUID]s是由Samsung Smart TV提供的裝置識別碼。 | Samsung的 [!DNL DUID]格式為英數字串。 |
| [!DNL Amazon Fire TV Advertising ID] | 代表執行作業系統之裝置的裝 [!DNL Fire OS] 置識別碼。 | 格式嚴格由32個小寫十六進位數字組成，以5個組顯示，以8-4-4-4-12格式用連字元分隔，共36個字元。 範例: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
