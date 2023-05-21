---
description: 本文介紹如何從Audience Manager用戶介面配置新的基於設備的目標。
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: 新增以裝置為基礎的目的地
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 3%

---

# 新增以裝置為基礎的目的地 {#add-new-device-based-destinations}

本文介紹如何從Audience Manager用戶介面配置新的基於設備的目標。

>[!IMPORTANT]
>
>目前，大多數基於設備的目標不符合自助服務配置工作流的條件。 如果您需要添加的基於設備的目標未顯示在目標清單中，請與Adobe顧問或客戶支援聯繫以獲得幫助。

## 概述 {#overview}

添加新的基於設備的目的地的過程包括兩個主要步驟。 首先，您需要配置Audience Manager與目標合作夥伴之間的整合。 完成此操作後，可以建立新的基於設備的目標。

## 必要條件 {#prerequisites}

在使用整合平台建立第一個基於設備的目標時，請聯繫Adobe咨詢或客戶服務部門，以便為您的客戶啟用Audience Manager和整合平台之間的ID同步。 這是Audience Manager與目標平台之間正確同步所必需的。

## 步驟 1. 使用目標平台進行身份驗證 {#step1}

在建立新的基於設備的目標之前，您需要配置Audience Manager與目標平台之間的整合。 下面是如何做到的：

1. 登錄到您的Audience Manager帳戶，然後轉到 **[!DNL Administration > Integrated Accounts]**。 如果您以前配置了與目標平台的整合，則應在此頁中列出該整合。 否則，頁面為空。
1. 按一下 **[!DNL Add Account]**.
1. 選擇要驗證的目標平台，然後按一下 **[!DNL Confirm]** 重定向到所選平台的驗證頁面。

   ![整合平台](assets/dbd-integrated-platforms.png)

1. 一旦您已經通過目標平台帳戶的身份驗證，您將被重定向到Audience Manager，您應該在該區域查看相關的廣告商帳戶。 選擇要使用的廣告商帳戶，然後按一下 **[!DNL Confirm]**。

## 步驟 2.建立新的基於設備的目標 {#step2}

配置目標平台整合後，可以建立新目標。 下面是如何做到的：

>[!NOTE]
>
>不能更改現有基於設備的目標的名稱。 確保提供有助於正確標識目標的名稱。

1. 登錄到Audience Manager帳戶，轉到 **[!DNL Audience Data > Destinations]**，然後按一下 **[!DNL Create Destination]**。
1. 在 **[!DNL Basic Information]** 部分，輸入 **[!DNL Name]** 和 **[!DNL Description]** 用於新目標，並使用以下清單中的設定：

   ![設定](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**:選擇要將受眾段發送到的目標平台。
   * **[!DNL Account]**:選擇與所選平台關聯的所需廣告商帳戶。
1. 按一下 **[!DNL Next]**.
1. 選擇 [資料導出標籤](/help/using/features/data-export-controls.md#controls-labels) 要為此目標設定。
1. 按一下 **[!DNL Save]**.
1. 在 **[!DNL Segment Mappings]** 部分，選擇要發送到此目標的受眾段。
1. 保存目標。
