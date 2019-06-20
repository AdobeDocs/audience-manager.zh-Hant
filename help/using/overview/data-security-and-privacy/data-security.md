---
description: Audience Manager十分重視資料安全性和隱私權。我們努力確保我們的系統安全並保護您的寶貴資料。
seo-description: Audience Manager十分重視資料安全性和隱私權。我們努力確保我們的系統安全並保護您的寶貴資料。
seo-title: 資料安全性
solution: Audience Manager
title: 資料安全性
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Security {#data-security}

Audience Manager十分重視資料安全性和隱私權。我們努力確保我們的系統安全並保護您的寶貴資料。

Audience Manager的安全性實務包括外部和內部稽核、活動記錄、培訓及其他旨在協助保護我們的系統及您寶貴資料的程序。我們相信一款安全的產品有助於建構和維護客戶信任的地方。

在Audience Manager中，我們考慮三個主要類別的安全性：

| 安全性類型 | 提供支援 |
|---|---|
| **資訊安全性** | 企業級驗證、加密和資料儲存實務 |
| **資料洩漏/透明度** | 深入且可採取行動，深入瞭解構成或促進資料流失的活動 |
| **流程/政策增強功能** | 客戶使用業界最佳隱私權與資料安全性實務 |

## Systems, Training, and Access {#systems-training-access}

有助於確保我們的系統和資料安全的流程。

**外部安全性驗證：** Audience Manager會在每年和每季測試安全性。

* 每年：Audience Manager一年一次，會通過獨立第三方公司進行的完整滲透測試。測試旨在識別應用程式中的安全性弱點。測試包括掃描跨網站指令碼、SQL整合、表單參數控制以及其他應用程式層級弱點。
* 每季：每季一次，內部團隊會檢查是否有安全性弱點。這些測試包括開啓連接埠和服務弱點的網路掃描。

**系統安全性：** 為協助確保資料安全無虞，Audience Manager：

* 封鎖來自未授權IP位址的請求。
* 保護防火牆、VPN以及虛擬私人雲端儲存空間背後的資料。
* 使用觸發式稽核記錄功能追蹤客戶和控制資訊資料庫中的變更。這些記錄會追蹤資料庫層級的所有變更，包括進行變更的使用者ID和IP位址。

**安全性資產：** Audience Manager有專門的網路營運團隊，可監視防火牆和入侵偵測裝置。只有關鍵人員才能存取我們的安全技術和資料。

**安全性培訓：** 在內部，我們對安全性的承諾延伸給開發人員的開發人員。Adobe針對開發人員提供有關如何建立安全應用程式和服務的正式訓練。

**安全存取：** Audience Manager需要使用強式密碼才能登入系統。See [password requirements](../../reference/password-requirements.md).

## Privacy and Personally Identifiable Information (PII) {#pii}

有助於確保個人資訊安全的流程。For additional privacy information, see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

**PII資料：** Audience Manager合約禁止客戶和資料合作夥伴將PII資訊傳送至我們的系統。此外，唯一使用者ID(UUID)不包含或使用PII資料做為ID產生演算法的一部分。

**IP位址：** Audience Manager會收集IP位址。IP位址用於資料處理和記錄匯總程序。它們也需要地理/位置查閱和定位。此外，保留記錄檔中的所有IP位址都會在90天內模糊化。

## Data Partitioning {#data-partitioning}

有助於保護個別客戶擁有資料的程序。

**特徵資料分區：** 您的資料(特性、ID等)由用戶端劃分。這有助於防止不同用戶端之間的意外資訊曝光。例如，Cookie中的特徵資料是由客戶分割，並儲存在用戶端特定子網域中。Audience Manager客戶不能意外讀取或使用它。Furthermore, trait data stored in the [!UICONTROL Profile Cache Servers (PCS)] is also partitioned by customer. 這可防止其他用戶端意外使用事件呼叫或其他請求中的資料。

**報表中的資料分區：** 用戶端ID是所有報告表格和報表查詢中的識別索引鍵，會依ID篩選。這有助於防止資料出現在其他Audience Manager客戶的報表中。

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager支援兩種主要方法，將S2S在機櫃中的資料檔案傳輸至我們的系統：

這兩種方法都是隨著客戶和合作夥伴資料的安全而設計，同時資料在其系統和系統之間流通。

**SFTP：** 對於SFTP選項，大部分的客戶選擇透過Secure FTP(SFTP)通訊協定(使用Secure Shell(SSH)通訊協定)傳送檔案。此方法可確保檔案在客戶系統與Adobe系統之間進行時加密。對於每位客戶，我們會在SFTP伺服器上建立一個jamed drop-box位置，此位置會系結至該系統上的使用者帳戶。只有客戶的認證和權限內部系統使用者才能存取此電子郵件放置位置的位置。其他客戶無法存取此監獄。

**Amazon Web Services S透過HTTPS：** 對於S傳送選項，我們建議所有客戶設定其S用戶端以使用HTTPS加密方法進行檔案傳輸(這不是預設值，所以必須明確配置)。s3cmd命令列工具以及各種主要程式設計語言提供的S程式庫都支援HTTPS選項。啓用此HTTPS選項後，客戶的資料就會在進入我們的系統時加密。對於每個客戶，我們建立個別的S儲存貯體子目錄，只能由該客戶的認證和內部系統使用者的認證存取。

To add PGP encryption to your data files, see [File PGP Encryption for Inbound Data Types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Protecting Data by Escaping {#escaping-data}

Note that [!DNL Audience Manager] does not escape outgoing data to secure it against possible cross-site scripting (XSS), etc. 客戶有責任逸出接收的資料。
