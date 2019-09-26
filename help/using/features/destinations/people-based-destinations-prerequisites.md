---
description: '請閱讀以下內容，以瞭解您在註冊人員型目標之前需要滿足的客戶需求。  '
seo-description: '請閱讀以下內容，以瞭解您在註冊人員型目標之前需要滿足的客戶需求。  '
seo-title: 基於人員的目標先決條件和考慮事項
solution: Audience Manager
title: 先決條件和注意事項
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

---


# 先決條件和注意事項 {#prerequisites-considerations}

請閱讀以下內容，以瞭解您在註冊前必須符合的客戶需求概觀 [!DNL People-Based Destinations]。

>[!IMPORTANT]
> 在進入實施階段之前，請仔細閱讀本文章。

## 註冊以人為本的目的地 {#signing-up}

[!DNL People-Based Destinations] 是一種進階功能，可讓您在以人為本的環境中啟用您的第一方受眾細分，透過社交網路或電子郵件行銷鎖定您的受眾，借此增強您的Audience Manager體驗。

請連絡您的Adobe代表，以利用這項優質功能。

## 特定合作夥伴的先決條件 {#partner-prerequisites}

### [!DNL Facebook]

在您可以用 [!DNL People-Based Destinations] 來傳送第一方對象區段至之 [!DNL Facebook]前，請確定您符合下列需求：

1. 您 [!DNL Facebook] 的使用者帳戶必須為您 **** 計畫使用的廣告帳戶啟用「管理促銷活動」權限。
1. 將 **Adobe Experience cloud商業帳戶新增為廣告合作夥伴**[!DNL Facebook Ad Account]。 使用 `business ID=206617933627973`. 如需詳 [細資訊，請參閱將合作夥伴新增至您的業務經理](https://www.facebook.com/business/help/708679622611131) 。
   >[!IMPORTANT]
   > 設定Adobe Experience cloud的權限時，您必須啟用「管理促銷 **活動** 」權限。 這是整合的必 [!DNL People-Based Destinations] 要項。
1. 閱讀並簽署 [!DNL Facebook Custom Audiences] 服務條款。 若要這麼做，請前 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`往您的 `accountID` 位置 [!DNL Facebook Ad Account ID]。

## 資料上線 {#data-onboarding}

目前，每次 [!DNL People-Based Destinations] 批次傳輸中，資料擷取支援最多10個連結至一個客戶ID([!DNL CRM ID])的雜湊電子郵件地址。 上傳連結至一個客戶ID的10個以上雜湊電子郵件地址會導致Audience manager以無特定順序收錄其中10個。

在多個批次傳輸中上傳超過10個雜湊電子郵件地址，連結至一個客戶ID，會導致Audience manager保留新增的10個最新電子郵件地址。

## 資料隱私權{#data-privacy}

雖然 [!DNL People-Based Destinations] 您可以根據您上傳的雜湊電子郵件地址來定位對象，但您仍禁止將任何直接可識別身份的訪客資訊上傳至Audience Manager。 在資料登入階段，您必須確保您打算使用的電子郵件地址已與演算法雜湊 [!DNL SHA256] 在一起。 否則，您將無法在中使用它們 [!DNL People-Based Destinations]。

## 資料散列與加密 {#data-hashing-encryption}

加密是雙向功能。 任何加密的資訊也可以使用正確的解密密鑰進行解密。 在Audience manager中加密資料會帶來嚴重風險，因為任何加密的個人識別資訊形式都可以解密。 與加密相比，加密 [!DNL People-Based Destinations] 的設計是改用雜湊資料。

雜湊是單向函式，可對輸入進行雜湊以產生獨特的結果。 通過使用適當的散列算法， [!DNL SHA256]例如，無法對散列函式進行反向操作並揭示未置亂的資訊。 您要登入Audience manager的電子郵件地址必須使用演算法雜湊 [!DNL SHA256] 處理。 如此，您就可以確保沒有未雜湊的電子郵件地址可送達Audience Manager。

## 雜湊要求 {#hashing-requirements}

散列電子郵件地址時，請務必符合下列要求：

* 從電子郵件字串中修剪所有前導和尾隨空格；範例： `johndoe@example.com`不是 `<space>johndoe@example.com<space>`;
* 請確定雜湊字串全部為小寫；範例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`不是 `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* 別用鹽鹽。

Adobe Experience cloud可讓您選擇透過Experience Cloud ID服務散列客戶ID。 如需如 [何使用ECID來雜湊客戶ID的詳細資訊，請參閱SHA256 Hashing Support for setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) 。

## 取得使用者權限 {#obtaining-user-permission}

由於 [!DNL People-Based Destinations] 協助您在以人為本的通道中啟用第一方受眾資料，因此您有責任告知客戶並取得客戶如何將其資料用於廣告或其他目的的必要同意。

在註冊之前，請 [!DNL People-Based Destinations]務必先取得客戶的同意，再將其資訊用於廣告用途。

如果您的客戶想要退出廣告宣傳，請參閱退出管理 [](../../overview/data-security-and-privacy/opt-out-management.md) ，以取得如何阻止Audience manager進一步收集資料的詳細資訊。

## 強制執行第一方資料啟動 {#enforcing-first-party-activation}

使用時， [!DNL People-Based Destinations]您只能使用第一方資料，在以人為本的通道中啟用受眾細分。 您無法在以人員為主的通道中使用任何第二方或第三方資料來啟動受眾。

## 透過宣告的ID定位的板載驗證雜湊ID {#onboard-authenticated-declared-id}

有兩種方式可讓您將離線資料帶入Audience Manager [!DNL People-Based Destinations]。

* [傳送批次資料](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 至Audience Manager，以擷取雜湊的電子郵件地址。 使用此方法，您可以選擇在中使用資料庫中的散列電 [!DNL CRM] 子郵件地址 [!DNL People-Based Destinations]。 此外，使用此方法時，您也可以針對已登入的特徵來限定雜湊 [電子郵件地址](../traits/trait-qualification-reference.md)。
* 使用 [Declared ID](../declared-ids.md) ，在傳入已驗證的客戶ID時，宣告雜湊的電子郵件地址。 使用此方法時，Audience manager僅會代表您傳送經過線上驗證 [!DNL People-Based Destinations] 的使用者的雜湊電子郵件地址。 透過以人為本的管道啟動的電子郵件地址，只是宣告的ID事件呼叫中的電子郵件地址。 與客戶ID相關的其他電子郵件地址不會即時傳送。
