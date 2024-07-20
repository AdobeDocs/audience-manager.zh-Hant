---
description: 本文說明如何從Audience Manager使用者介面設定新的以裝置為基礎的目的地。
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: 新增以裝置為基礎的目的地
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 2%

---

# 新增以裝置為基礎的目的地 {#add-new-device-based-destinations}

本文說明如何從Audience Manager使用者介面設定新的以裝置為基礎的目的地。

>[!IMPORTANT]
>
>目前，大部分以裝置為基礎的目的地不符合自助服務設定工作流程的資格。 如果目的地清單未顯示您需要新增的以裝置為基礎的目的地，請聯絡您的Adobe顧問或客戶支援以尋求協助。

## 概述 {#overview}

新增以裝置為基礎之目的地的程式包含兩個主要步驟。 首先，您需要設定Audience Manager與目的地合作夥伴之間的整合。 完成此操作後，您可以建立以裝置為基礎的新目的地。

## 必備條件 {#prerequisites}

使用整合平台建立第一個以裝置為基礎的目的地時，請聯絡Adobe Consulting或客戶服務，為您的帳戶啟用Audience Manager與整合平台之間的ID同步。 這是Audience Manager與目的地平台之間正確同步的必要條件。

## 步驟 1.使用目的地平台進行驗證 {#step1}

建立以裝置為基礎的新目的地之前，您需要先設定Audience Manager與目的地平台之間的整合。 以下是其操作方式：

1. 登入您的Audience Manager帳戶並移至&#x200B;**[!DNL Administration > Integrated Accounts]**。 如果您先前設定好與目的地平台的整合，您應會看到此頁面所列的專案。 否則，頁面會是空的。
1. 按一下 **[!DNL Add Account]**。
1. 選取您要驗證的目的地平台，然後按一下&#x200B;**[!DNL Confirm]**&#x200B;以重新導向至所選平台的驗證頁面。

   ![整合平台](assets/dbd-integrated-platforms.png)

1. 在您驗證目的地平台帳戶後，系統會將您重新導向至Audience Manager，您應可在其中檢視相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!DNL Confirm]**。

## 步驟 2.建立以裝置為基礎的新目的地 {#step2}

設定完目的地平台整合後，您就可以建立新的目的地。 以下是其操作方式：

>[!NOTE]
>
>您無法變更現有的以裝置為基礎的目的地名稱。 請務必提供有助於您正確識別目的地的名稱。

1. 登入您的Audience Manager帳戶，前往&#x200B;**[!DNL Audience Data > Destinations]**，然後按一下&#x200B;**[!DNL Create Destination]**。
1. 在&#x200B;**[!DNL Basic Information]**&#x200B;區段中，輸入您新目的地的&#x200B;**[!DNL Name]**&#x200B;和&#x200B;**[!DNL Description]**，並使用下列清單中的設定：

   ![安裝程式](assets/dbd-new-basic.png)

   * **[!DNL Category]**： [!DNL Integrated Platforms]；
   * **[!DNL Type]**： [!DNL Device-Based]；
   * **[!DNL Platform]**：選取您要傳送對象區段的目的地平台。
   * **[!DNL Account]**：選取與所選平台相關聯的所需廣告商帳戶。
1. 按一下 **[!DNL Next]**。
1. 選擇要為此目的地設定的[資料匯出標籤](/help/using/features/data-export-controls.md#controls-labels)。
1. 按一下 **[!DNL Save]**。
1. 在&#x200B;**[!DNL Segment Mappings]**&#x200B;區段中，選取您要傳送至此目的地的對象區段。
1. 儲存目的地。
