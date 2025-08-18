---
description: 本頁提供如何設定及管理Audience Manager與以人物為基礎的平台之間整合的相關指引。
seo-description: This page contains guidance on how to configure and manage the integration between Audience Manager and people-based platforms.
seo-title: Authentication with People-Based Platforms
solution: Audience Manager
title: 使用以人物為基礎的平台進行驗證
feature: People-based Destinations
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: 1809e9ee0b19a8ffb4bec38162f728d543d13701
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---


# 使用以人物為基礎的平台進行驗證 {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 此處未包含任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

本頁包含如何設定及管理整合的指引
介於Audience Manager和以人物為基礎的平台之間。

>[!NOTE]
>無論您的實作情況為何，此步驟都是以人物為基礎的目的地的必要步驟。

## 設定以人物為基礎的平台驗證 {#configure-authentication}

1. 登入您的Audience Manager帳戶並移至&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您先前設定好與社交平台的整合，您應會看到此頁面所列的專案。 否則，頁面會是空的。
   ![以人物為基礎的整合](assets/pbd-config.png)
2. 按一下 **[!UICONTROL Add Account]**。
3. 使用&#x200B;**[!UICONTROL People-Based Platform]**下拉式功能表選取您要設定整合的平台。
   ![以人員為基礎的平台](assets/pbd-add.png)
4. 按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;以重新導向至所選平台的驗證頁面。
5. 在驗證您的Social Platform帳戶後，您會重新導向至Audience Manager，在那裡您應該會看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!UICONTROL Confirm]**。
6. Audience Manager會在頁面頂端顯示通知，讓您知道帳戶是否已成功新增。 通知也可讓您新增連絡人電子郵件地址，以在社交平台驗證即將到期時接收來自Adobe的通知。

## 驗證Token到期日和通知管理 {#token-expiration-notification}

Audience Manager會透過驗證權杖（將於特定時間後到期），處理您與社交平台的整合。 權杖有效期間受限於每個社交平台的整合規則。 驗證Token過期後，Audience Manager便無法將您的對象區段傳送至您的目的地。 若要避免出現這種情況，我們建議將至少一個連絡人電子郵件地址新增到您的整合中，以便在驗證Token即將到期時立即通知您。 發生此情況時，您可以重新驗證身分，確保目的地會繼續收到您的對象區段。

以下說明如何新增電子郵件地址至現有的整合：

1. 登入您的Audience Manager帳戶並移至&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 識別您要接收權杖到期通知的整合，然後按一下&#x200B;**[!UICONTROL Edit]**&#x200B;圖示。
1. 輸入您要接收權杖過期通知的電子郵件地址（以逗號分隔）。
1. 按一下 **[!UICONTROL Save]**。

## 驗證權杖續約 {#token-renewal}

當驗證Token過期時，Audience Manager與對應社交平台之間的整合會中斷，因此Audience Manager無法再將受眾區段傳送至目的地。 [!UICONTROL Integrated Accounts]頁面會顯示[!UICONTROL Expiration]欄中每個整合的到期狀態，並可讓您隨時更新驗證。

以下說明如何更新已過期或即將過期的驗證：
1. 登入您的Audience Manager帳戶並移至&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 識別更新驗證所需的整合。 過期的驗證會標示為[!UICONTROL Expired]，而即將過期的驗證會顯示剩餘的驗證天數。
1. 按一下&#x200B;**[!UICONTROL Renew]**&#x200B;欄中對應的[!UICONTROL Expiration]圖示。 這會觸發&#x200B;**[!UICONTROL Renew Account]**工作流程，帶您回到社交平台的驗證頁面。 驗證後，Token會以新的到期日更新。
   ![pbd — 續約](assets/pbd-renew.png)
