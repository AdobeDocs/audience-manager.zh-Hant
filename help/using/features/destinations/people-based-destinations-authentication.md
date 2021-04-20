---
description: '本頁包含如何設定和管理Audience Manager與人員型平台之間整合的指引。 '
seo-description: '本頁包含如何設定和管理Audience Manager與人員型平台之間整合的指引。 '
seo-title: 使用以人物為基礎的平台進行驗證
solution: Audience Manager
title: 使用以人物為基礎的平台進行驗證
feature: People-based Destinations
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 2%

---

# 使用以人物為基礎的平台進行驗證 {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

本頁包含如何設定和管理整合的指引
在Audience Manager平台和以人為本的平台之間。

>[!NOTE]
>無論您的實作藍本為何，這是以人為本的目的地的必要步驟。

## 配置基於人的平台身份驗證{#configure-authentication}

1. 登入您的Audience Manager帳戶，並前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您先前已設定與社交平台的整合，您應該會在此頁面中看到它。 否則，頁面為空。
   ![以人為本的整合](assets/pbd-config.png)
2. 按一下 **[!UICONTROL Add Account]**.
3. 使用&#x200B;**[!UICONTROL People-Based Platform]**下拉式功能表，選取您要設定整合的平台。
   ![以人為本的平台](assets/pbd-add.png)
4. 按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;以重新導向至所選平台的驗證頁面。
5. 一旦您已驗證您的社交平台帳戶，就會將您重新導向至Audience Manager，您應該在該處看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!UICONTROL Confirm]**。
6. Audience Manager會在頁面頂端顯示通知，讓您知道帳戶是否已成功新增。 此通知也可讓您新增連絡人電子郵件地址，以便在社交平台驗證即將到期時，從Adobe接收通知。

## 驗證Token過期和通知管理{#token-expiration-notification}

Audience Manager會透過驗證Token處理您與社交平台的整合，這些Token會在特定時間後過期。 代號有效期限受每個社交平台整合規則的約束。 一旦驗證Token過期，Audience Manager便無法將您的讀者區段傳送至您的目的地。 為避免此情形，我們建議您在整合中新增至少一個連絡人電子郵件地址，以便在驗證Token即將過期時立即收到通知。 當發生此情況時，您可以重新驗證，以確保目標可繼續接收您的受眾細分。

以下說明如何將電子郵件地址新增至現有整合：

1. 登入您的Audience Manager帳戶，並前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 識別您要接收Token過期通知的整合，然後按一下&#x200B;**[!UICONTROL Edit]**&#x200B;圖示。
1. 輸入您要接收Token過期通知的電子郵件地址，以逗號分隔。
1. 按一下 **[!UICONTROL Save]**.

## 驗證Token續約{#token-renewal}

當驗證Token過期時，Audience Manager與對應社交平台的整合會中斷，因此Audience Manager無法再將觀眾區段傳送至目的地。 [!UICONTROL Integrated Accounts]頁面顯示[!UICONTROL Expiration]欄中每個整合的過期狀態，並允許您隨時續約驗證。

以下說明如何續約過期或即將過期的驗證：
1. 登入您的Audience Manager帳戶，並前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 識別需要為更新驗證的整合。 過期的驗證標籤為[!UICONTROL Expired]，而即將過期的驗證顯示剩餘的已驗證天數。
1. 按一下[!UICONTROL Expiration]列中相應的&#x200B;**[!UICONTROL Renew]**&#x200B;表徵圖。 這會觸發&#x200B;**[!UICONTROL Renew Account]**工作流程，並帶您回到社交平台的驗證頁面。 一旦您驗證後，代號會隨著新的到期日而續約。
   ![pbd-續約](assets/pbd-renew.png)
