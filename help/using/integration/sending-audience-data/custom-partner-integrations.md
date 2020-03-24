---
description: 此頁面列出 Audience Manager 與資料合作夥伴之間的自訂整合。
seo-description: 此頁面列出 Audience Manager 與資料合作夥伴之間的自訂整合。
seo-title: 自訂合作夥伴整合
solution: Audience Manager
title: 自訂合作夥伴整合
translation-type: tm+mt
source-git-commit: c069c901df6d8737f611d27ce7dffd4072e50adf

---


# 自訂合作夥伴整合 {#custom-partner-integrations}

此頁面列出 Audience Manager 與資料合作夥伴之間的自訂整合。

## Oracle Data Cloud {#oracle-data-cloud}

### 說明

Audience Manager 會透過傳入資料檔案，從適用於 Audience Marketplace 的 Oracle Data Cloud 擷取 Cookie 和行動 ID 資料。以下說明的自訂整合規格僅指包含行動ID（IDFA和Android裝置ID）的傳入資料檔案。

### 整合細節

從Oracle Data Cloud接收的入站資料檔案與Amazon S3 Name and File Size Requirements for Inbound Data Files [(入站資料檔案的](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) Amazon S3名稱和檔案大小要求)中描述的標准入站檔案名語法不同，與 [Inbound Data File Contents（入站資料檔案內容）中描述的標准入站檔案內容語法不同：語法、無效字元、變數和範例](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。

除了傳入資料檔案的標準實作欄位外，以下反白顯示的元素也是必要的。 如需所有其他標準欄位和檔案名稱元素的說明，請參閱上述兩個連結頁面中的檔案名稱語法和檔案內容語法。

### 檔案命名

ODC檔案名的結構如下：

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

檔 `odc` 案名稱元素會將檔案識別為從Oracle Data Cloud匯入，並指示Audience Manager傳入檔案驗證器處理檔案。

### 檔案內容

ODC入站資料檔案中的欄位必須按如下所示的順序顯示：

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

可以 `ID type` 是：

* IDFA
* Android裝置ID

>[!IMPORTANT]
>
>請勿在相同的傳入資料檔案中傳送IDFA和Android裝置ID。

## ODC入站檔案示例

下載范 [例檔案](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)。 此檔案可讓數個IDFA符合特徵ID 38838的資格。 您可以在標準文字編輯器或程式碼編輯器中開啟此檔案。