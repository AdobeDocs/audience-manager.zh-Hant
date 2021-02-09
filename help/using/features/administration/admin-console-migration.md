---
description: Audience Manager使用者管理正移至Adobe Admin Console。 本文將說明您需要做什麼來準備使用者移轉，以及移轉完成後將會變更什麼。
keywords: rbac; RBAC；基於角色；基於角色；基於角色的訪問控制
seo-description: Audience Manager使用者管理正移至Adobe Admin Console。 本文將說明您需要做什麼來準備使用者移轉，以及移轉完成後將會變更什麼。
seo-title: Audience Manager使用者移轉至Admin Console
solution: Audience Manager
title: Audience Manager使用者移轉至Admin Console
feature: Administration
translation-type: tm+mt
source-git-commit: 04504d4561414f9558a1f1f4db33cbcf535d54af
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 3%

---


# [!DNL Audience Manager] 使用者移轉至  [!DNL Admin Console] {#user-migration}

## 概述 {#overview}

[!DNL Audience Manager] 使用者帳戶管理已移轉至 [Adobe Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)，以簡化整個Adobe解決方案的使用體驗。

使用[!DNL Admin Console]的優點包括：

| 好處 | 說明 |
|---|---|
| 單一登入 跨解決方案 | [!DNL Audience Manager] 使用者可以使用 [!DNL Experience Cloud] 其或登入和所有其他解決 [!DNL Adobe ID] 方案 [!DNL Enterprise ID]。此登入可讓您存取整合式解決方案和[!DNL Experience Cloud]核心服務。 移轉後，嘗試透過舊版登入(`bank.demdex.com`)登入的使用者將會重新導向至`experiencecloud.adobe.com`。 |
| 管理使用者和群組 | 移轉完成後，[!DNL Audience Manager]管理員將只管理[[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/)中的用戶和組。 |
| 管理產品與服務 | 在[[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/)中，管理員可以： <ul><li>建立、更新和移除使用者</li><li>授與解決方案與服務的存取權</li><li>授予使用者權限</li></ul> |

為方便使用者移轉，我們要求所有[!DNL Audience Manager]管理員依照本文所述的步驟，盡快將其使用者帳戶移轉至[Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)。

## 使用者需要執行哪些動作{#what-to-do-users}

身為Audience Manager使用者，您只需聯絡您的[!DNL Audience Manager]管理員，要求他們在[!DNL Admin Console]中為您建立新的使用者帳戶。

## {#what-to-do-admins}管理員需要執行什麼

Audience Manager管理員應依照下列步驟將使用者移轉至[!DNL Admin Console]。

1. 前往[https://adminconsole.adobe.com](https://adminconsole.adobe.com)，並使用您的Adobe ID或Enterprise ID登入。 如果您沒有[!DNL Admin Console]的存取權，請連絡客戶服務或您的Adobe顧問。
2. 請參閱[!DNL Adobe Admin Console] [說明指南](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html)，以取得如何建立和管理使用者帳戶的詳細說明。
3. 為您所有現有的Audience Manager使用者建立新的使用者帳戶。
4. 通知您的使用者有關新建立的使用者帳戶。 當使用者移轉至[!DNL Admin Console]時，他們應停止使用舊版登入。

## 用戶遷移注意事項{#considerations}

使用者和管理員在Audience Manager使用者移轉時應牢記下列考量：

* 在Admin Console中建立新的使用者帳戶後，其舊有使用者帳戶的現有權限將會自動保留。 管理員不需要在[!DNL Admin Console]中指派新權限。
* 管理員不需要停用舊版使用者帳戶。 舊用戶帳戶將自動合併到已遷移的用戶帳戶中。
* 使用者權限的更新仍會從[!DNL Audience Manager]管理。 [!DNL Admin Console]僅涵蓋使用者和群組管理。