---
description: Audience Manager用戶管理正在向Adobe Admin Console轉移。 本文介紹您需要做什麼來準備用戶遷移，以及遷移完成後將發生哪些更改。
keywords: rbac;RBAC；基於角色；基於角色；基於角色的訪問控制
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Audience Manager用戶遷移到Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 3%

---

# [!DNL Audience Manager] 用戶遷移 [!DNL Admin Console] {#user-migration}

## 概述 {#overview}

[!DNL Audience Manager] 用戶帳戶管理正在轉到 [Adobe Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)，讓您的Adobe解決方案獲得更優化的體驗。

使用 [!DNL Admin Console] 包括：

| 好處 | 說明 |
|---|---|
| 單一登入 跨解決方案 | [!DNL Audience Manager] 用戶可以登錄 [!DNL Experience Cloud] 所有其他解決方案 [!DNL Adobe ID] 或 [!DNL Enterprise ID]。 此登錄支援跨整個系統訪問整合解決方案和核心服務 [!DNL Experience Cloud]。 遷移後，嘗試通過舊登錄登錄登錄的用戶(`bank.demdex.com`)將重定向到 `experiencecloud.adobe.com`。 |
| 管理用戶和組 | 遷移完成後， [!DNL Audience Manager] 管理員將只管理 [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)。 |
| 管理產品和服務 | 從 [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)，管理員可以： <ul><li>建立、更新和刪除用戶</li><li>授予對解決方案和服務的訪問權</li></ul> |

為方便用戶遷移，我們要求 [!DNL Audience Manager] 管理員開始將其用戶帳戶遷移到 [Adobe Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html) 按照本文所述步驟盡快完成。

## 用戶需要做什麼 {#what-to-do-users}

作為Audience Manager用戶，您只需與 [!DNL Audience Manager] 管理員，並要求他們為您在 [!DNL Admin Console]。

## 管理員需要做什麼 {#what-to-do-admins}

Audience Manager管理員應按照以下步驟將用戶遷移到 [!DNL Admin Console]。

1. 轉到 [https://adminconsole.adobe.com](https://adminconsole.adobe.com) 用你的Adobe ID或Enterprise ID登錄。 如果您無權訪問 [!DNL Admin Console]，聯繫客戶服務或您的Adobe顧問。
2. 檢查 [!DNL Adobe Admin Console] [幫助指南](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) 有關如何建立和管理用戶帳戶的詳細說明。
3. 為所有現有Audience Manager用戶建立新用戶帳戶。
4. 將新建立的用戶帳戶通知您的用戶。 用戶遷移到 [!DNL Admin Console]，他們應停止使用舊登錄。

## 用戶遷移注意事項 {#considerations}

用戶和管理員都應牢記以下Audience Manager用戶遷移注意事項：

* 在Admin Console中建立新用戶帳戶後，其舊用戶帳戶的現有權限仍將應用。
* 用戶權限的更新仍將從 [!DNL Audience Manager]。 的 [!DNL Admin Console] 僅涵蓋用戶和組管理。
* 管理員不需要禁用舊用戶帳戶。 舊用戶帳戶將自動合併到已遷移的用戶帳戶中。
