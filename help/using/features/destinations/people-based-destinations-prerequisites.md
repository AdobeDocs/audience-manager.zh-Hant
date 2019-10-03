---
description: '請閱讀以下內容，以瞭解您在註冊人員型目標之前需要滿足的客戶需求。  '
seo-description: 'Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.  '
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Prerequisites and Considerations
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# Prerequisites and Considerations {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

Read below for an overview of customer requirements that you need to meet before signing up for .[!DNL People-Based Destinations]

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
1. 閱讀並簽署 [!DNL Facebook Custom Audiences] 服務條款。 To do this, go to , where  is your .`https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]``accountID`[!DNL Facebook Ad Account ID]

## Data Onboarding {#data-onboarding}

目前，每次 [!DNL People-Based Destinations] 批次傳輸中，資料擷取支援最多10個連結至一個客戶ID([!DNL CRM ID])的雜湊電子郵件地址。 Uploading more than 10 hashed email addresses linked to one customer ID causes Audience Manager to ingest 10 of them, in no specific order.

Uploading more than 10 hashed email addresses linked to one customer ID in multiple batch transfers causes Audience Manager to retain the most recent 10 email addresses added.

## 資料隱私權{#data-privacy}

雖然 [!DNL People-Based Destinations] 您可以根據您上傳的雜湊電子郵件地址來定位對象，但您仍禁止將任何直接可識別身份的訪客資訊上傳至Audience Manager。 在資料登入階段，您必須確保您打算使用的電子郵件地址已與演算法雜湊 [!DNL SHA256] 在一起。 否則，您將無法在中使用它們 [!DNL People-Based Destinations]。

## Data Hashing Versus Encryption {#data-hashing-encryption}

加密是雙向功能。 任何加密的資訊也可以使用正確的解密密鑰進行解密。 在Audience manager中加密資料會帶來嚴重風險，因為任何加密的個人識別資訊形式都可以解密。 與加密相比，加密 [!DNL People-Based Destinations] 的設計是改用雜湊資料。

雜湊是單向函式，可對輸入進行雜湊以產生獨特的結果。 通過使用適當的散列算法， [!DNL SHA256]例如，無法對散列函式進行反向操作並揭示未置亂的資訊。 您要登入Audience manager的電子郵件地址必須使用演算法雜湊 [!DNL SHA256] 處理。 如此，您就可以確保沒有未雜湊的電子郵件地址可送達Audience Manager。

## 雜湊要求 {#hashing-requirements}

散列電子郵件地址時，請務必符合下列要求：

* 從電子郵件字串中修剪所有前導和尾隨空格；範例： `johndoe@example.com`不是 `<space>johndoe@example.com<space>`;
* 在對電子郵件字串進行散列時，請務必對小寫字串進行散列；
   * 範例： `example@email.com`不是 `EXAMPLE@EMAIL.COM`;
* 請確定雜湊字串全部為小寫
   * 範例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`不是 `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Do not salt the string.

Watch the video below to understand the hashing requirements of .[!UICONTROL People-Based Destinations]

>[!VIDEO](https://video.tv.adobe.com/v/29003/?captions=chi_hant)

Adobe Experience Cloud gives you the option to hash customer IDs through the Experience Cloud ID Service. See SHA256 Hashing Support for setCustomerIDs for detailed information on how to use ECID to hash customer IDs.[](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html)

## 取得使用者權限 {#obtaining-user-permission}

Since  helps you activate first-party audience data in people-based channels, it is your responsibility to inform and obtain any necessary consents from your customers of how you will use their data for advertising or other purposes.[!DNL People-Based Destinations]

在註冊之前，請 [!DNL People-Based Destinations]務必先取得客戶的同意，再將其資訊用於廣告用途。

如果您的客戶想要退出廣告宣傳，請參閱退出管理 [](../../overview/data-security-and-privacy/opt-out-management.md) ，以取得如何阻止Audience manager進一步收集資料的詳細資訊。

## 強制執行第一方資料啟動 {#enforcing-first-party-activation}

When using , you can only use first-party data to activate audience segments in people-based channels. [!DNL People-Based Destinations]您無法在以人員為主的通道中使用任何第二方或第三方資料來啟動受眾。

## Onboard Authenticated Hashed IDs through Declared ID Targeting {#onboard-authenticated-declared-id}

有兩種方式可讓您將離線資料帶入Audience Manager [!DNL People-Based Destinations]。

* [傳送批次資料](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 至Audience Manager，以擷取雜湊的電子郵件地址。 使用此方法，您可以選擇在中使用資料庫中的散列電 [!DNL CRM] 子郵件地址 [!DNL People-Based Destinations]。 此外，使用此方法時，您也可以針對已登入的特徵來限定雜湊 [電子郵件地址](../traits/trait-qualification-reference.md)。
* 使用 [Declared ID](../declared-ids.md) ，在傳入已驗證的客戶ID時，宣告雜湊的電子郵件地址。 使用此方法時，Audience manager僅會代表您傳送經過線上驗證 [!DNL People-Based Destinations] 的使用者的雜湊電子郵件地址。 透過以人為本的管道啟動的電子郵件地址，只是宣告的ID事件呼叫中的電子郵件地址。 與客戶ID相關的其他電子郵件地址不會即時傳送。
