---
description: '本頁包含如何設定及管理Audience Manager與以人物為基礎的平台之間整合的指引。 '
seo-description: '本頁包含如何設定及管理Audience Manager與以人物為基礎的平台之間整合的指引。 '
seo-title: 使用以人物為基礎的平台進行驗證
solution: Audience Manager
title: 使用以人物為基礎的平台進行驗證
feature: 以人物為基礎的目的地
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 2%

---

# 使用以人物為基礎的平台進行驗證 {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>本文包含的產品檔案旨在引導您完成此功能的設定與使用。 這裡沒有任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

本頁包含如何設定及管理整合的指引
在Audience Manager和以人物為基礎的平台之間。

>[!NOTE]
>無論您的實作案例為何，這都是以人物為基礎的目的地的必要步驟。

## 配置基於人員的平台身份驗證{#configure-authentication}

1. 登入您的Audience Manager帳戶，然後前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您先前已設定與社交平台的整合，您應會在此頁面中看到該整合。 否則，頁面為空。
   ![以人物為基礎的整合](assets/pbd-config.png)
2. 按一下 **[!UICONTROL Add Account]**.
3. 使用&#x200B;**[!UICONTROL People-Based Platform]**下拉式功能表，選取您要設定整合的平台。
   ![以人物為基礎的平台](assets/pbd-add.png)
4. 按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;以重新導向至所選平台的驗證頁面。
5. 一旦您通過社交平台帳戶驗證，系統會將您重新導向至Audience Manager，您應該會在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!UICONTROL Confirm]**。
6. Audience Manager會在頁面頂端顯示通知，告知您帳戶是否已成功新增。 通知也可讓您新增聯絡人電子郵件地址，以在社交平台驗證即將過期時從Adobe接收通知。

## 驗證令牌過期和通知管理{#token-expiration-notification}

Audience Manager會透過驗證Token來處理您與社交平台的整合，此Token會在一段時間後過期。 代號有效期限取決於每個社交平台的整合規則。 驗證Token過期後，Audience Manager就無法將您的對象區段傳送至目的地。 若要避免此情形，建議您至少新增一個連絡人電子郵件地址至您的整合，以便在驗證Token即將過期時立即收到通知。 發生此情況時，您可以重新驗證，以確保目的地繼續收到您的對象區段。

以下說明如何將電子郵件地址新增至現有的整合：

1. 登入您的Audience Manager帳戶，然後前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 識別您要接收的Token過期通知的整合，然後按一下&#x200B;**[!UICONTROL Edit]**&#x200B;圖示。
1. 輸入您要接收代號過期通知的電子郵件地址，並以逗號分隔。
1. 按一下 **[!UICONTROL Save]**.

## 驗證令牌續訂{#token-renewal}

當驗證Token過期時，Audience Manager與對應社交平台之間的整合會中斷，因此Audience Manager無法再將受眾區段傳送至目的地。 [!UICONTROL Integrated Accounts]頁面會顯示[!UICONTROL Expiration]欄中每個整合的到期狀態，並可讓您隨時更新驗證。

以下說明如何續約過期或即將過期的驗證：
1. 登入您的Audience Manager帳戶，然後前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 識別您需要為續約驗證的整合。 過期的驗證會標示為[!UICONTROL Expired]，而即將過期的驗證會顯示剩餘的已驗證天數。
1. 按一下[!UICONTROL Expiration]欄中對應的&#x200B;**[!UICONTROL Renew]**&#x200B;圖示。 這會觸發&#x200B;**[!UICONTROL Renew Account]**工作流程，引導您回到社交平台的驗證頁面。 驗證後，代號會以新的到期日續訂。
   ![pbd-renew](assets/pbd-renew.png)
