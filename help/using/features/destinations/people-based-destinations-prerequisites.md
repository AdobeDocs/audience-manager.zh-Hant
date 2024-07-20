---
description: 請閱讀下文，概略瞭解您在註冊People-Based Destinations之前需要滿足的客戶需求。
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: 必要條件和考量事項
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: 2b823855994f394261a66e896ef7de7bb7a5450f
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 2%

---


# 必要條件和考量事項 {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 此處未包含任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

請閱讀下文，概略瞭解您在註冊[!UICONTROL People-Based Destinations]之前需要滿足的客戶需求。

>[!IMPORTANT]
> 在進入實作階段之前，請先仔細閱讀本文。

## 正在註冊[!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations]是一項進階功能，可讓您在以人物為基礎的環境中、透過社交網路上的自訂優惠方案或電子郵件行銷鎖定您的對象，來啟用第一方對象區段，藉以強化您的Audience Manager體驗。

請聯絡您的Adobe代表以使用此進階功能。

## 合作夥伴特定必要條件 {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

使用[!UICONTROL People-Based Destinations]將第一方對象[!UICONTROL segments]傳送至[!DNL Facebook]之前，請確定您符合下列要求：

1. 您的[!DNL Facebook]使用者帳戶必須針對您計畫使用的廣告帳戶啟用&#x200B;**管理行銷活動**&#x200B;許可權。
2. 將&#x200B;**Adobe Experience Cloud**&#x200B;商業帳戶新增為您[!DNL Facebook Ad Account]中的廣告合作夥伴。 使用 `business ID=206617933627973`。如需詳細資訊，請參閱[新增合作夥伴至您的Business Manager](https://www.facebook.com/business/help/1717412048538897)。

   >[!IMPORTANT]
   >設定Adobe Experience Cloud的許可權時，您必須啟用&#x200B;**管理行銷活動**&#x200B;許可權。 這是進行 [!UICONTROL People-Based Destinations] 整合的必要權限。

3. 閱讀並簽署[!DNL Facebook Custom Audiences]服務條款。 若要完成此操作，請前往 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

### [!DNL LinkedIn] {#linkedin}

使用[!UICONTROL People-Based Destinations]將第一方對象區段傳送至[!DNL LinkedIn]之前，請確定您的[!DNL LinkedIn Campaign Manager]帳戶具有[!DNL Creative Manager]或更高的許可權層級。

若要瞭解如何編輯您的[!DNL LinkedIn Campaign Manager]使用者許可權，請參閱LinkedIn檔案中的[在Advertising帳戶上新增、編輯和移除使用者許可權](https://www.linkedin.com/help/lms/answer/5753)。

如需視訊指示，請參閱[瞭解及設定LinkedIn以人物為基礎的目的地](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html)。

### [!DNL Google Customer Match] {#gcm}

使用[!UICONTROL People-Based Destinations]將第一方對象區段傳送至[!DNL Google Customer Match]目的地之前，請務必閱讀並遵守Google有關使用[!DNL Customer Match]的原則，如在[Google支援檔案](https://support.google.com/google-ads/answer/6299717)中所述。

接下來，確定您的[!DNL Google]帳戶已設定為[!DNL Standard]或更高的許可權等級。 如需詳細資訊，請參閱[Google Ads檔案](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1)。

Google會自動允許具有合規帳戶的客戶列出。

## 資料上線 {#data-onboarding}

>[!IMPORTANT]
>
>所有Audience Manager客戶不需註冊[!UICONTROL People-Based Destinations]，即可內嵌雜湊電子郵件。

[!UICONTROL People-Based Destinations]的資料擷取目前支援每個批次傳輸最多10個連結至一個客戶ID ([!DNL CRM ID])的雜湊電子郵件地址。

在多次批次傳輸中，上傳連結至一個客戶ID的10個以上的雜湊電子郵件地址，會導致Audience Manager保留最近新增的10個電子郵件地址。

若要擷取雜湊識別碼，[請建立雜湊識別碼的跨裝置資料來源](../create-data-source-hashed-emails.md)並啟用&#x200B;**[!UICONTROL Share associated cross-device IDs in people-based destinations and/or hashed email workflows]**&#x200B;選項。

![Audience Manager使用者介面影像，顯示在以人物為基礎的目的地及/或雜湊電子郵件工作流程中，共用相關跨裝置ID的選項](assets/data-source-share-ids.png)

## 資料隱私權 {#data-privacy}

雖然[!UICONTROL People-Based Destinations]可讓您根據您所上傳的雜湊電子郵件地址來鎖定對象，但您仍無法上傳任何直接可識別的訪客資訊至Audience Manager。 在資料上線階段中，您必須確定您計畫使用的電子郵件地址已使用[!DNL SHA256]演演算法執行雜湊處理。 否則，您將無法在[!UICONTROL People-Based Destinations]中使用它們。

## 資料雜湊與加密 {#data-hashing-encryption}

加密是雙向功能。 任何加密的資訊也可使用正確的解密金鑰解密。 在Audience Manager環境中加密資料會帶來嚴重風險，因為任何加密形式的個人識別資訊都可以解密。 與加密相反，[!UICONTROL People-Based Destinations]設計成使用雜湊資料。

雜湊是單向函式，會對輸入進行雜湊以產生唯一結果。 若使用適當的雜湊演演算法（例如[!DNL SHA256]），便無法反轉雜湊函式並顯示未雜湊的資訊。 您即將加入Audience Manager的電子郵件地址必須使用[!DNL SHA256]演演算法雜湊。 如此一來，您便可確保沒有未雜湊的電子郵件地址會觸及Audience Manager。

## 雜湊需求 {#hashing-requirements}

對電子郵件地址進行雜湊處理時，請務必遵守下列要求：

* 修剪電子郵件字串中所有開頭和結尾的空格；範例： `johndoe@example.com`，而非`<space>johndoe@example.com<space>`；
* 雜湊電子郵件字串時，請務必雜湊小寫字串；
   * 範例： `example@email.com`，而非`EXAMPLE@EMAIL.COM`；
* 請確定雜湊字串都是小寫
   * 範例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`，而非`55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`；
* 請勿對字串執行Salt處理。

觀看以下影片以瞭解[!UICONTROL People-Based Destinations]的雜湊需求。

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud提供您透過[!DNL Adobe Experience Platform Identity Service (ECID)]雜湊客戶ID的選項。 如需如何使用ECID雜湊客戶ID的詳細資訊，請參閱setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html)的[SHA256雜湊支援。

## 取得使用者許可權 {#obtaining-user-permission}

由於[!UICONTROL People-Based Destinations]可協助您在以人物為基礎的管道中啟用第一方對象資料，因此您有責任通知客戶，並取得客戶對於您將如何將其資料用於廣告或其他目的的任何必要同意。

在您註冊[!UICONTROL People-Based Destinations]之前，請務必先取得客戶的同意，然後再將其資訊用於廣告用途。

如果您的客戶希望退出廣告行銷活動，請參閱[選擇退出管理](../../overview/data-security-and-privacy/data-privacy-requests.md)，以取得有關如何停止Audience Manager進一步收集資料的詳細資訊。

## 強制第一方資料啟用 {#enforcing-first-party-activation}

使用[!UICONTROL People-Based Destinations]時，您只能使用第一方資料在以人物為基礎的管道中啟用對象區段。 您無法在以人物為基礎的管道中，使用任何第二方或第三方資料來啟用對象。

使用[!UICONTROL People-Based Destinations]時，請使用[資料匯出控制項](../data-export-controls.md)，根據目的地平台和資料提供者的准則與需求，標籤您的[!UICONTROL data sources]和[!UICONTROL destinations]。

## 透過宣告ID目標定位將已驗證的雜湊ID上線 {#onboard-authenticated-declared-id}

有兩種方式可將離線資料帶入 Audience Manager 中以用於[!UICONTROL People-Based Destinations]。

* [傳送批次資料](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)給Audience Manager以擷取雜湊電子郵件地址。 使用此方法，您可以選擇使用[!UICONTROL People-Based Destinations]中[!DNL CRM]資料庫的雜湊電子郵件地址。 此外，使用此方法時，您也可以讓雜湊電子郵件地址符合[已上線特徵](../traits/trait-and-segment-qualification-reference.md)。
* 傳入已驗證的客戶ID時，請使用[宣告ID](../declared-ids.md)來宣告雜湊電子郵件地址。 使用此方法時，Audience Manager代表您只會將線上驗證的使用者之雜湊電子郵件地址傳送給[!UICONTROL People-Based Destinations]。 透過以人物為基礎的管道啟用的電子郵件地址只是宣告ID事件呼叫中的電子郵件地址。 與客戶ID相關聯的其他電子郵件地址不會即時傳送。
