---
description: 本文說明如何從Audience Manager UI設定新的裝置型目標。
seo-description: 本文說明如何從Audience Manager UI設定新的裝置型目標。
seo-title: 新增裝置型目標
solution: Audience Manager
title: 新增裝置型目標
translation-type: tm+mt
source-git-commit: 69fb3601ac9de300032abc8730a40c41abc12d97
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 1%

---


# 新增裝置型目標 {#add-new-device-based-destinations}

本文說明如何從Audience Manager UI設定新的裝置型目標。

>[!IMPORTANT]
>
>目前，大多數基於設備的目標都不適用於自助服務配置工作流。 如果您需要新增的裝置型目標未顯示在目標清單中，請連絡您的Adobe顧問或客戶支援以取得協助。

## 概述 {#overview}

新增裝置型目的地的程式包括兩個主要步驟。 首先，您需要設定Audience Manager與目標合作夥伴之間的整合。 完成此作業後，您就可以建立新的裝置型目標。

## 必備條件 {#prerequisites}

當使用整合平台建立第一個以裝置為基礎的目的地時，請聯絡Adobe諮詢或客戶服務，以便讓Audience Manager和您帳戶的整合平台之間進行ID同步化。 這是Audience Manager與目標平台正確同步的必要條件。

## 步驟 1. 使用目標平台驗證 {#step1}

在建立新的裝置型目標之前，您必須先設定Audience Manager與目標平台之間的整合。 以下是如何做到的：

1. 登入您的Audience Manager帳戶，然後前往 **[!DNL Administration > Integrated Accounts]**。 如果您先前已設定與目標平台的整合，您應會在此頁面中看到它。 否則，頁面為空。
1. 按一下 **[!DNL Add Account]**.
1. 選擇您要驗證的目標平台，然後按一 **[!DNL Confirm]** 下以重新導向至所選平台的驗證頁面。

   ![整合平台](assets/dbd-integrated-platforms.png)

1. 一旦您已驗證您的目標平台帳戶，就會將您重新導向至Audience Manager，您應該會在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下 **[!DNL Confirm]**。

## 步驟 2.建立新的裝置型目標 {#step2}

配置目標平台整合後，可以建立新目標。 以下是如何做到的：

>[!NOTE]
>
>您無法變更現有裝置型目的地的名稱。 請務必提供有助於正確識別目標的名稱。

1. 登入您的Audience Manager帳戶，前往， **[!DNL Audience Data > Destinations]**&#x200B;然後按一下 **[!DNL Create Destination]**。
1. 在該 **[!DNL Basic Information]** 部分中，輸入 **[!DNL Name]** 和 **[!DNL Description]** 新目標，然後使用下列清單中的設定：

   ![設定](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: 選取您要傳送對象區段的目標平台。
   * **[!DNL Account]**: 選取與所選平台相關聯的所需廣告商帳戶。
1. 按一下 **[!DNL Next]**.
1. 選擇 [要為此目標設定的資料導出標籤](/help/using/features/data-export-controls.md#controls-labels) 。
1. 按一下 **[!DNL Save]**.
1. 在區 **[!DNL Segment Mappings]** 段中，選取您要傳送至此目的地的對象區段。
1. 保存目標。
