---
description: 本文說明如何從Audience Manager UI設定新裝置型目的地。
seo-description: 本文說明如何從Audience Manager UI設定新裝置型目的地。
seo-title: 新增以裝置為基礎的目標
solution: Audience Manager
title: 新增以裝置為基礎的目標
translation-type: tm+mt
source-git-commit: d185a1d418e99abb99c36b28dfb419a1fb3b60f5

---


# 新增以裝置為基礎的目標 {#add-new-device-based-destinations}

本文說明如何從Audience Manager UI設定新裝置型目的地。

## 概述 {#overview}

新增裝置型目的地的程序包含兩個主要步驟。首先，您需要設定Audience Manager與目的地合作夥伴之間的整合。在完成這項作業後，您就可以建立新的裝置目的地。

>[!IMPORTANT]
>
>並非所有裝置型目的地都符合自助服務設定工作流程的資格。如果您需要新增的裝置目的地未顯示在目的地清單中，請聯絡您的Adobe顧問或客戶支援尋求協助。

## 步驟 1. 使用目標平台進行驗證 {#step1}

您必須先設定Audience Manager與目的地平台之間的整合，才能建立新的裝置目的地。以下是如何做到這一點：

1. 登入您的Audience Manager帳戶 **[!DNL Administration > Integrated Accounts]**&#x200B;並前往。如果您先前已設定與目的地平台整合，則應在此頁面中查看它。否則，頁面是空的。
2. Click **[!DNL Add Account]**.
3. 選取您要驗證的目標平台，然後按一下以 **[!DNL Confirm]** 重新導向至所選平台的驗證頁面。![整合平台](assets/dbd-integrated-platforms.png)
4. 在您驗證您的目的地平台帳戶後，將會重新導向至Audience Manager，您應該會看到相關聯的廣告商帳戶。選取您要使用並按一下 **[!DNL Confirm]**&#x200B;的廣告商帳戶。

## 步驟 2.建立新裝置型目的地 {#step2}

設定目標平台整合後，您可以建立新目的地。以下是如何做到這一點：

>[!NOTE]
>
>您無法變更現有裝置目的地的名稱。請務必提供名稱以協助您正確識別目標。

1. 登入您的Audience **[!DNL Audience Data > Destinations]** Manager帳戶，前往並按一下 **[!DNL Create Destination]**。
2. **[!DNL Basic Information]** 在區段中輸入新 **[!DNL Name]** 目的地， **[!DNL Description]** 並使用下列清單中的設定： ![設定](assets/dbd-new-basic.png)
   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**：選取您要傳送對象區段的目標平台。
   * **[!DNL Account]**：選取所選平台相關聯的廣告商帳戶。
3. Click **[!DNL Next]**.
4. 選擇您要為此目的地設定的 [「資料匯出標籤](/help/using/features/data-export-controls.md#controls-labels) 」。
5. Click **[!DNL Save]**.
6. 在 **[!DNL Segment Mappings]** 區段中，選取您要傳送至此目的地的對象區段。
7. 儲存目的地。

