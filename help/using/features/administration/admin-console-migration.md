---
description: Audience Manager使用者管理即將移至Adobe Admin Console。 本文說明準備使用者移轉所需的工作，以及移轉完成後將發生的變化。
keywords: RBAC；RBAC；角色型；角色型；角色型存取控制
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Audience Manager使用者移轉至Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 1%

---

# [!DNL Audience Manager]個使用者移轉至[!DNL Admin Console] {#user-migration}

## 概述 {#overview}

[!DNL Audience Manager]使用者帳戶管理即將移至[Adobe Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)，以便在您的Adobe解決方案中提供更精簡的體驗。

使用[!DNL Admin Console]的優點包括：

| 好處 | 說明 |
|---|---|
| 跨解決方案的單一登入 | [!DNL Audience Manager]使用者可以使用其[!DNL Adobe ID]或[!DNL Enterprise ID]登入[!DNL Experience Cloud]和所有其他解決方案。 此登入可讓您存取[!DNL Experience Cloud]的整合式解決方案和核心服務。 移轉後，嘗試透過舊版登入頁面(`bank.demdex.com`)登入的使用者將被重新導向至`experiencecloud.adobe.com`。 |
| 管理使用者和群組 | 移轉一旦完成，[!DNL Audience Manager]管理員將專門管理[[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)中的使用者和群組。 |
| 管理產品和服務 | 從[[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)，系統管理員可以： <ul><li>建立、更新和移除使用者</li><li>授予解決方案與服務的存取權</li></ul> |

為方便使用者移轉，我們要求所有[!DNL Audience Manager]管理員依照本文所述的步驟，儘快開始將其使用者帳戶移轉至[Adobe Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。

## 使用者需要做什麼 {#what-to-do-users}

身為Audience Manager使用者，您只需要連絡您的[!DNL Audience Manager]管理員，要求他們在[!DNL Admin Console]為您建立新的使用者帳戶。

## 管理員需要做什麼 {#what-to-do-admins}

Audience Manager管理員應該遵循下列步驟，將使用者移轉至[!DNL Admin Console]。

1. 前往[https://adminconsole.adobe.com](https://adminconsole.adobe.com)並使用您的Adobe ID或Enterprise ID登入。 如果您無法存取[!DNL Admin Console]，請聯絡客戶服務或您的Adobe顧問。
2. 請檢視[!DNL Adobe Admin Console] [說明指南](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html)，以取得有關如何建立和管理使用者帳戶的詳細指示。
3. 為所有現有的Audience Manager使用者建立新的使用者帳戶。
4. 通知您的使用者有關新建立的使用者帳戶。 使用者移轉至[!DNL Admin Console]後，即應停止使用舊版登入。

## 使用者移轉考量事項 {#considerations}

使用者和管理員在Audience Manager使用者移轉時，應牢記以下考量事項：

* 在Admin Console中建立新的使用者帳戶後，其舊版使用者帳戶的現有許可權仍適用。
* 使用者許可權的更新仍會從[!DNL Audience Manager]進行管理。 [!DNL Admin Console]僅涵蓋使用者和群組管理。
* 管理員不需要停用舊版使用者帳戶。 舊的使用者帳戶會自動合併到已移轉的使用者帳戶中。
