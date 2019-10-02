---
description: '請閱讀以下內容，以瞭解您在註冊人員型目標之前需要滿足的客戶需求。  '
seo-description: '請閱讀以下內容，以瞭解您在註冊人員型目標之前需要滿足的客戶需求。  '
seo-title: 基於人員的目標先決條件和考慮事項
solution: Audience Manager
title: Prerequisites and Considerations
translation-type: tm+mt
source-git-commit: ad9c077f538759e195a83d47e0ef36ccffa25c7e

---


# 先決條件和注意事項 {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 Nothing contained herein is legal advice. Please consult your own legal counsel for legal guidance.

Read below for an overview of customer requirements that you need to meet before signing up for .[!DNL People-Based Destinations]

>[!IMPORTANT]
> Read through this article carefully before moving on to the implementation phase.

## Signing up for People-Based Destinations {#signing-up}

[!DNL People-Based Destinations] is a premium capability that enhances your Audience Manager experience by allowing you to activate your first-party audience segments in people-based environments, by targeting your audience with customized offers on social networks or through email marketing.

Please contact your Adobe representative to take advantage of this premium feature.

## 特定合作夥伴的先決條件 {#partner-prerequisites}

### [!DNL Facebook]

在您可以用 [!DNL People-Based Destinations] 來傳送第一方對象區段至之 [!DNL Facebook]前，請確定您符合下列需求：

1. Your  user account must have the Manage campaigns permission enabled for the Ad account that you plan to use.[!DNL Facebook]****
1. 將 **Adobe Experience cloud商業帳戶新增為廣告合作夥伴**[!DNL Facebook Ad Account]。 使用 `business ID=206617933627973`. 如需詳 [細資訊，請參閱將合作夥伴新增至您的業務經理](https://www.facebook.com/business/help/708679622611131) 。
   >[!IMPORTANT]
   > When configuring the permissions for Adobe Experience Cloud, you must enable the Manage campaigns permission. ****&#x200B;這是整合的必 [!DNL People-Based Destinations] 要項。
1. Read and sign the [!DNL Facebook Custom Audiences] Terms of Service. 若要這麼做，請前 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`往您的 `accountID` 位置 [!DNL Facebook Ad Account ID]。

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
* 在對電子郵件字串進行散列時，請務必對小寫字串進行散列；
   * 範例： `example@email.com`不是 `EXAMPLE@EMAIL.COM`;
* Make sure the hashed string is all lowercase
   * 範例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`不是 `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Do not salt the string.

Adobe Experience cloud可讓您選擇透過Experience Cloud ID服務散列客戶ID。 如需如 [何使用ECID來雜湊客戶ID的詳細資訊，請參閱SHA256 Hashing Support for setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) 。

## Obtaining User Permission {#obtaining-user-permission}

Since  helps you activate first-party audience data in people-based channels, it is your responsibility to inform and obtain any necessary consents from your customers of how you will use their data for advertising or other purposes.[!DNL People-Based Destinations]

Before you sign up for , make sure to obtain your customers' consent before using their information for advertising purposes.[!DNL People-Based Destinations]

In case your customers wish to opt-out of advertising campaigns, see Opt-out Management for details on how to stop Audience Manager from collecting data any further.[](../../overview/data-security-and-privacy/opt-out-management.md)

## Enforcing First-Party Data Activation {#enforcing-first-party-activation}

When using , you can only use first-party data to activate audience segments in people-based channels. [!DNL People-Based Destinations]You cannot use any second- or third-party data for audience activation in people-based channels.

## Onboard Authenticated Hashed IDs through Declared ID Targeting {#onboard-authenticated-declared-id}

There are two ways you can bring your offline data to Audience Manager for .[!DNL People-Based Destinations]

* [傳送批次資料](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 至Audience Manager，以擷取雜湊的電子郵件地址。 With this method, you can choose to use the hashed email addresses from your  database in . [!DNL CRM][!DNL People-Based Destinations]Additionally, when using this method, you can also qualify the hashed email addresses for onboarded traits.[](../traits/trait-qualification-reference.md)
* Use Declared IDs to declare hashed email addresses when passing in authenticated customer IDs. [](../declared-ids.md)使用此方法時，Audience manager僅會代表您傳送經過線上驗證 [!DNL People-Based Destinations] 的使用者的雜湊電子郵件地址。 透過以人為本的管道啟動的電子郵件地址，只是宣告的ID事件呼叫中的電子郵件地址。 與客戶ID相關的其他電子郵件地址不會即時傳送。
