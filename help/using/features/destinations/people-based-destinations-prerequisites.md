---
description: '請閱讀以下內容，以瞭解您在註冊人員型目標之前需要滿足的客戶需求。  '
seo-description: '請閱讀以下內容，以瞭解您在註冊人員型目標之前需要滿足的客戶需求。  '
seo-title: 基於人員的目標先決條件和考慮事項
solution: Audience Manager
title: 必要條件和考量事項
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 3%

---

# 必要條件和考量事項 {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

請閱讀以下內容，以瞭解您在註冊[!UICONTROL People-Based Destinations]之前必須符合的客戶需求。

>[!IMPORTANT]
> 在進入實施階段之前，請仔細閱讀本文章。

## 註冊[!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] 是一項進階功能，可讓您在以人為本的環境中啟動您的第一方受眾細分，透過社交網路或電子郵件行銷鎖定您的受眾，從而增強您的Audience Manager體驗。

請連絡您的Adobe代表，以利用此優質功能。

## 特定於合作夥伴的先決條件{#partner-prerequisites}

### [!DNL Facebook] {#facebook}

使用[!UICONTROL People-Based Destinations]將您的第一方對象[!UICONTROL segments]傳送至[!DNL Facebook]之前，請確定您符合下列需求：

1. 您的[!DNL Facebook]使用者帳戶必須為您計畫使用的廣告帳戶啟用&#x200B;**管理促銷活動**&#x200B;權限。
2. 將&#x200B;**Adobe Experience Cloud**&#x200B;商業帳戶新增為[!DNL Facebook Ad Account]的廣告合作夥伴。 使用 `business ID=206617933627973`。如需詳細資訊，請參閱[將合作夥伴新增至您的業務經理](https://www.facebook.com/business/help/1717412048538897)。
   >[!IMPORTANT]
   > 設定Adobe Experience Cloud的權限時，您必須啟用「管理促銷活動&#x200B;**」權限。**&#x200B;這是進行 [!UICONTROL People-Based Destinations] 整合的必要權限。
3. 閱讀並簽署[!DNL Facebook Custom Audiences]服務條款。 若要完成此操作，請前往 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

### [!DNL LinkedIn] {#linkedin}

使用[!UICONTROL People-Based Destinations]將您的第一方對象區段傳送至[!DNL LinkedIn]之前，請確定您的[!DNL LinkedIn Campaign Manager]帳戶具有[!DNL Creative Manager]或更高的權限層級。

如要瞭解如何編輯[!DNL LinkedIn Campaign Manager]使用者權限，請參閱LinkedIn檔案中的[新增、編輯和移除廣告帳戶的使用者權限](https://www.linkedin.com/help/lms/answer/5753)。

如需視訊指示，請參閱[瞭解和設定LinkedIn以人員為基礎的目的地](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html)。

### [!DNL Google Customer Match] {#gcm}

您必須先將[!DNL Google]新增至您的允許清單，才能使用[!UICONTROL People-Based Destinations]將您的第一方對象區段傳送至[!DNL Google Customer Match]目的地。

請連絡您的[!DNL Google]代表，並依照[使用客戶符合合作夥伴來上傳您的資料](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google]檔案中所述的允許清單指示進行。

完成此程式後，可以建立[!UICONTROL People-Based Destination]。

## 資料上線 {#data-onboarding}

[!UICONTROL People-Based Destinations]的資料擷取目前支援最多10個雜湊電子郵件地址，每個批次傳輸會連結至一個客戶ID([!DNL CRM ID])。 上傳連結至一個客戶ID的10個以上雜湊電子郵件地址會導致Audience Manager以無特定順序收錄其中10個。

在多次批次傳輸中，上傳超過10個連結至一個客戶ID的雜湊電子郵件地址會導致Audience Manager保留新增的10個最新電子郵件地址。

## 資料隱私權{#data-privacy}

雖然[!UICONTROL People-Based Destinations]可讓您根據您上傳的雜湊電子郵件地址來定位對象，但您仍禁止將任何直接可識別身份的訪客資訊上傳至Audience Manager。 在資料登入階段，您必須確保您打算使用的電子郵件地址已使用[!DNL SHA256]演算法雜湊。 否則，您將無法在[!UICONTROL People-Based Destinations]中使用它們。

## 資料散列與加密{#data-hashing-encryption}

加密是雙向功能。 任何加密的資訊也可以使用正確的解密密鑰進行解密。 在Audience Manager環境中加密資料會帶來嚴重風險，因為任何加密形式的個人身份識別資訊也可以解密。 與加密相反，[!UICONTROL People-Based Destinations]的設計目的是改用雜湊資料。

雜湊是單向函式，可對輸入進行雜湊以產生獨特的結果。 通過使用適當的散列算法（如[!DNL SHA256]），沒有辦法反轉散列函式並顯示未置亂的資訊。 您要登入Audience Manager的電子郵件地址必須使用[!DNL SHA256]演算法雜湊。 如此，您就可以確保沒有未雜湊的電子郵件地址可觸及Audience Manager。

## 散列要求{#hashing-requirements}

散列電子郵件地址時，請務必符合下列要求：

* 從電子郵件字串中修剪所有前導和尾隨空格；範例：`johndoe@example.com`，而非`<space>johndoe@example.com<space>`;
* 在對電子郵件字串進行散列時，請務必對小寫字串進行散列；
   * 範例：`example@email.com`，而非`EXAMPLE@EMAIL.COM`;
* 請確定雜湊字串全部為小寫
   * 範例：`55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`，而非`55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* 別用鹽鹽。

觀看以下視頻以瞭解[!UICONTROL People-Based Destinations]的散列要求。

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud提供選項，讓您透過[!DNL Adobe Experience Platform Identity Service (ECID)]雜湊客戶ID。 請參閱[SHA256 Hashing Support for setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html)以取得如何使用ECID來雜湊客戶ID的詳細資訊。

## 獲取用戶權限{#obtaining-user-permission}

由於[!UICONTROL People-Based Destinations]可協助您在以人為本的通道中啟用第一方受眾資料，因此您有責任向客戶通知並取得任何必要的同意，告知您將如何將其資料用於廣告或其他用途。

在註冊[!UICONTROL People-Based Destinations]之前，請務必取得客戶的同意，然後才能將客戶的資訊用於廣告。

如果您的客戶希望退出廣告宣傳，請參閱[退出管理](../../overview/data-security-and-privacy/data-privacy-requests.md)以取得如何停止Audience Manager進一步收集資料的詳細資訊。

## 強制第一方資料啟動{#enforcing-first-party-activation}

使用[!UICONTROL People-Based Destinations]時，您只能使用第一方資料，在以人為本的頻道中啟用受眾細分。 您無法在以人員為主的通道中使用任何第二方或第三方資料來啟動受眾。

使用[!UICONTROL People-Based Destinations]時，請使用[資料匯出控制](../data-export-controls.md)，根據目標平台和資料提供者的准則和要求來標示[!UICONTROL data sources]和[!UICONTROL destinations]。

## 透過宣告ID定位{#onboard-authenticated-declared-id}的板載已驗證雜湊ID

有兩種方式可將離線資料帶入 Audience Manager 中以用於[!UICONTROL People-Based Destinations]。

* [傳送批次](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 資料Audience Manager以收錄雜湊的電子郵件地址。使用此方法，您可以選擇使用[!UICONTROL People-Based Destinations]中[!DNL CRM]資料庫中的雜湊電子郵件地址。 此外，使用此方法時，您也可以將雜湊電子郵件地址限定為[已登入特徵](../traits/trait-and-segment-qualification-reference.md)。
* 使用[Declared IDs](../declared-ids.md)來宣告傳入已驗證的客戶ID時的雜湊電子郵件地址。 使用此方法時，Audience Manager僅代表您傳送已線上驗證之使用者的雜湊電子郵件地址給[!UICONTROL People-Based Destinations]。 透過以人為本的管道啟動的電子郵件地址，只是宣告的ID事件呼叫中的電子郵件地址。 與客戶ID相關的其他電子郵件地址不會即時傳送。
