---
description: Audience Manager takes data security and privacy very seriously. 我們致力於確保系統安全，並保護您寶貴的資料。
seo-description: Audience manager非常重視資料安全性和隱私權。 我們致力於確保系統安全，並保護您寶貴的資料。
seo-title: 資料安全性
solution: Audience Manager
title: 資料安全性
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 9e1abb305c66a4adf6a42a7873144222491692f9

---


# 資料安全性 {#data-security}

Audience manager非常重視資料安全性和隱私權。 我們致力於確保系統安全，並保護您寶貴的資料。

Audience manager的安全性實務包括外部和內部稽核、活動記錄、訓練和其他程式，這些程式旨在協助保護我們的系統和您的寶貴資料。 我們相信，安全的產品有助於建立和維護客戶對我們的信任。

在Audience manager中，我們考慮了三個主要類別的安全性：

| 安全類型 | 支援 |
|---|---|
| **資訊安全** | 企業級驗證、加密和資料儲存實務 |
| **資料洩漏／透明度** | 對構成或促成資料洩漏的現場活動進行深入、可操作的洞察 |
| **流程／政策增強功能** | 客戶，透過使用隱私權與資料安全的業界最佳實務 |

## 系統、培訓與存取 {#systems-training-access}

有助於確保系統和資料安全的流程。

**** 外部安全性驗證： Audience manager會每年和每季測試安全性。

* 每年：Audience manager每年會接受獨立第三方公司的全面普及率測試。 此測試旨在識別應用程式中的安全性弱點。 這些測試包括掃描跨網站指令碼、插入SQL、表單參數控制以及其他應用程式層級的弱點。
* Quarterly: Once each quarter, internal teams check for security vulnerabilities. 這些測試包括網路掃描開啟埠和服務漏洞。

**** Systems Security:  To help keep data safe and private, Audience Manager:

* Blocks requests from unauthorized IP addresses.
* Protects data behind firewalls, VPNs, and with Virtual Private Cloud storage.
* 使用觸發式稽核記錄來追蹤客戶和控制資訊資料庫的變更。 These logs track all changes at the database level, including the user ID and IP address from which changes are made.

**Security Assets:**  Audience Manager has a dedicated network operations team that monitors firewalls and intrusion-detection devices. 只有重要人員才能存取我們的安全技術和資料。

**** 安全性訓練： 在內部，我們對安全性的承諾延伸到負責我們產品的開發人員。 Adobe provides formal training to developers on how to build secure applications and services.

**** Secure Access:  Audience Manager requires strong passwords to log on to the system. See password requirements.[](../../reference/password-requirements.md)

## Privacy and Personally Identifiable Information (PII) {#pii}

Processes that help keep personal information safe. 如需其他隱私權資訊，請參 [閱Adobe隱私權中心](https://www.adobe.com/privacy/advertising-services.html)。

**** PII資料： Audience manager合約禁止客戶和資料合作夥伴將PII資訊傳送至我們的系統。 Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** IP Addresses:  Audience Manager does collect IP addresses. IP位址用於資料處理和記錄匯整程式。 地理／位置查詢和定位也需要這些功能。 此外，保留的記錄檔中的所有IP位址都會在90天內模糊化。

## 資料分區 {#data-partitioning}

有助於保護個別客戶所擁有資料的程式。

**** 特徵資料分區： 您的資料（特徵、ID等）由客戶機分區。 這有助於防止不同客戶之間意外洩露資訊。 例如，Cookie中的特徵資料會依客戶劃分，並儲存在用戶端特定的子網域中。 其他Audience manager用戶端無法讀取或意外使用。 此外，儲存在中的特徵資料 [!UICONTROL Profile Cache Servers (PCS)] 也由客戶劃分。 如此可避免其他用戶端在事件呼叫或其他要求中意外使用您的資料。

**** 報告中的資料分區： 客戶端ID是所有報表表格中識別索引鍵的一部分，報表查詢會依ID篩選。 這有助於防止您的資料出現在其他Audience manager客戶的報表中。

## 傳入伺服器對伺服器(S2S)傳輸 {#inbound-s2s}

Adobe Audience manager支援兩種將S2S已登入的資料檔案傳輸至我們系統的主要方法：

這兩種方法的設計都考慮到了客戶和合作夥伴資料的安全性，同時資料在他們的系統和系統之間流動。

**** SFTP:對於SFTP選項，大部分客戶選擇通過使用安全殼層(SSH)協定的安全FTP(SFTP)協定傳遞檔案。 此方法可確保在客戶系統與Adobe系統之間進行檔案加密。 對於每位客戶，我們會在SFTP伺服器上建立已擱置的下拉式方塊位置，此位置會系結至該系統上的使用者帳戶。 只有客戶的認證和特權內部系統用戶才能訪問此囚禁中的下拉框位置。 其他客戶永遠無法進入此監獄。

**** Amazon Web Services S3（透過HTTPS）:對於S3傳送選項，建議所有客戶設定其S3用戶端，使用HTTPS加密方法進行檔案傳送（這不是預設值，因此必須明確設定）。 s3cmd命令列工具以及各種主要程式設計語言可用的S3程式庫都支援HTTPS選項。 啟用此HTTPS選項後，客戶的資料會在飛往我們的系統時進行加密。 我們為每個客戶建立個別的S3儲存貯體子目錄，只能由該客戶的認證和內部系統使用者的認證存取。

To add PGP encryption to your data files, see File PGP Encryption for Inbound Data Types.[](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)

## 通過逸出保護資料 {#escaping-data}

Note that  does not escape outgoing data to secure it against possible cross-site scripting (XSS), etc. [!DNL Audience Manager]It is the responsibility of the client to escape incoming data.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] is a web security policy mechanism that helps protect against cookie hijacking and protocol downgrade attacks by not permitting  traffic and transparently upgrading all  traffic to .[!DNL HTTP][!DNL HTTP][!DNL HTTPS]

This policy improves data security between clients and Adobe Edge servers.

### 範例 {#hsts-example}

When trying to access ,  will automatically upgrade the request to  , in case the browser doesn’t automatically request the  domain.`http://bank.demdex.com`[!DNL HSTS]`https://bank.demdex.com`[!DNL HTTPS]

See HTTP Strict Transport Security - Wikipedia for more information about HSTS.[](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
