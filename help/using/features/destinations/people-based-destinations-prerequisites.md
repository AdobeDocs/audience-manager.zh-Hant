---
description: '註冊以人物為基礎的目的地前，您需要符合的客戶需求概觀，請參閱下文。  '
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: 必要條件和考量事項
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: bb0bc62b139917bbf6429bc92a85f8a5010cbebe
workflow-type: tm+mt
source-wordcount: '964'
ht-degree: 4%

---

# 必要條件和考量事項 {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含的產品檔案旨在引導您完成此功能的設定與使用。 這裡沒有任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

請閱讀以下概述，了解您在註冊[!UICONTROL People-Based Destinations]之前需要滿足的客戶需求。

>[!IMPORTANT]
> 請先仔細閱讀本文章，再繼續進行實作階段。

## 註冊[!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] 是一項進階功能，可讓您在以人物為基礎的環境中，透過社交網路上的自訂選件或透過電子郵件行銷來鎖定您的對象，啟動您的第一方對象區段，進而增強您的Audience Manager體驗。

請連絡您的Adobe代表，以利用此進階功能。

## 特定於合作夥伴的先決條件 {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

使用[!UICONTROL People-Based Destinations]將第一方對象[!UICONTROL segments]傳送至[!DNL Facebook]之前，請務必符合下列要求：

1. 您的[!DNL Facebook]使用者帳戶必須為您打算使用的廣告帳戶啟用&#x200B;**管理促銷活動**&#x200B;權限。
2. 將&#x200B;**Adobe Experience Cloud**&#x200B;商業帳戶新增為[!DNL Facebook Ad Account]中的廣告合作夥伴。 使用 `business ID=206617933627973`。有關詳細資訊，請參閱[將合作夥伴添加到您的Business Manager](https://www.facebook.com/business/help/1717412048538897)。
   >[!IMPORTANT]
   > 設定Adobe Experience Cloud的權限時，您必須啟用&#x200B;**管理促銷活動**&#x200B;權限。 這是進行 [!UICONTROL People-Based Destinations] 整合的必要權限。
3. 閱讀並簽署[!DNL Facebook Custom Audiences]服務條款。 若要完成此操作，請前往 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

### [!DNL LinkedIn] {#linkedin}

使用[!UICONTROL People-Based Destinations]將第一方對象區段傳送至[!DNL LinkedIn]之前，請確定您的[!DNL LinkedIn Campaign Manager]帳戶具有[!DNL Creative Manager]或更高的權限層級。

若要了解如何編輯您的[!DNL LinkedIn Campaign Manager]使用者權限，請參閱LinkedIn檔案中的[新增、編輯及移除Advertising帳戶的使用者權限](https://www.linkedin.com/help/lms/answer/5753)。

如需視訊指示，請參閱[了解和設定LinkedIn以人物為基礎的目的地](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) 。

### [!DNL Google Customer Match] {#gcm}

使用[!UICONTROL People-Based Destinations]將第一方受眾區段傳送至[!DNL Google Customer Match]目的地之前，請確定您的[!DNL Google Ads]帳戶符合[Google客戶比對政策](https://support.google.com/google-ads/answer/6299717/customer-match-policy)。

Google會自動允許帳戶符合規範的客戶列出。

## 資料上線 {#data-onboarding}

[!UICONTROL People-Based Destinations]的資料擷取目前支援每筆批次傳輸最多10個雜湊電子郵件地址，連結至一個客戶ID([!DNL CRM ID])。 上傳連結至一個客戶ID的超過10個雜湊電子郵件地址會導致Audience Manager以不特定順序擷取其中的10個。

上傳多個雜湊電子郵件地址，連結至多個批次傳輸中的一個客戶ID，使Audience Manager保留最近新增的10個電子郵件地址。

## 資料隱私權 {#data-privacy}

雖然[!UICONTROL People-Based Destinations]可讓您根據上傳的雜湊電子郵件地址來鎖定對象，但您仍禁止將任何可直接識別的訪客資訊上傳至Audience Manager。 在資料上線階段中，您必須確定您打算使用的電子郵件地址已與[!DNL SHA256]演算法雜湊。 否則，您將無法在[!UICONTROL People-Based Destinations]中使用它們。

## 資料雜湊和加密 {#data-hashing-encryption}

加密是雙向功能。 任何加密的資訊也可以使用正確的解密密鑰進行解密。 在Audience Manager環境中加密資料會帶來嚴重風險，因為任何加密形式的個人識別資訊也可以解密。 與加密相反，[!UICONTROL People-Based Destinations]旨在改用雜湊資料。

雜湊是一種單向函式，可將輸入進行雜湊處理以產生唯一的結果。 使用適當的雜湊演算法（例如[!DNL SHA256]），便無法反轉雜湊函式並顯示未加擾的資訊。 您要上線至Audience Manager的電子郵件地址必須使用[!DNL SHA256]演算法雜湊。 如此，您即可確保沒有未雜湊的電子郵件地址可觸及Audience Manager。

## 雜湊要求 {#hashing-requirements}

對電子郵件地址進行雜湊處理時，請務必符合下列要求：

* 修剪電子郵件字串中的所有開頭和結尾空格；範例：`johndoe@example.com`，而不是`<space>johndoe@example.com<space>`;
* 對電子郵件字串進行雜湊處理時，請務必將小寫字串雜湊；
   * 範例：`example@email.com`，而不是`EXAMPLE@EMAIL.COM`;
* 確認雜湊字串全部為小寫
   * 範例：`55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`，而不是`55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* 別給繩子加鹽。

觀看以下影片以了解[!UICONTROL People-Based Destinations]的雜湊要求。

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud可讓您選擇透過[!DNL Adobe Experience Platform Identity Service (ECID)]雜湊客戶ID。 如需如何使用ECID來雜湊客戶ID的詳細資訊，請參閱setCustomerIDs的[SHA256雜湊支援](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) 。

## 取得使用者權限 {#obtaining-user-permission}

由於[!UICONTROL People-Based Destinations]可協助您在以人物為基礎的管道中啟用第一方受眾資料，因此您有責任向客戶通知並取得任何必要的同意，告知您將如何將其資料用於廣告或其他用途。

在註冊[!UICONTROL People-Based Destinations]之前，請務必先取得客戶的同意，再將其資訊用於廣告用途。

若您的客戶想要退出廣告促銷活動，請參閱[選擇退出管理](../../overview/data-security-and-privacy/data-privacy-requests.md)以取得如何停止Audience Manager進一步收集資料的詳細資訊。

## 強制執行第一方資料啟用 {#enforcing-first-party-activation}

使用[!UICONTROL People-Based Destinations]時，您只能使用第一方資料，在以人物為基礎的管道中啟用對象區段。 您無法在以人物為基礎的管道中使用任何第二方或第三方資料來啟動受眾。

使用[!UICONTROL People-Based Destinations]時，請使用[資料匯出控制項](../data-export-controls.md)，根據目標平台和資料提供者的准則和需求，標示您的[!UICONTROL data sources]和[!UICONTROL destinations]。

## 透過宣告ID定位，將已驗證的雜湊ID上線 {#onboard-authenticated-declared-id}

有兩種方式可將離線資料帶入 Audience Manager 中以用於[!UICONTROL People-Based Destinations]。

* [傳送批次](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 資料Audience Manager以內嵌雜湊電子郵件地址。使用此方法，您可以選擇在[!UICONTROL People-Based Destinations]中使用[!DNL CRM]資料庫中的雜湊電子郵件地址。 此外，使用此方法時，您也可以將雜湊電子郵件地址限定為[已上線特徵](../traits/trait-and-segment-qualification-reference.md)。
* 傳入已驗證的客戶ID時，請使用[宣告ID](../declared-ids.md)來宣告雜湊電子郵件地址。 使用此方法時，Audience Manager僅代表已線上驗證的使用者傳送雜湊電子郵件地址至[!UICONTROL People-Based Destinations]。 透過以人物為基礎的管道啟動的電子郵件地址，只是宣告ID事件呼叫中的電子郵件地址。 與客戶ID相關聯的其他電子郵件地址不會即時傳送。
