---
description: '請閱讀以下內容，以瞭解您在註冊人員型目標之前需要滿足的客戶需求。  '
seo-description: '請閱讀以下內容，以瞭解您在註冊人員型目標之前需要滿足的客戶需求。  '
seo-title: 基於人員的目標先決條件和考慮事項
solution: Audience Manager
title: 必要條件和考量事項
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: 2e32f9ebff487ae8dfb2088ec1bbfcea1daa00a1
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 3%

---


# 必要條件和考量事項 {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

請閱讀以下內容，以瞭解您在註冊前必須符合的客戶需求概觀 [!UICONTROL People-Based Destinations]。

>[!IMPORTANT]
> 在進入實施階段之前，請仔細閱讀本文章。

## 註冊 [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] 是一種進階功能，可讓您在以人為本的環境中啟用您的第一方受眾細分，透過社交網路或電子郵件行銷鎖定您的受眾，從而增強您的Audience Manager體驗。

請連絡您的Adobe代表，以利用這項優質功能。

## 特定合作夥伴的先決條件 {#partner-prerequisites}

### [!DNL Facebook]

請務必符 [!UICONTROL People-Based Destinations] 合下列要求，才能 [!UICONTROL segments] 用 [!DNL Facebook]來傳送第一方對象：

1. 您 [!DNL Facebook] 的使用者帳戶必須為您 **** 計畫使用的廣告帳戶啟用「管理促銷活動」權限。
2. Add the **Adobe Experience Cloud** business account as an advertising partner in your [!DNL Facebook Ad Account]. 使用 `business ID=206617933627973`。See [Add Partners to Your Business Manager](https://www.facebook.com/business/help/1717412048538897) for details.
   >[!IMPORTANT]
   > When configuring the permissions for Adobe Experience Cloud, you must enable the **Manage campaigns** permission. 這是進行 [!UICONTROL People-Based Destinations] 整合的必要權限。
3. 閱讀並簽署 [!DNL Facebook Custom Audiences] 服務條款。 若要完成此操作，請前往 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

### [!DNL LinkedIn]

在您可以用 [!UICONTROL People-Based Destinations] 來傳送第一方對象區段至之前 [!DNL LinkedIn]，請確定您的 [!DNL LinkedIn Campaign Manager] 帳戶具有或 [!DNL Creative Manager] 更高的權限層級。

如要瞭解如何編輯您的 [!DNL LinkedIn Campaign Manager] 使用者權限，請參 [閱LinkedIn檔案中的「新增、編輯及移除廣告帳戶的使用者權限](https://www.linkedin.com/help/lms/answer/5753) 」。

如需 [視訊指示，請參閱瞭解和設定LinkedIn以人為本的目的地](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) 。

### [!DNL Google Customer Match]

您必須先將 [!UICONTROL People-Based Destinations] 您新增至其允許清單，才能使用將第一方 [!DNL Google Customer Match] 對象區 [!DNL Google] 段傳送至目的地。

請連絡您 [!DNL Google] 的代表，並依照使用客戶符合合作夥伴中所述的 [允許清單指示來上傳您的資料](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507)[!DNL Google] 檔案。

完成此程式後，您可以建立 [!UICONTROL People-Based Destination]。

## 資料上線 {#data-onboarding}

目前，每次 [!UICONTROL People-Based Destinations] 批次傳輸中，資料擷取支援最多10個連結至一個客戶ID([!DNL CRM ID])的雜湊電子郵件地址。 上傳連結至一個客戶ID的10個以上雜湊電子郵件地址會導致Audience Manager以無特定順序收錄其中10個。

在多個批次傳輸中上傳超過10個雜湊電子郵件地址，連結至一個客戶ID，會導致Audience Manager保留新增的10個最新電子郵件地址。

## 資料隱私權{#data-privacy}

雖然 [!UICONTROL People-Based Destinations] 您可以根據您上傳的雜湊電子郵件地址來定位對象，但您仍禁止將任何直接可識別身份的訪客資訊上傳至Audience Manager。 在資料登入階段，您必須確保您打算使用的電子郵件地址已與演算法雜湊 [!DNL SHA256] 在一起。 否則，您將無法在中使用它們 [!UICONTROL People-Based Destinations]。

## 資料散列與加密 {#data-hashing-encryption}

加密是雙向功能。 任何加密的資訊也可以使用正確的解密密鑰進行解密。 在Audience Manager中加密資料會帶來嚴重風險，因為任何加密的個人識別資訊形式都可以解密。 與加密相比，加密 [!UICONTROL People-Based Destinations] 的設計是改用雜湊資料。

雜湊是單向函式，可對輸入進行雜湊以產生獨特的結果。 通過使用適當的散列算法， [!DNL SHA256]例如，無法對散列函式進行反向操作並揭示未置亂的資訊。 您要登入Audience Manager的電子郵件地址必須使用演算法雜湊 [!DNL SHA256] 處理。 如此，您就可以確保沒有未雜湊的電子郵件地址可送達Audience Manager。

## 雜湊要求 {#hashing-requirements}

散列電子郵件地址時，請務必符合下列要求：

* 從電子郵件字串中修剪所有前導和尾隨空格；範例： `johndoe@example.com`，不是 `<space>johndoe@example.com<space>`;
* 在對電子郵件字串進行散列時，請務必對小寫字串進行散列；
   * 範例： `example@email.com`，不是 `EXAMPLE@EMAIL.COM`;
* 請確定雜湊字串全部為小寫
   * 範例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`，不是 `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* 別用鹽鹽。

請觀看以下影片，瞭解其雜湊要求 [!UICONTROL People-Based Destinations]。

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud可讓您選擇透過雜湊客戶ID [!DNL Adobe Experience Platform Identity Service (ECID)]。 如需如 [何使用ECID來雜湊客戶ID的詳細資訊，請參閱SHA256 Hashing Support for setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) 。

## 取得使用者權限 {#obtaining-user-permission}

由於 [!UICONTROL People-Based Destinations] 協助您在以人為本的通道中啟用第一方受眾資料，因此您有責任告知客戶並取得客戶如何將其資料用於廣告或其他目的的必要同意。

在註冊之前，請 [!UICONTROL People-Based Destinations]務必先取得客戶的同意，再將其資訊用於廣告用途。

如果您的客戶想要退出廣告宣傳，請參閱退出管理 [](../../overview/data-security-and-privacy/data-privacy-requests.md) ，以取得如何阻止Audience Manager進一步收集資料的詳細資訊。

## 強制執行第一方資料啟動 {#enforcing-first-party-activation}

使用時， [!UICONTROL People-Based Destinations]您只能使用第一方資料，在以人為本的通道中啟用受眾細分。 您無法在以人員為主的通道中使用任何第二方或第三方資料來啟動受眾。

使用時， [!UICONTROL People-Based Destinations]請使用「資 [料匯出控制」來標](../data-export-controls.md) 示您的 [!UICONTROL data sources][!UICONTROL destinations] 標籤，並依照目標平台和資料提供者的准則和要求。

## 透過宣告的ID定位的板載驗證雜湊ID {#onboard-authenticated-declared-id}

有兩種方式可將離線資料帶入 Audience Manager 中以用於[!UICONTROL People-Based Destinations]。

* [傳送批次資料](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 至Audience Manager，以擷取雜湊的電子郵件地址。 使用此方法，您可以選擇在中使用資料庫中的散列電 [!DNL CRM] 子郵件地址 [!UICONTROL People-Based Destinations]。 此外，使用此方法時，您也可以針對已登入的特徵來限定雜湊 [電子郵件地址](../traits/trait-and-segment-qualification-reference.md)。
* Use [Declared IDs](../declared-ids.md) to declare hashed email addresses when passing in authenticated customer IDs. When using this method, Audience Manager, on your behalf, only sends to [!UICONTROL People-Based Destinations] the hashed email addresses from users who have authenticated online. 透過以人為本的管道啟動的電子郵件地址，只是宣告的ID事件呼叫中的電子郵件地址。 與客戶ID相關的其他電子郵件地址不會即時傳送。
