---
description: Audience manager非常重視資料安全性和隱私權。 我們致力於確保系統安全，並保護您寶貴的資料。
seo-description: Audience manager非常重視資料安全性和隱私權。 我們致力於確保系統安全，並保護您寶貴的資料。
seo-title: Audience manager中的資料安全性
solution: Audience Manager
title: Audience manager中的資料安全性
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 1d606cf8ac8cf7b78a7ddf661e9a6d2ce32df71e

---


# Audience manager中的資料安全性 {#data-security}

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

**** PII資料： Audience manager合約禁止客戶和資料合作夥伴將PII資訊傳送至我們的系統。 此外，唯一使用者ID(UUID)不包含或使用PII資料做為ID產生演算法的一部分。

**** IP位址： Audience manager確實會收集IP位址。 IP位址用於資料處理和記錄匯整程式。 地理／位置查詢和定位也需要這些功能。 此外，保留的記錄檔中的所有IP位址都會在90天內模糊化。

## 資料分區 {#data-partitioning}

有助於保護個別客戶所擁有資料的程式。

**** 特徵資料分區： 您的資料（特徵、ID等）由客戶機分區。 這有助於防止不同客戶之間意外洩露資訊。 例如，Cookie中的特徵資料會依客戶劃分，並儲存在用戶端特定的子網域中。 其他Audience manager用戶端無法讀取或意外使用。 此外，儲存在中的特徵資料 [!UICONTROL Profile Cache Servers (PCS)] 也由客戶劃分。 如此可避免其他用戶端在事件呼叫或其他要求中意外使用您的資料。

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

比方說，網域會 `yourcompany.demdex.com` 傳送流量至 [!DNL DCS] via [!DNL HTTP]。 [!DNL HSTS] 升級呼叫以使 [!DNL HTTPS] 用，而所有後續 [!DNL DCS] 來自 `yourcompany.demdex.com` 的呼叫將 [!DNL HTTPS] 使用 [!DNL HTTP]。

如需 [有關HSTS的詳細資訊，請參閱HTTP嚴格傳輸安全性-](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) Wikipedia。
