---
description: 此頁面列出 Audience Manager 與資料合作夥伴之間的自訂整合。
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: 自訂合作夥伴整合
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 18%

---

# 自訂合作夥伴整合 {#custom-partner-integrations}

此頁面列出 Audience Manager 與資料合作夥伴之間的自訂整合。

## Oracle資料雲 {#oracle-data-cloud}

### 說明

Audience Manager 會透過傳入資料檔案，從適用於 Audience Marketplace 的 Oracle Data Cloud 擷取 Cookie 和行動 ID 資料。下面描述的自定義整合規範僅引用包含移動ID（IDFA和Android設備ID）的入站資料檔案。

### 整合細節

從Oracle資料雲接收的入站資料檔案與中描述的標准入站檔案名語法不同 [Amazon入站資料檔案的S3名稱和檔案大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 以及中所述的標准入站檔案內容語法 [入站資料檔案內容：語法、無效字元、變數和示例](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。

除了入站資料檔案的標準實現欄位外，還需要以下突出顯示的元素。 有關所有其它標準欄位和檔案名元素的說明，請參閱上面連結的兩頁中的檔案名語法和檔案內容語法。

### 檔案命名

ODC檔案名的結構化為：

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

的 `odc` 檔案名元素將檔案標識為從Oracle資料雲導入，並指示Audience Manager入站檔案驗證程式進行這樣的處理。

### 檔案內容

ODC入站資料檔案中的欄位必須按如下所示的順序顯示：

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

的 `ID type` 可以：

* IDFA
* Android設備ID

>[!IMPORTANT]
>
>不要在同一入站資料檔案中發送IDFA和Android設備ID。

## ODC入站檔案示例

下載 [示例檔案](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)。 此檔案為特性ID 38838限定了幾個IDFA。 可以在標準文本編輯器或代碼編輯器中開啟此檔案。
