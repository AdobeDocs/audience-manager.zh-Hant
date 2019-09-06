---
description: '本頁面包含如何設定及管理Audience Manager與人員平台之間整合的指引。 '
seo-description: '本頁面包含如何設定及管理Audience Manager與人員平台之間整合的指引。 '
seo-title: 以人員為基礎的平台驗證
solution: Audience Manager
title: 以人員為基礎的平台驗證
translation-type: tm+mt
source-git-commit: 05f334dc3d975a0fe18b93c844889e3edb2dfafa

---


# 以人員為基礎的平台驗證 {#authentication-with-people-based-platforms}

本頁面包含如何設定及管理Audience Manager與人員平台之間整合的指引。

>[!NOTE]
>這是「以人為本」的必要步驟，不論您的實施案例為何。

## 設定人員型平台驗證 {#configure-authentication}

1. 登入您的Audience Manager帳戶，然後前往 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。如果您先前已設定與社交平台的整合，則應在此頁面中查看它。否則，頁面是空的。
   ![人員型整合](assets/pbd-config.png)
1. Click **[!UICONTROL Add Account]**.
1. 使用 **[!UICONTROL People-Based Platform]** 下拉式選單選擇您要設定整合的平台。
   ![人員型平台](assets/pbd-add.png)
1. 按一下以 **[!UICONTROL Confirm]** 重新導向至所選平台的驗證頁面。
1. 在您驗證您的社交平台帳戶後，將會重新導向至Audience Manager，您應該會看到相關聯的廣告商帳戶。選取您要使用並按一下 **[!UICONTROL Confirm]**&#x200B;的廣告商帳戶。
1. Audience Manager會在頁面頂端顯示通知，讓您知道帳戶是否成功新增。此通知也可讓您新增連絡人電子郵件地址，以便在社交平台驗證即將過期時接收通知。

## 驗證Token有效期和通知管理 {#token-expiration-notification}

Audience Manager透過在特定時間長度後過期的驗證Token，處理與社交平台之間的整合。Token有效性持續時間取決於每個社交平台的整合規則。一旦驗證Token過期，Audience Manager就無法將您的觀眾區段傳送至目的地。為避免此情況發生，我們建議您在整合中加入至少一個連絡人電子郵件地址，如此當驗證Token即將過期時，您就會立即收到通知。此時，您可以重新驗證，確保目的地繼續接收您的觀眾區段。

以下說明如何新增電子郵件地址至現有整合：

1. 登入您的Audience Manager帳戶，然後前往 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。
1. 識別您要接收Token過期通知的整合，並按一下 **[!UICONTROL Edit]** 圖示。
1. 輸入您要接收代號有效期通知的電子郵件地址，並以逗號分隔。
1. Click **[!UICONTROL Save]**.

## 驗證Token續約 {#token-renewal}

當驗證Token過期時，Audience Manager與對應社交平台之間的整合會中斷，因此Audience Manager無法再將觀眾區段傳送至目的地。[!UICONTROL Integrated Accounts] 頁面會顯示 [!UICONTROL Expiration] 欄中每個整合的有效期狀態，並允許您隨時續約驗證。

以下是如何續約過期或過期驗證的方法：
1. 登入您的Audience Manager帳戶，然後前往 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。
1. 識別您需要續約驗證的整合。過期的驗證會標示為 [!UICONTROL Expired]，而即將到期的驗證則會顯示剩餘的驗證天數。
1. 按一下欄中的對應 **[!UICONTROL Renew]** 圖示 [!UICONTROL Expiration] 。如此會觸發 **[!UICONTROL Renew Account]** 工作流程，讓您回到社交平台的驗證頁面。在驗證之後，代號會以新的到期日續約。
   ![pdd-renew](assets/pbd-renew.png)
