---
description: Audience manager非常重視資料安全性和隱私權。 我們致力於確保系統安全，並保護您寶貴的資料。
seo-description: Audience manager非常重視資料安全性和隱私權。 我們致力於確保系統安全，並保護您寶貴的資料。
seo-title: 資料安全性
solution: Audience Manager
title: 資料安全性
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 91444ad943fcd020c83e522922d67ef400bf8824

---


# 資料安全性 {#data-security}

Audience manager非常重視資料安全性和隱私權。 我們致力於確保系統安全，並保護您寶貴的資料。

Audience manager的安全性實務包括外部和內部稽核、活動記錄、訓練和其他程式，這些程式旨在協助保護我們的系統和您的寶貴資料。 我們相信，安全的產品有助於建立和維護客戶對我們的信任。

在Audience manager中，我們考慮了三個主要類別的安全性：

| Security Type | 支援 |
|---|---|
| **資訊安全** | Enterprise-level authentication, encryption, and data storage practices |
| **Data leakage/transparency** | Deep and actionable insight into on-site activities that constitute or contribute to data leakage |
| **Process/policy enhancements** | Clients, by working with industry best practices for privacy and data security |

## Systems, Training, and Access {#systems-training-access}

Processes that help keep our system and your data secure.

**External Security Validation:**  Audience Manager tests security on an annual and quarterly basis.

* Yearly: Once a year, Audience Manager undergoes a full penetration test conducted by an independent third-party company. The test is designed to identify security vulnerabilities in the application. The tests include scanning for cross-site scripting, SQL injections, form parameter manipulation, and other application-level vulnerabilities.
* 每季：每季一次，內部團隊會檢查安全性弱點。 These tests include network scans for open ports and service vulnerabilities.

**Systems Security:**  To help keep data safe and private, Audience Manager:

* Blocks requests from unauthorized IP addresses.
* 保護防火牆、 VPN和虛擬專用雲儲存後的資料。
* 使用觸發式稽核記錄來追蹤客戶和控制資訊資料庫的變更。 這些記錄檔會追蹤資料庫層級的所有變更，包括進行變更的使用者ID和IP位址。

**** 安全資產： Audience manager有專屬的網路營運團隊，負責監控防火牆和入侵偵測裝置。 只有重要人員才能存取我們的安全技術和資料。

**** 安全性訓練： 在內部，我們對安全性的承諾延伸到負責我們產品的開發人員。 Adobe為開發人員提供如何建立安全應用程式與服務的正式訓練。

**** 安全訪問： Audience manager需要強式密碼才能登入系統。 請參 [閱密碼要求](../../reference/password-requirements.md)。

## 隱私權與個人識別資訊(PII) {#pii}

有助於確保個人資訊安全的流程。 如需其他隱私權資訊，請參 [閱Adobe隱私權中心](https://www.adobe.com/privacy/advertising-services.html)。

**** PII資料： Audience manager合約禁止客戶和資料合作夥伴將PII資訊傳送至我們的系統。 此外，唯一使用者ID(UUID)不包含或使用PII資料做為ID產生演算法的一部分。

**** IP位址： Audience manager確實會收集IP位址。 IP位址用於資料處理和記錄匯整程式。 地理／位置查詢和定位也需要這些功能。 此外，保留的記錄檔中的所有IP位址都會在90天內模糊化。

## 資料分區 {#data-partitioning}

有助於保護個別客戶所擁有資料的程式。

**** 特徵資料分區： 您的資料（特徵、ID等）由客戶機分區。 這有助於防止不同客戶之間意外洩露資訊。 例如，Cookie中的特徵資料會依客戶劃分，並儲存在用戶端特定的子網域中。 其他Audience manager用戶端無法讀取或意外使用。 此外，儲存在中的特徵資料 [!UICONTROL Profile Cache Servers (PCS)] 也由客戶劃分。 如此可避免其他用戶端在事件呼叫或其他要求中意外使用您的資料。

**** 報告中的資料分區： 客戶端ID是所有報表表格中識別索引鍵的一部分，報表查詢會依ID篩選。 這有助於防止您的資料出現在其他Audience manager客戶的報表中。

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager supports two main methods of transferring S2S on-boarded data files to our systems:

Both methods are designed with the security of our customer and partner data in mind while data is in flight between their systems and our system.

**** SFTP: For the SFTP option, most customers choose to deliver files via the Secure FTP (SFTP) protocol, which uses the Secure Shell (SSH) protocol. This method ensures that files are encrypted while in flight between the customer's systems and Adobe's system. For each customer, we create a jailed drop-box location on our SFTP servers, which is tied to a user account on that system. Only the customer's credentialed and privileged internal system users can access this jailed drop-box location. 其他客戶永遠無法進入此監獄。

**** Amazon Web Services S3 via HTTPS: For the S3 delivery option, we recommend that all customers configure their S3 clients to use the HTTPS encryption method for file transfers (this is not the default, so it must be explicitly configured). The HTTPS option is supported both by the s3cmd command line tool as well as the S3 libraries available in every major programming language. With this HTTPS option enabled, customer's data is encrypted while in flight to our systems. For each customer, we create a separate S3 bucket sub-directory that can be accessed only by that customer's credentials and those of our internal system users.

To add PGP encryption to your data files, see File PGP Encryption for Inbound Data Types.[](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)

## Protecting Data by Escaping {#escaping-data}

Note that  does not escape outgoing data to secure it against possible cross-site scripting (XSS), etc. [!DNL Audience Manager]客戶有責任逸出傳入的資料。

## HTTP Strict-Transport-Security (#hsts)

[!DNL HTTP Strict-Transport-Security (HSTS)] 是網頁安全性原則機制，不允許流量並透明地將所有流量升級至，有助於防止Cookie劫持 [!DNL HTTP] 和通訊協定降級 [!DNL HTTP] 攻擊 [!DNL HTTPS]。

此政策可改善用戶端與Adobe edge伺服器間的資料安全性。

### 範例 {#hsts-example}

當嘗試存取時， `http://bank.demdex.com`會 [!DNL HSTS] 自動將要求升級至 `https://bank.demdex.com`，以防瀏覽器無法自動要求網 [!DNL HTTPS] 域。

如需 [有關HSTS的詳細資訊，請參閱HTTP嚴格傳輸安全性-](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) Wikipedia。
