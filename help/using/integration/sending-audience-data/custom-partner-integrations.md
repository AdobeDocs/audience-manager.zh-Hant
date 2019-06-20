---
description: 此頁面列出 Audience Manager 與資料合作夥伴之間的自訂整合。
seo-description: 此頁面列出 Audience Manager 與資料合作夥伴之間的自訂整合。
seo-title: 自訂合作夥伴整合
solution: Audience Manager
title: 自訂合作夥伴整合
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Custom Partner Integrations {#custom-partner-integrations}

此頁面列出 Audience Manager 與資料合作夥伴之間的自訂整合。

## Oracle Data Cloud {#oracle-data-cloud}

**說明**

Audience Manager 會透過傳入資料檔案，從適用於 Audience Marketplace 的 Oracle Data Cloud 擷取 Cookie 和行動 ID 資料。以下所述的自訂整合規格僅適用於包含行動ID的傳入資料檔案(IDFA和Android裝置ID)。

<br> 

**整合資訊**

Inbound Data Files received from the Oracle Data Cloud differ from the standard inbound file name syntax described in [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) and from the standard inbound file content syntax described in [Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

除了傳入資料檔案的標準實施欄位外，以下強調的元素也是必要項目。如需所有其他標準欄位和檔案名稱元素的說明，請參閱上述兩頁中的「檔案名稱語法」和「檔案內容語法」。

<br> 

**檔案命名**

ODC檔案名稱的結構如下：

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

`odc` 檔案名稱元素會識別檔案從Oracle Data Cloud匯入，並指示Audience Manager傳入的檔案驗證器進行處理。

<br> 

**檔案內容**

ODC傳入資料檔案中的欄位必須以下列順序顯示：

<pre>&lt;<b>ID type</b>&gt;&lt;TAB&gt;&lt;user ID&gt;&lt;TAB&gt;&lt;trait ID&gt;,&lt;trait ID&gt;,&lt;trait ID&gt;,...</pre>

The `ID type` can be:

* IDFA
* Android裝置ID

>[!IMPORTANT]
>
>請勿在相同傳入的資料檔案中傳送IDFA和Android裝置ID。

<br> 

**ODC傳入檔案範例**

Download the [sample file](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). 此檔案可為特徵ID38838資格取得數個IDFA。您可以在標準文字編輯器或程式碼編輯器中開啓此檔案。