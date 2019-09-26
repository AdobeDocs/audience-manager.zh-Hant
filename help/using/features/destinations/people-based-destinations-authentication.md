---
description: '本頁包含如何設定及管理Audience manager與人員型平台之間整合的指引。 '
seo-description: '本頁包含如何設定及管理Audience manager與人員型平台之間整合的指引。 '
seo-title: 使用以人為本的平台進行驗證
solution: Audience Manager
title: 使用以人為本的平台進行驗證
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

---


# 使用以人為本的平台進行驗證 {#authentication-with-people-based-platforms}

本頁包含如何設定及管理Audience manager與人員型平台之間整合的指引。

>[!NOTE]
>無論您的實作藍本為何，這是以人為本的目的地的必要步驟。

## 配置基於人員的平台身份驗證 {#configure-authentication}

1. 登入您的Audience manager帳戶，然後前往 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。 如果您先前已設定與社交平台的整合，您應該會在此頁面中看到它。 否則，頁面為空。
   ![以人為本的整合](assets/pbd-config.png)
1. Click **[!UICONTROL Add Account]**.
1. 使用下 **[!UICONTROL People-Based Platform]** 拉式選單來選取您要設定整合的平台。
   ![以人為本的平台](assets/pbd-add.png)
1. 按一 **[!UICONTROL Confirm]** 下以重新導向至所選平台的驗證頁面。
1. 一旦您已驗證您的社交平台帳戶，就會將您重新導向至Audience Manager，您應該會在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下 **[!UICONTROL Confirm]**。
1. Audience manager會在頁面頂端顯示通知，讓您知道帳戶是否已成功新增。 此通知也可讓您新增連絡人電子郵件地址，以在社交平台驗證即將到期時接收Adobe的通知。

## 驗證Token過期和通知管理 {#token-expiration-notification}

Audience manager會透過驗證Token處理您與社交平台的整合，驗證Token會在特定時間後過期。 代號有效期限受每個社交平台整合規則的約束。 一旦驗證Token過期，Audience manager就無法將您的觀眾區隔傳送至您的目的地。 為避免此情形，我們建議您在整合中新增至少一個連絡人電子郵件地址，以便在驗證Token即將過期時立即收到通知。 當發生此情況時，您可以重新驗證，以確保目標可繼續接收您的受眾細分。

以下說明如何將電子郵件地址新增至現有整合：

1. 登入您的Audience manager帳戶，然後前往 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。
1. 識別您要接收Token過期通知的整合，然後按一下圖 **[!UICONTROL Edit]** 示。
1. 輸入您要接收Token過期通知的電子郵件地址，以逗號分隔。
1. Click **[!UICONTROL Save]**.

## 驗證Token續約 {#token-renewal}

當驗證Token過期時，Audience manager與對應社交平台的整合會中斷，因此Audience manager無法再將對象區段傳送至目的地。 此頁 [!UICONTROL Integrated Accounts] 面會顯示欄中每個整合的過期狀態， [!UICONTROL Expiration] 並允許您隨時續約驗證。

以下說明如何續約過期或即將過期的驗證：
1. 登入您的Audience manager帳戶，然後前往 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。
1. 識別需要為更新驗證的整合。 過期的驗證會標 [!UICONTROL Expired]記為，而即將到期的驗證會顯示剩餘的驗證天數。
1. 按一下欄 **[!UICONTROL Renew]** 中的對應 [!UICONTROL Expiration] 圖示。 這會觸發 **[!UICONTROL Renew Account]** 工作流程，讓您重新瀏覽社交平台的驗證頁面。 一旦您驗證後，代號會隨著新的到期日而續約。
   ![pbd-續約](assets/pbd-renew.png)
