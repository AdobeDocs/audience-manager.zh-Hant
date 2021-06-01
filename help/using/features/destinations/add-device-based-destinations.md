---
description: 本文說明如何從Audience Manager使用者介面設定新的以裝置為基礎的目的地。
seo-description: 本文說明如何從Audience Manager使用者介面設定新的以裝置為基礎的目的地。
seo-title: 新增以裝置為基礎的目的地
solution: Audience Manager
title: 新增以裝置為基礎的目的地
feature: 目的地基本知識
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 4%

---

# 新增以裝置為基礎的目的地 {#add-new-device-based-destinations}

本文說明如何從Audience Manager使用者介面設定新的以裝置為基礎的目的地。

>[!IMPORTANT]
>
>目前，大部分以裝置為基礎的目的地都不符合自助服務設定工作流程的資格。 如果您需要新增的以裝置為基礎的目的地未顯示在目的地清單中，請聯絡您的Adobe顧問或客戶支援以取得協助。

## 概述 {#overview}

新增以裝置為基礎的新目的地的程式包含兩個主要步驟。 首先，您需要設定Audience Manager與目標合作夥伴之間的整合。 完成此操作後，您就可以建立新的以裝置為基礎的目的地。

## 必要條件 {#prerequisites}

使用整合平台建立第一個以裝置為基礎的目的地時，請連絡Adobe諮詢或客戶服務，為您的帳戶啟用Audience Manager與整合平台之間的ID同步。 這是正確同步Audience Manager與目標平台的必要條件。

## 步驟 1. 使用目標平台進行驗證 {#step1}

您必須先設定Audience Manager和目標平台之間的整合，才能建立新的以裝置為基礎的目的地。 以下是操作方法：

1. 登入您的Audience Manager帳戶，然後前往&#x200B;**[!DNL Administration > Integrated Accounts]**。 如果您先前已設定與目的地平台的整合，您應會在本頁面中看到該整合列出。 否則，頁面為空。
1. 按一下 **[!DNL Add Account]**.
1. 選擇要驗證的目標平台，然後按一下&#x200B;**[!DNL Confirm]**&#x200B;以重定向到所選平台的驗證頁。

   ![整合平台](assets/dbd-integrated-platforms.png)

1. 一旦驗證至您的目的地平台帳戶，系統會將您重新導向至Audience Manager，您應該會在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!DNL Confirm]**。

## 步驟 2.建立新的以裝置為基礎的目的地 {#step2}

設定目標平台整合後，您就可以建立新目標。 以下是操作方法：

>[!NOTE]
>
>您無法更改現有基於設備的目標的名稱。 請務必提供可協助您正確識別目的地的名稱。

1. 登入您的Audience Manager帳戶，前往&#x200B;**[!DNL Audience Data > Destinations]**，然後按一下&#x200B;**[!DNL Create Destination]**。
1. 在&#x200B;**[!DNL Basic Information]**&#x200B;區段中，輸入新目的地的&#x200B;**[!DNL Name]**&#x200B;和&#x200B;**[!DNL Description]**，然後使用下列清單中的設定：

   ![設定](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**:選取您要傳送受眾區段的目標平台。
   * **[!DNL Account]**:選取與所選平台相關聯的所需廣告商帳戶。
1. 按一下 **[!DNL Next]**.
1. 選擇要為此目標設定的[資料導出標籤](/help/using/features/data-export-controls.md#controls-labels)。
1. 按一下 **[!DNL Save]**.
1. 在&#x200B;**[!DNL Segment Mappings]**&#x200B;區段中，選取您要傳送至此目的地的對象區段。
1. 儲存目的地。
