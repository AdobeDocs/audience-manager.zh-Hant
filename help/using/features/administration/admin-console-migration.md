---
description: Audience Manager使用者管理功能即將移至Adobe Admin Console。 本文說明您為準備使用者移轉所需執行的動作，以及移轉完成後將會有何改變。
keywords: rbac;RBAC；角色型；角色型；角色型存取控制
seo-description: Audience Manager使用者管理功能即將移至Adobe Admin Console。 本文說明您為準備使用者移轉所需執行的動作，以及移轉完成後將會有何改變。
seo-title: Audience Manager使用者移轉至Admin Console
solution: Audience Manager
title: Audience Manager使用者移轉至Admin Console
feature: 管理
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 3%

---

# [!DNL Audience Manager] 使用者移轉至  [!DNL Admin Console] {#user-migration}

## 概述 {#overview}

[!DNL Audience Manager] 使用者帳戶管理功能正移至 [Adobe Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)，讓您的Adobe解決方案享有更簡化的體驗。

使用[!DNL Admin Console]的好處包括：

| 好處 | 說明 |
|---|---|
| 單一登入 跨解決方案 | [!DNL Audience Manager] 使用者可使用其 [!DNL Experience Cloud] 或登入和所有其他解決 [!DNL Adobe ID] 方案 [!DNL Enterprise ID]。此登入可讓您在[!DNL Experience Cloud]存取整合式解決方案和核心服務。 移轉後，嘗試透過舊版登入頁面(`bank.demdex.com`)登入的使用者會重新導向至`experiencecloud.adobe.com`。 |
| 管理使用者和群組 | 移轉完成後，[!DNL Audience Manager]管理員將只管理[[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/)中的使用者和群組。 |
| 管理產品和服務 | 從[[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/)，管理員可以： <ul><li>建立、更新和移除使用者</li><li>授予解決方案和服務的存取權</li></ul> |

為方便使用者移轉，我們請所有[!DNL Audience Manager]管理員依照本文所述步驟，盡快將其使用者帳戶移轉至[Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)。

## {#what-to-do-users}用戶需要執行什麼操作

作為Audience Manager用戶，您只需聯繫[!DNL Audience Manager]管理員，要求他們在[!DNL Admin Console]中為您建立新用戶帳戶。

## 管理員需要執行什麼{#what-to-do-admins}

Audience Manager管理員應按照下列步驟將使用者移轉至[!DNL Admin Console]。

1. 前往[https://adminconsole.adobe.com](https://adminconsole.adobe.com)並使用您的Adobe ID或Enterprise ID登入。 如果您無法存取[!DNL Admin Console]，請聯絡客戶服務或您的Adobe顧問。
2. 查看[!DNL Adobe Admin Console] [幫助指南](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html)，了解如何建立和管理用戶帳戶的詳細說明。
3. 為所有現有Audience Manager使用者建立新使用者帳戶。
4. 將新建立的使用者帳戶告知使用者。 使用者移轉至[!DNL Admin Console]後，應停止使用舊版登入。

## 使用者移轉考量事項 {#considerations}

使用者和管理員在移轉Audience Manager使用者時，應謹記下列事項：

* 以Admin Console建立新使用者帳戶後，其來自舊版使用者帳戶的現有權限仍會套用。
* 系統仍會從[!DNL Audience Manager]管理使用者權限的更新。 [!DNL Admin Console]僅涵蓋使用者和群組管理。
* 管理員不需要停用舊版使用者帳戶。 舊使用者帳戶會自動合併至已移轉的帳戶。
