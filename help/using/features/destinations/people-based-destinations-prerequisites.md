---
description: '請參閱下方以取得您需要符合的客戶需求概述，以便在註冊人員目標之前進行註冊。  '
seo-description: '請參閱下方以取得您需要符合的客戶需求概述，以便在註冊人員目標之前進行註冊。  '
seo-title: 基於人員的目標位置與考量事項
solution: Audience Manager
title: 先決條件與考量事項
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# 先決條件與考量事項 {#prerequisites-considerations}

請參閱下方以取得您需要在註冊之前符合客戶需求的概述 [!DNL People-Based Destinations]。

>[!IMPORTANT]
> 請仔細閱讀本文章，然後再移至實作階段。

## 註冊以符合人員目標 {#signing-up}

[!DNL People-Based Destinations] 是一種高階功能，可讓您在以人員為基礎的環境中啓用第一方受眾細分，透過社交網路或電子郵件行銷的自訂優惠鎖定受眾，借此強化您的Audience Manager體驗。

如需如何註冊的詳細資訊，請與您的Adobe銷售代表聯絡 [!DNL People-Based Destinations]。

## 合作夥伴專屬必要條件 {#partner-prerequisites}

### [!DNL Facebook]

您必須先符合下列需求，才能將 [!DNL People-Based Destinations][!DNL Facebook]讀者區段傳送給您：

1. [!DNL Facebook] 您的使用者帳戶必須已針對您打算使用的廣告帳戶啓用 **「管理促銷活動** 」權限。
1. 將 **Adobe Experience Cloud** 業務帳戶新增為您 [!DNL Facebook Ad Account]的廣告合作夥伴。使用 `business ID=206617933627973`. 如需詳細資訊，請參閱 [新增合作夥伴給您的業務經理](https://www.facebook.com/business/help/708679622611131) 。
   >[!IMPORTANT]
   > 設定Adobe Experience Cloud的權限時，您必須啓用 **「管理促銷活動** 」權限。這是 [!DNL People-Based Destinations] 整合的必要項目。
1. 閱讀並簽署服務 [!DNL Facebook Custom Audiences] 條款。`https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]``accountID`[!DNL Facebook Ad Account ID]要做到這一點，請前往這裡。

## 資料倉庫 {#data-onboarding}

[!DNL People-Based Destinations] 目前的資料擷取支援每個批次傳輸，最多可支援10個連結至一個客戶ID([!DNL CRM ID])的雜湊電子郵件地址。上傳超過10個連結至一個客戶ID的雜湊電子郵件地址，會導致Audience Manager收錄其中10個，並無特定順序。

在多次批次傳輸中上傳超過10個連結至一個客戶ID的雜湊電子郵件地址，會導致Audience Manager保留最近新增10個電子郵件地址。

## 資料隱私權{#data-privacy}

雖然 [!DNL People-Based Destinations] 允許您根據電子郵件地址鎖定受眾，但無法直接識別可直接識別的訪客資訊。在資料上線階段中，您必須確保使用 [!DNL SHA256] 演算法的電子郵件地址被雜湊化。否則，您將無法使用 [!DNL People-Based Destinations]它們。

## 資料雜湊與加密 {#data-hashing-encryption}

加密是雙向的函數。您也可以使用正確的解密金鑰解密任何加密資訊。在Audience Manager環境中加密資料會造成嚴重的隱私風險，因為任何加密的個人資訊形式也可以解密，揭露敏感的客戶資料。而非加密， [!DNL People-Based Destinations] 則可用來處理雜湊資料，以保護您用於定位的客戶資料。

雜湊是單向函數，可雜湊輸入產生獨特結果。使用適當的雜湊演算法，就 [!DNL SHA256]無法反轉雜湊函數，並顯示雜亂的資訊。您登入Audience Manager的電子郵件地址必須與 [!DNL SHA256] 演算法雜湊。如此，就不會將任何個人識別資訊送達Audience Manager，確保客戶資料安全無虞。

## 雜湊需求 {#hashing-requirements}

當電子郵件地址雜湊時，請務必符合下列要求：

* 從電子郵件字串修剪所有前導和尾隨空格；範例： `johndoe@example.com``<space>johndoe@example.com<space>`而不是；
* 確定雜湊字串全部小寫；範例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149``55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`而不是；
* 請勿鹽漬字串。

Adobe Experience Cloud可讓您選擇透過Experience Cloud ID服務雜湊客戶ID。如需如何使用ECID至雜湊客戶ID的詳細資訊，請參閱 [SHA256](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) 雜湊支援setCustomerIDs。

## 取得使用者權限 {#obtaining-user-permission}

由於 [!DNL People-Based Destinations] 幫助您在以人員為主的通路中啓用第一方受眾資料，您有責任告知客戶您將如何運用其資料作為廣告用途。

在您註冊之前 [!DNL People-Based Destinations]，請務必先取得客戶的同意，再將其資訊用於廣告用途。

如果客戶希望選擇退出廣告促銷活動，請參閱 [退出管理](../../overview/data-security-and-privacy/opt-out-management.md) ，瞭解如何阻止Audience Manager進一步收集資料。

## 強制第一方資料啓動 {#enforcing-first-party-activation}

在使用 [!DNL People-Based Destinations]時，您只能使用第一方資料在以人員為基礎的管道中啓動受眾細分。您無法使用任何第二方或第三方資料來啓動受眾頻道的受眾。

## 透過宣告的ID定位登入驗證雜湊ID {#onboard-authenticated-declared-id}

有兩種方式可讓您將離線資料帶入Audience Manager [!DNL People-Based Destinations]。

* [將批次資料](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 傳送至Audience Manager，以收錄雜湊電子郵件地址。使用此方法，您可以使用 [!DNL CRM] 資料庫中的所有雜湊電子郵件地址 [!DNL People-Based Destinations]。此外，使用此方法時，您也可以符合 [已登錄特性的雜湊電子郵件地址](../traits/trait-qualification-reference.md)。
* 在通過驗證的客戶ID時，使用 [「宣告的ID](../declared-ids.md) 」宣告雜湊電子郵件地址。使用此方法時，Audience Manager只會傳送已 [!DNL People-Based Destinations] 通過線上驗證之使用者的雜湊電子郵件地址。透過Facebook啓動的電子郵件地址僅為宣告ID事件呼叫中的一個。與客戶ID相關聯的其他電子郵件地址不會即時傳送。
