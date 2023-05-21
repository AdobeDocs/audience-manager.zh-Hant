---
description: 請閱讀以下內容，瞭解您在註冊基於人員的目標之前需要滿足的客戶要求。
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: 必要條件和考量事項
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: cd40e1e3cc2199d1937950934d674cfad301f3e8
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# 必要條件和考量事項 {#prerequisites-considerations}

>[!IMPORTANT]
>本文包含旨在指導您完成此功能的設定和使用的產品文檔。 這裡沒有法律建議。 請咨詢您自己的法律顧問以獲得法律指導。

請閱讀以下內容，瞭解您在註冊前需要滿足的客戶需求概述 [!UICONTROL People-Based Destinations]。

>[!IMPORTANT]
> 在進入實施階段之前，請仔細閱讀本文。

## 註冊 [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] 是一種高級功能，它允許您在基於人的環境中激活第一方受眾群體，通過在社交網路上或通過電子郵件營銷為受眾提供定制服務來增強您的Audience Manager體驗。

請聯繫您的Adobe代表以利用此高級功能。

## 特定於合作夥伴的先決條件 {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

在您使用之前 [!UICONTROL People-Based Destinations] 派你的第一個派對觀眾 [!UICONTROL segments] 至 [!DNL Facebook]，確保滿足以下要求：

1. 您 [!DNL Facebook] 用戶帳戶必須具有 **管理市場活動** 已為您計畫使用的Ad帳戶啟用權限。
2. 添加 **Adobe Experience Cloud** 作為廣告合作夥伴的業務客戶 [!DNL Facebook Ad Account]。 使用 `business ID=206617933627973`。請參閱 [將合作夥伴添加到您的業務經理](https://www.facebook.com/business/help/1717412048538897) 的雙曲餘切值。
   >[!IMPORTANT]
   > 為Adobe Experience Cloud配置權限時，必須啟用 **管理市場活動** 權限。 這是進行 [!UICONTROL People-Based Destinations] 整合的必要權限。
3. 閱讀並簽名 [!DNL Facebook Custom Audiences] 服務條款。 若要完成此操作，請前往 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

### [!DNL LinkedIn] {#linkedin}

在您使用之前 [!UICONTROL People-Based Destinations] 將第一方觀眾群發給 [!DNL LinkedIn]，確保 [!DNL LinkedIn Campaign Manager] 帳戶 [!DNL Creative Manager] 或更高權限級別。

瞭解如何編輯 [!DNL LinkedIn Campaign Manager] 用戶權限，請參閱 [添加、編輯和刪除廣告帳戶上的用戶權限](https://www.linkedin.com/help/lms/answer/5753) 在LinkedIn檔案里。

請參閱 [理解和配置LinkedIn以人為本的目標](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) 視頻說明。

### [!DNL Google Customer Match] {#gcm}

在您使用之前 [!UICONTROL People-Based Destinations] 將第一方觀眾群發給 [!DNL Google Customer Match] 目標，確保閱讀並遵守Google的使用策略 [!DNL Customer Match]，在 [Google支援文檔](https://support.google.com/google-ads/answer/6299717)。

接下來，確保 [!DNL Google] 為 [!DNL Standard] 或更高權限級別。 查看 [Google廣告文檔](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) 的雙曲餘切值。

擁有合規帳戶的客戶將自動獲得Google的許可。

## 資料上線 {#data-onboarding}

資料接收 [!UICONTROL People-Based Destinations] 當前支援多達10個連接到一個客戶ID的散列電子郵件地址([!DNL CRM ID])，每批傳送。 上載10個以上連結到一個客戶ID的散列電子郵件地址會導致Audience Manager按不同順序接收其中的10個。

上載10個以上散列電子郵件地址，這些地址連結到多個批傳輸中的一個客戶ID，導致Audience Manager保留最近添加的10個電子郵件地址。

## 資料隱私權 {#data-privacy}

儘管 [!UICONTROL People-Based Destinations] 允許您根據您上傳的經過散列的電子郵件地址將目標訪問者設定為目標，您仍然禁止將任何可直接識別的訪問者資訊上載到Audience Manager。 在資料載入階段，必須確保您計畫使用的電子郵件地址與 [!DNL SHA256] 算法。 否則，您將無法在 [!UICONTROL People-Based Destinations]。

## 資料散列與加密 {#data-hashing-encryption}

加密是雙向功能。 也可以使用正確的解密密鑰來解密任何加密的資訊。 在Audience Manager環境中對資料進行加密會帶來嚴重的風險，因為任何加密形式的個人身份資訊也可以解密。 與加密相比， [!UICONTROL People-Based Destinations] 設計用於處理散列資料。

散列函式是對輸入進行加擾以產生唯一結果的單向函式。 通過使用適當的散列算法，例如 [!DNL SHA256]，無法對散列函式進行逆向處理，也無法揭示未置亂的資訊。 您要登載到Audience Manager的電子郵件地址必須與 [!DNL SHA256] 算法。 這樣，您就可以確保沒有未散列的電子郵件地址到達Audience Manager。

## 散列要求 {#hashing-requirements}

散列電子郵件地址時，請確保符合以下要求：

* 從電子郵件字串中裁切所有前導空格和尾隨空格；示例： `johndoe@example.com`不 `<space>johndoe@example.com<space>`;
* 散列電子郵件字串時，確保散列小寫字串；
   * 示例： `example@email.com`不 `EXAMPLE@EMAIL.COM`;
* 確保散列字串全部為小寫
   * 示例： `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`不 `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* 別用鹽把繩子撒了。

觀看下面的視頻，瞭解 [!UICONTROL People-Based Destinations]。

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud為您提供了通過 [!DNL Adobe Experience Platform Identity Service (ECID)]。 請參閱 [SHA256對setCustomerID的散列支援](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) 有關如何使用ECID對客戶ID進行散列的詳細資訊。

## 獲取用戶權限 {#obtaining-user-permission}

自 [!UICONTROL People-Based Destinations] 幫助您在基於人的渠道中激活第一方受眾資料，您有責任告知客戶並獲得客戶將如何使用其資料用於廣告或其他目的的任何必要同意。

在你註冊之前 [!UICONTROL People-Based Destinations]，確保在將客戶資訊用於廣告目的之前獲得客戶同意。

如果客戶希望退出廣告活動，請參閱 [選擇退出管理](../../overview/data-security-and-privacy/data-privacy-requests.md) 有關如何停止Audience Manager進一步收集資料的詳細資訊。

## 強制實施第一方資料激活 {#enforcing-first-party-activation}

使用時 [!UICONTROL People-Based Destinations]，您只能使用第一方資料激活基於人的渠道中的受眾段。 您不能在基於人的渠道中使用任何第二方或第三方資料激活受眾。

使用時 [!UICONTROL People-Based Destinations]。 [資料導出控制項](../data-export-controls.md) 為 [!UICONTROL data sources] 和 [!UICONTROL destinations] 指南和要求，提供資料。

## 通過聲明的ID目標的板載已驗證散列ID {#onboard-authenticated-declared-id}

有兩種方式可將離線資料帶入 Audience Manager 中以用於[!UICONTROL People-Based Destinations]。

* [發送批處理資料](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) Audience Manager以攝取已散列的電子郵件地址。 使用此方法，您可以選擇使用您的 [!DNL CRM] 資料庫 [!UICONTROL People-Based Destinations]。 此外，使用此方法時，您還可以將散列電子郵件地址 [已上鈎的性狀](../traits/trait-and-segment-qualification-reference.md)。
* 使用 [聲明的ID](../declared-ids.md) 在傳遞經過驗證的客戶ID時聲明散列的電子郵件地址。 使用此方法時，Audience Manager僅代表您發送到 [!UICONTROL People-Based Destinations] 已線上驗證的用戶的散列電子郵件地址。 通過基於人員的渠道激活的電子郵件地址僅是聲明的ID事件調用中的電子郵件地址。 與客戶ID關聯的其他電子郵件地址不會即時發送。
