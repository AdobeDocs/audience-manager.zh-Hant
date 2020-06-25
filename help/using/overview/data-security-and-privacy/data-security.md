---
description: Audience Manager 非常重視資料安全性和隱私權。我們致力確保系統安全無虞及保護您寶貴的資料。
seo-description: Audience Manager 非常重視資料安全性和隱私權。我們致力確保系統安全無虞及保護您寶貴的資料。
seo-title: Audience Manager 的資料安全性
solution: Audience Manager
title: Audience Manager 的資料安全性
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 98%

---


# Audience Manager 的資料安全性 {#data-security}

Audience Manager 非常重視資料安全性和隱私權。我們致力確保系統安全無虞及保護您寶貴的資料。

Audience Manager 的安全性實務作法包括外部與內部稽核、活動記錄、培訓和其他程序，這些程序的設計目的是協助保護我們的系統和您的寶貴資料。我們相信，安全的產品有助於建立和維持客戶對我們的信任。

在 Audience Manager 中，我們針對三大類別考量安全性：

| 安全類型 | 提供支援的對象 |
|---|---|
| **資訊安全** | 企業級驗證、加密和資料儲存實務作法 |
| **資料洩漏/透明度** | 對構成或促成資料洩漏的站上活動執行的可操作深入分析 |
| **增強流程/政策** | 客戶，藉由採用業界最佳的隱私權與資料安全性實務作法 |

## 系統、培訓與存取 {#systems-training-access}

有助於確保系統和資料安全的程序。

**外部安全性驗證：** Audience Manager 會進行年度和季度安全測試。

* 年度：Audience Manager 每年會接受一次獨立第三方公司進行的全面滲透測試。此測試的目的是識別應用程式中的安全性弱點。這些測試包括掃描跨網站指令碼、SQL 插入、表單參數操控以及其他應用程式層級的弱點。
* 季度：內部團隊每季會檢查一次安全性弱點。這些測試包括針對開放連接埠和服務弱點進行網路掃描。

**系統安全性：**&#x200B;為協助確保資料安全無虞且隱私，Audience Manager 會：

* 封鎖來自未授權 IP 位址的請求。
* 保護防火牆、VPN 後和使用虛擬私有雲端儲存空間的資料。
* 使用觸發式稽核記錄來追蹤客戶和控制資訊資料庫的變更。這些記錄會追蹤資料庫層級的所有變更，包括進行變更的使用者 ID 和 IP 位址。

**安全資產：** Audience Manager 有一個專責的網路營運團隊，負責監控防火牆和入侵偵測裝置。只有重要人員才能存取我們的安全技術和資料。

**安全培訓：**&#x200B;在公司內部，我們對安全性的承諾延伸到負責我們產品的開發人員。Adobe 為開發人員提供如何建立安全應用程式與服務的正式培訓。

**安全存取：** Audience Manager 需要增強式密碼才能登入系統。請參閱[密碼要求](../../reference/password-requirements.md)。

## 隱私權與個人識別資訊 (PII) {#pii}

有助於確保個人資訊安全的程序。如需其他隱私權資訊，請參閱 [Adobe 隱私權中心](https://www.adobe.com/tw/privacy/experience-cloud.html)。

**PII 資料：** Audience Manager 合約禁止客戶和資料合作夥伴將 PII 資訊傳送至我們的系統中。此外，不重複使用者 ID (UUID) 不包含，也不使用 PII 資料作為 ID 產生演算法的一部分。

**IP 位址：** Audience Manager 確實會收集 IP 位址。IP 位址用於資料處理和記錄彙程序。地理/位置查詢和目標定位也需使用 IP 位址。此外，保留的記錄檔中的所有 IP 位址都會在 90 天內模糊化。

## 資料分割 {#data-partitioning}

有助於保護個別用戶端所擁有資料的程序。

**特徵資料分區：**  您的資[!UICONTROL traits]料（ID等） 由用戶端分割。這有助於防止不同用戶端之間意外洩露資訊。例如，Cookie 中的特徵資料會依客戶分割，並儲存在用戶端專用的子網域中，其他 Audience Manager 用戶端無法讀取或意外使用。此外，儲存在 [!UICONTROL Profile Cache Servers (PCS)] 中的特徵資料也是由用戶端分割。這麼做可避免其他用戶端在事件呼叫或其他請求中意外使用您的資料。

**報表中的資料分割：**&#x200B;用戶端 ID 屬於所有報表表格中識別索引鍵的一部分，且報表查詢會依 ID 篩選。這有助於防止您的資料出現在其他 Audience Manager 用戶端的報表中。

## 傳入伺服器對伺服器 (S2S) 傳輸 {#inbound-s2s}

Adobe Audience Manager 支援兩種主要方法，可將 S2S 已上線的資料檔案傳輸至我們的系統：

這兩種方法的設計都有考量在雙方系統之間傳輸資料的過程中，客戶和合作夥伴資料的安全性。

**SFTP：**&#x200B;針對 SFTP 選項，大部分客戶選擇透過使用安全殼層 (SSH) 通訊協定的安全 FTP (SFTP) 通訊協定來傳送檔案。此方法可確保對在客戶系統與 Adobe 系統之間傳輸的檔案進行加密。我們會為每個客戶在 SFTP 伺服器上建立監禁的下拉式方塊位置，此位置會繫結至該系統上的使用者帳戶。只有該客戶的經認證和獲權限內部系統使用者可以存取這個監禁的下拉式方塊位置。其他客戶永遠無法進入這個監獄。

**[!UICONTROL Amazon Web Services S3](透過 HTTPS 傳輸)：**針對 S3 傳送選項，建議所有客戶將其 S3 用戶端設定為使用 HTTPS 加密方法進行檔案傳輸 (這不是預設值，因此必須明確設定)。s3cmd 命令列工具及各種主要程式設計語言可用的 S3 程式庫都支援 HTTPS 選項。啟用此 HTTPS 選項後，便會在將客戶的資料傳輸至我們的系統時進行加密。我們會為每個客戶建立獨立的 S3 儲存貯體子目錄，只有該客戶的認證和我們的內部系統使用者的認證可存取。

若要將 PGP 加新增到您的資料檔案，請參閱[傳入資料類型的檔案 PGP 加密](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)。

## 藉由逸出保護資料 {#escaping-data}

請注意，[!DNL Audience Manager] 不會逸出傳出的資料，以防其遭受跨網站指令碼 (XSS) 等攻擊。用戶端有責任將傳入的資料逸出。

## HTTP 強制安全傳輸技術 {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] 是業界通用的 Web 安全機制，可協助抵禦 Cookie 劫持和通訊協定降級攻擊。

此政策會指示 Web 瀏覽器，一旦對指定網域發出安全 [!DNL HTTPS] 呼叫，就不得允許任何後續的不安全呼叫 ([!DNL HTTP]) 傳至該網域。這可以抵禦中間人攻擊，這類攻擊者可能會嘗試將 [!DNL HTTPS] 呼叫降級為不受保護的 [!DNL HTTP] 呼叫。

此政策可改善用戶端與 Adobe [Edge](../../reference/system-components/components-edge.md) 伺服器間的資料安全性。

### 範例 {#hsts-example}

Let&#39;s say the `yourcompany.demdex.com` domain sends traffic to the [!DNL DCS] via [!DNL HTTP]. [!DNL HSTS] 將呼叫升級以改用 [!DNL HTTPS]，而所有後續來自 `yourcompany.demdex.com` 的 [!DNL DCS] 呼叫都會使用 [!DNL HTTPS] 而非 [!DNL HTTP]。

如需有關 HSTS 的詳細資訊，請參閱 [HTTP 強制安全傳輸技術 - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)。
