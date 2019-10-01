---
description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-title: Data Security
solution: Audience Manager
title: Data Security
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: b76e905ec890dbe8270177d142dddb351438b039

---


# Data Security {#data-security}

Audience manager非常重視資料安全性和隱私權。 我們致力於確保系統安全，並保護您寶貴的資料。

Audience manager的安全性實務包括外部和內部稽核、活動記錄、訓練和其他程式，這些程式旨在協助保護我們的系統和您的寶貴資料。 我們相信，安全的產品有助於建立和維護客戶對我們的信任。

在Audience manager中，我們考慮了三個主要類別的安全性：

| 安全類型 | 支援 |
|---|---|
| **資訊安全** | 企業級驗證、加密和資料儲存實務 |
| **資料洩漏／透明度** | 對構成或促成資料洩漏的現場活動進行深入、可操作的洞察 |
| **流程／政策增強功能** | Clients, by working with industry best practices for privacy and data security |

## Systems, Training, and Access {#systems-training-access}

Processes that help keep our system and your data secure.

**** External Security Validation:  Audience Manager tests security on an annual and quarterly basis.

* Yearly: Once a year, Audience Manager undergoes a full penetration test conducted by an independent third-party company. The test is designed to identify security vulnerabilities in the application. The tests include scanning for cross-site scripting, SQL injections, form parameter manipulation, and other application-level vulnerabilities.
* 每季：每季一次，內部團隊會檢查安全性弱點。 這些測試包括網路掃描開啟埠和服務漏洞。

**** 系統安全性： 為協助確保資料安全且私密，Audience Manager:

* 阻止來自未授權IP位址的請求。
* 保護防火牆、 VPN和虛擬專用雲儲存後的資料。
* 使用觸發式稽核記錄來追蹤客戶和控制資訊資料庫的變更。 這些記錄檔會追蹤資料庫層級的所有變更，包括進行變更的使用者ID和IP位址。

**** 安全資產： Audience manager有專屬的網路營運團隊，負責監控防火牆和入侵偵測裝置。 只有重要人員才能存取我們的安全技術和資料。

**** 安全性訓練： 在內部，我們對安全性的承諾延伸到負責我們產品的開發人員。 Adobe為開發人員提供如何建立安全應用程式與服務的正式訓練。

**** 安全訪問： Audience manager需要強式密碼才能登入系統。 請參 [閱密碼要求](../../reference/password-requirements.md)。

## 隱私權與個人識別資訊(PII) {#pii}

有助於確保個人資訊安全的流程。 如需其他隱私權資訊，請參 [閱Adobe隱私權中心](https://www.adobe.com/privacy/advertising-services.html)。

**** PII Data:  Audience Manager contractually prohibits customers and data partners from sending PII information into our system. Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** IP Addresses:  Audience Manager does collect IP addresses. IP addresses are used in data-processing and log-aggregation processes. They are also required for geographic/location look-ups and targeting. Additionally, all IP addresses within retained log files are obfuscated within 90 days.

## Data Partitioning {#data-partitioning}

Processes that help protect data owned by individual clients.

**** Trait Data Partitioning:  Your data (traits, IDs, etc.) is partitioned by client. This helps prevent accidental information exposure between different clients. For example, trait data in cookies is partitioned by customer and stored in a client-specific sub-domain. 其他Audience manager用戶端無法讀取或意外使用。 此外，儲存在中的特徵資料 [!UICONTROL Profile Cache Servers (PCS)] 也由客戶劃分。 如此可避免其他用戶端在事件呼叫或其他要求中意外使用您的資料。

**** 報告中的資料分區： 客戶端ID是所有報表表格中識別索引鍵的一部分，報表查詢會依ID篩選。 這有助於防止您的資料出現在其他Audience manager客戶的報表中。

## 傳入伺服器對伺服器(S2S)傳輸 {#inbound-s2s}

Adobe Audience manager支援兩種將S2S已登入的資料檔案傳輸至我們系統的主要方法：

這兩種方法的設計都考慮到了客戶和合作夥伴資料的安全性，同時資料在他們的系統和系統之間流動。

**** SFTP:對於SFTP選項，大部分客戶選擇通過使用安全殼層(SSH)協定的安全FTP(SFTP)協定傳遞檔案。 此方法可確保在客戶系統與Adobe系統之間進行檔案加密。 對於每位客戶，我們會在SFTP伺服器上建立已擱置的下拉式方塊位置，此位置會系結至該系統上的使用者帳戶。 只有客戶的認證和特權內部系統用戶才能訪問此囚禁中的下拉框位置。 其他客戶永遠無法進入此監獄。

**** Amazon Web Services S3（透過HTTPS）:對於S3傳送選項，建議所有客戶設定其S3用戶端，使用HTTPS加密方法進行檔案傳送（這不是預設值，因此必須明確設定）。 s3cmd命令列工具以及各種主要程式設計語言可用的S3程式庫都支援HTTPS選項。 啟用此HTTPS選項後，客戶的資料會在飛往我們的系統時進行加密。 我們為每個客戶建立個別的S3儲存貯體子目錄，只能由該客戶的認證和內部系統使用者的認證存取。

要將PGP加密添加到資料檔案，請參 [閱File PGP Encryption for Inbound Data Types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)。

## 通過逸出保護資料 {#escaping-data}

請注意， [!DNL Audience Manager] 不要逸出傳出資料，以防其受到跨網站指令碼(XSS)等攻擊。 客戶有責任逸出傳入的資料。

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] 是業界的Web安全機制，可協助防範Cookie劫持和通訊協定降級攻擊。

該策略指示Web瀏覽器，一旦對給 [!DNL HTTPS] 定域進行安全調用，則不應允許該域進行後續的不安全調用([!DNL HTTP])。 這可以防止中間人攻擊，攻擊者可能會嘗試將呼叫降級為 [!DNL HTTPS] 無保護呼 [!DNL HTTP] 叫。」

此政策可改善用戶端與Adobe [Edge伺服器間的資料安](../../reference/system-components/components-edge.md) 全。

### 範例 {#hsts-example}

當嘗試存取時， `http://bank.demdex.com`會 [!DNL HSTS] 自動將要求升級至 `https://bank.demdex.com`，以防瀏覽器無法自動要求網 [!DNL HTTPS] 域。

See HTTP Strict Transport Security - Wikipedia for more information about HSTS.[](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
