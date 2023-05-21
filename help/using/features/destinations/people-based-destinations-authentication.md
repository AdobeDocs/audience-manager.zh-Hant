---
description: 本頁介紹如何配置和管理Audience Manager平台與基於人員的平台之間的整合。
seo-description: This page contains guidance on how to configure and manage the integration between Audience Manager and people-based platforms.
seo-title: Authentication with People-Based Platforms
solution: Audience Manager
title: 使用以人物為基礎的平台進行驗證
feature: People-based Destinations
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 1%

---

# 使用以人物為基礎的平台進行驗證 {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>本文包含旨在指導您完成此功能的設定和使用的產品文檔。 這裡沒有法律建議。 請咨詢您自己的法律顧問以獲得法律指導。

本頁介紹如何配置和管理Audience Manager平台與基於人員的平台之間的整合。

>[!NOTE]
>這是基於人員的目標的必需步驟，無論您的實施方案如何。

## 配置基於人的平台身份驗證 {#configure-authentication}

1. 登錄到您的Audience Manager帳戶，然後轉到 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您以前配置了與社交平台的整合，則應在此頁中列出。 否則，頁面為空。
   ![基於人的整合](assets/pbd-config.png)
2. 按一下 **[!UICONTROL Add Account]**.
3. 使用 **[!UICONTROL People-Based Platform]** 下拉菜單，以選擇要配置整合的平台。
   ![基於人的平台](assets/pbd-add.png)
4. 按一下 **[!UICONTROL Confirm]** 重定向到所選平台的驗證頁面。
5. 一旦您已經通過社交平台帳戶的身份驗證，您將被重定向到Audience Manager，您應該在該區域查看相關的廣告商帳戶。 選擇要使用的廣告商帳戶，然後按一下 **[!UICONTROL Confirm]**。
6. Audience Manager在頁面頂部顯示通知，以便您知道是否已成功添加帳戶。 此通知還允許您添加聯繫人電子郵件地址以在社交平台身份驗證即將過期時從Adobe接收通知。

## 驗證令牌過期和通知管理 {#token-expiration-notification}

Audience Manager通過身份驗證令牌處理與社交平台的整合，該令牌在一定時間後過期。 令牌有效性持續時間受每個社交平台的融合規則的約束。 一旦驗證令牌過期，Audience Manager將無法將您的受眾段發送到目標。 為避免出現此情形，我們建議至少向您的整合添加一個聯繫人電子郵件地址，以便在身份驗證令牌即將過期時立即收到通知。 當發生這種情況時，您可以重新驗證以確保目標繼續接收您的受眾群。

下面是如何將電子郵件地址添加到現有整合：

1. 登錄到您的Audience Manager帳戶，然後轉到 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 標識要接收令牌到期通知的整合，然後按一下 **[!UICONTROL Edit]** 表徵圖
1. 輸入要接收令牌過期通知的電子郵件地址，以逗號分隔。
1. 按一下 **[!UICONTROL Save]**.

## 驗證令牌續訂 {#token-renewal}

當Audience Manager令牌過期時，Audience Manager與相應社交平台之間的整合被中斷，因此不能再將受眾段發送到目的地。 的 [!UICONTROL Integrated Accounts] 頁面顯示了 [!UICONTROL Expiration] 列，並允許您隨時續訂身份驗證。

下面是如何續訂過期或即將過期的身份驗證：
1. 登錄到您的Audience Manager帳戶，然後轉到 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。
1. 確定續訂身份驗證所需的整合。 過期的身份驗證標籤為 [!UICONTROL Expired]，而即將過期的身份驗證將顯示剩餘的已驗證天數。
1. 按一下相應 **[!UICONTROL Renew]** 的 [!UICONTROL Expiration] 的雙曲餘切值。 這將觸發 **[!UICONTROL Renew Account]** 工作流，它將您帶回社交平台的驗證頁面。 驗證後，將使用新的到期日期續訂令牌。
   ![pbd更新](assets/pbd-renew.png)
