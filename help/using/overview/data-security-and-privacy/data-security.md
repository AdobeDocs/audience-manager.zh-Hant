---
description: Audience manager非常重視資料安全性和隱私權。 我們致力於確保系統安全，並保護您寶貴的資料。
seo-description: Audience manager非常重視資料安全性和隱私權。 我們致力於確保系統安全，並保護您寶貴的資料。
seo-title: Data Security
solution: Audience Manager
title: Data Security
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 34884e3212d50237c73fdc6aa163d90c29a642f5

---


# 資料安全性 {#data-security}

Audience Manager takes data security and privacy very seriously. 我們致力於確保系統安全，並保護您寶貴的資料。

Audience manager的安全性實務包括外部和內部稽核、活動記錄、訓練和其他程式，這些程式旨在協助保護我們的系統和您的寶貴資料。 我們相信，安全的產品有助於建立和維護客戶對我們的信任。

In Audience Manager, we think about security in three main categories:

| Security Type | Provides Support For |
|---|---|
| **Information security** | Enterprise-level authentication, encryption, and data storage practices |
| **Data leakage/transparency** | Deep and actionable insight into on-site activities that constitute or contribute to data leakage |
| **Process/policy enhancements** | 客戶，透過使用隱私權與資料安全的業界最佳實務 |

## Systems, Training, and Access {#systems-training-access}

Processes that help keep our system and your data secure.

**** External Security Validation:  Audience Manager tests security on an annual and quarterly basis.

* 每年：Audience manager每年會接受獨立第三方公司的全面普及率測試。 此測試旨在識別應用程式中的安全性弱點。 這些測試包括掃描跨網站指令碼、插入SQL、表單參數控制以及其他應用程式層級的弱點。
* 每季：每季一次，內部團隊會檢查安全性弱點。 這些測試包括網路掃描開啟埠和服務漏洞。

**** 系統安全性： 為協助確保資料安全且私密，Audience Manager:

* 阻止來自未授權IP位址的請求。
* 保護防火牆、 VPN和虛擬專用雲儲存後的資料。
* 使用觸發式稽核記錄來追蹤客戶和控制資訊資料庫的變更。 這些記錄檔會追蹤資料庫層級的所有變更，包括進行變更的使用者ID和IP位址。

**** 安全資產： Audience manager有專屬的網路營運團隊，負責監控防火牆和入侵偵測裝置。 只有重要人員才能存取我們的安全技術和資料。

**** 安全性訓練： 在內部，我們對安全性的承諾延伸到負責我們產品的開發人員。 Adobe為開發人員提供如何建立安全應用程式與服務的正式訓練。

**** 安全訪問： Audience manager需要強式密碼才能登入系統。 請參 [閱密碼要求](../../reference/password-requirements.md)。

## 隱私權與個人識別資訊(PII) {#pii}

有助於確保個人資訊安全的流程。 For additional privacy information, see the Adobe Privacy Center.[](https://www.adobe.com/privacy/advertising-services.html)

**** PII資料： Audience manager合約禁止客戶和資料合作夥伴將PII資訊傳送至我們的系統。 此外，唯一使用者ID(UUID)不包含或使用PII資料做為ID產生演算法的一部分。

**** IP位址： Audience manager確實會收集IP位址。 IP位址用於資料處理和記錄匯整程式。 地理／位置查詢和定位也需要這些功能。 此外，保留的記錄檔中的所有IP位址都會在90天內模糊化。

## Data Partitioning {#data-partitioning}

Processes that help protect data owned by individual clients.

**** 特徵資料分區： 您的資料（特徵、ID等）由客戶機分區。 這有助於防止不同客戶之間意外洩露資訊。 For example, trait data in cookies is partitioned by customer and stored in a client-specific sub-domain. It cannot be read or used accidentally by another Audience Manager client. Furthermore, trait data stored in the  is also partitioned by customer. [!UICONTROL Profile Cache Servers (PCS)]如此可避免其他用戶端在事件呼叫或其他要求中意外使用您的資料。

**** 報告中的資料分區： 客戶端ID是所有報表表格中識別索引鍵的一部分，報表查詢會依ID篩選。 This helps prevent your data from appearing in the reports of another Audience Manager customer.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager supports two main methods of transferring S2S on-boarded data files to our systems:

Both methods are designed with the security of our customer and partner data in mind while data is in flight between their systems and our system.

**** SFTP: For the SFTP option, most customers choose to deliver files via the Secure FTP (SFTP) protocol, which uses the Secure Shell (SSH) protocol. This method ensures that files are encrypted while in flight between the customer's systems and Adobe's system. For each customer, we create a jailed drop-box location on our SFTP servers, which is tied to a user account on that system. Only the customer's credentialed and privileged internal system users can access this jailed drop-box location. This jail is never accessible to other customers.

**** Amazon Web Services S3（透過HTTPS）:對於S3傳送選項，建議所有客戶設定其S3用戶端，使用HTTPS加密方法進行檔案傳送（這不是預設值，因此必須明確設定）。 s3cmd命令列工具以及各種主要程式設計語言可用的S3程式庫都支援HTTPS選項。 啟用此HTTPS選項後，客戶的資料會在飛往我們的系統時進行加密。 我們為每個客戶建立個別的S3儲存貯體子目錄，只能由該客戶的認證和內部系統使用者的認證存取。

要將PGP加密添加到資料檔案，請參 [閱File PGP Encryption for Inbound Data Types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)。

## 通過逸出保護資料 {#escaping-data}

請注意， [!DNL Audience Manager] 不要逸出傳出資料，以防其受到跨網站指令碼(XSS)等攻擊。 客戶有責任逸出傳入的資料。

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] 是業界的Web安全機制，可協助防範Cookie劫持和通訊協定降級攻擊。

該策略指示Web瀏覽器，一旦對給 [!DNL HTTPS] 定域進行安全調用，則不應允許該域進行後續的不安全調用([!DNL HTTP])。 這可以防止中間人攻擊，攻擊者可能會嘗試將呼叫降級為 [!DNL HTTPS] 無保護呼 [!DNL HTTP] 叫。」

此政策可改善用戶端與Adobe [Edge伺服器間的資料安](../../reference/system-components/components-edge.md) 全。

### 範例 {#hsts-example}

比方說，網域會 `yourcompany.demdex.com` 傳送流量至 [!DNL DCS] via [!DNL HTTP]。 [!DNL HSTS] 升級呼叫以使 [!DNL HTTPS] 用，而所有後續 [!DNL DCS] 來自 `yourcompany.demdex.com` 的呼叫將 [!DNL HTTPS] 使用 [!DNL HTTP]。

如需 [有關HSTS的詳細資訊，請參閱HTTP嚴格傳輸安全性-](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) Wikipedia。
