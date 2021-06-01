---
description: 此頁面列出 Audience Manager 與資料合作夥伴之間的自訂整合。
seo-description: 此頁面列出 Audience Manager 與資料合作夥伴之間的自訂整合。
seo-title: 自訂合作夥伴整合
solution: Audience Manager
title: 自訂合作夥伴整合
feature: 協力廠商整合
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 22%

---

# 自訂合作夥伴整合 {#custom-partner-integrations}

此頁面列出 Audience Manager 與資料合作夥伴之間的自訂整合。

## Oracle資料雲{#oracle-data-cloud}

### 說明

Audience Manager 會透過傳入資料檔案，從適用於 Audience Marketplace 的 Oracle Data Cloud 擷取 Cookie 和行動 ID 資料。以下說明的自訂整合規格僅指包含行動ID（IDFA和Android裝置ID）的傳入資料檔案。

### 整合細節

從Oracle資料雲接收的傳入資料檔案與[Amazon S3名稱和傳入資料檔案的檔案大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)中所述的標準傳入檔案名稱語法不同，而與[傳入資料檔案內容中描述的標準傳入檔案內容語法不同：語法、無效字元、變數和Examples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。

除了傳入資料檔案的標準實作欄位外，以下強調顯示的元素為必要元素。 有關所有其他標準欄位和檔案名元素的說明，請參閱上述連結的兩頁中的「檔案名語法」和「檔案內容語法」。

### 檔案命名

ODC檔案名的結構如下：

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

`odc`檔案名稱元素會識別從OracleData Cloud匯入的檔案，並指示Audience Manager傳入檔案驗證器依此方式處理。

### 檔案內容

ODC入站資料檔案中的欄位必須按以下順序顯示：

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

`ID type`可以是：

* IDFA
* Android裝置ID

>[!IMPORTANT]
>
>請勿在相同的傳入資料檔案中傳送IDFA和Android裝置ID。

## ODC傳入檔案示例

下載[範例檔案](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)。 此檔案會符合數個IDFA的特徵ID 38838資格。 您可以在標準文字編輯器或程式碼編輯器中開啟此檔案。
