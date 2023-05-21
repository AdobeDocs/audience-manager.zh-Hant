---
description: 「管理」(Administration)菜單下的選項允許您建立Audience Manager用戶並將其分配給組。 您還可以查看限制（特徵、段、目標和模型）。
keywords: rbac;RBAC；基於角色；基於角色；基於角色的訪問控制
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: 管理
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: 8ef6e8eb4351c24b55703b1788c68c580f199fc8
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 2%

---

# [!UICONTROL Administration] （RBAC控制項） {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> 用戶帳戶管理正在移到 [Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。 要開始用戶遷移，我們要求所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager用戶遷移到Admin Console](admin-console-migration.md)。
> 
> 在所有客戶都遷移後，此文檔的用戶管理部分將消失。


以下選項 [!UICONTROL Administration] 的子菜單。 您還可以查看限制（特徵、段、目標和模型）。

企業客戶使用 [!DNL Audience Manager] 需要一個資料管理平台來管理其所有資料，但必須能夠控制不同資料元素對特定業務部門的可見性。 可以使用組權限(也稱為 [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC])。

[!DNL Audience Manager] 使用組來分配權限。 未在用戶級別分配權限。 組權限與對象關聯([!UICONTROL traits]、段等) 以及可以對這些對象執行的操作（編輯、查看等）。 這些控制項也可通過Audience ManagerREST API獲得。 請參閱 [用戶管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)。 [組管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md), [權限管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API方法。

## 建立用戶 {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> 用戶帳戶管理正在移到 [Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。 要開始用戶遷移，我們要求所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager用戶遷移到Admin Console](admin-console-migration.md)。
> 
> 在所有客戶都遷移後，此文檔的用戶管理部分將消失。
在中建立用戶 [!DNL Audience Manager] 並指定用戶詳細資訊、登錄狀態以及將用戶分配給組。

1. 按一下 **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. 按一下 ![](assets/icon_add.png) 顯示 [!UICONTROL Create New User] 的子菜單。
1. 下 **[!UICONTROL User Details]**，填寫欄位：
   * **[!UICONTROL Username]:** 為Audience Manager指定唯一用戶名。
   * **[!UICONTROL First Name]:** 指定用戶的名。
   * **[!UICONTROL Last Name]:** 指定用戶的姓。
   * **[!UICONTROL Email Address]:** 指定用戶的電子郵件地址。 [!DNL Audience Manager] 不向用戶發送常規通知。 [!DNL Audience Manager] 管理員有權訪問用戶的電子郵件地址，並可根據需要手動向用戶發送電子郵件。 例如，如果用戶忘記了密碼，則此欄位中指定的電子郵件地址用於發送臨時密碼和重置密碼的說明。
   * **[!UICONTROL Phone Number]:** 指定用戶的電話號碼。
   * **[!UICONTROL Is Admin]:** 指定此用戶是否為 [!DNL Audience Manager] 管理員。 管理員用戶可以管理用戶（建立、編輯等） 和組（建立、分配權限等）。 非管理員用戶只能控制自己的用戶配置檔案，包括編輯其電子郵件地址和重置自己的密碼。 有關詳細資訊，請參見 [編輯帳戶設定](../../features/administration/edit-account-settings.md)。
1. 下 **[!UICONTROL Login]**，選擇所需狀態：
   * **[!UICONTROL Active]:**  活動用戶可以訪問 [!DNL Audience Manager] 並具有組成員資格授予的權限。
   * **[!UICONTROL Deactivated]:**  已停用的用戶無法訪問 [!DNL Audience Manager] 沒有任何權限。 如果停用用戶，則其用戶資訊將保留在 [!DNL Audience Manager] 如有必要，你可以簡單地重新激活它們。 如果刪除用戶，則如果用戶需要使用，則必須重新建立 [!DNL Audience Manager] 在未來。
   * **[!UICONTROL Expired]:** 用戶密碼超過90天。
   * **[!UICONTROL Pending]:** 用戶具有臨時密碼，例如在密碼重置後或作為全新帳戶，而且他們尚未設定永久密碼。
   * **[!UICONTROL Locked Out]:** 5次不正確的登錄嘗試將鎖定用戶。
1. 下 **[!UICONTROL Assigned Groups]**，從下拉清單中，選擇要為此用戶分配的所需組。
有關組和權限的詳細資訊，請參見 [建立組](../../features/administration/administration-overview.md#create-group)。
1. 按一下 **[!UICONTROL Save]**.

## 建立 [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> 用戶帳戶管理正在移到 [Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。 要開始用戶遷移，我們建議所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager用戶遷移到Admin Console](admin-console-migration.md)。
> 
> 所有客戶都遷移後，此部分將消失。

A *組* 是共用訪問權限的用戶的集合 [!UICONTROL destination]。 [!UICONTROL segment], [!UICONTROL trait] 對象。 您可以僅將組限制為單個對象，或授予它們對不同對象組合的廣泛訪問權限。

<!-- t_create_groups.xml -->

要建立群組:

1. 按一下 **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. 按一下  ![](assets/icon_add.png) 開啟 [!UICONTROL Group Settings] 的子菜單。
3. 在 [!UICONTROL Group Details]:
   * 命名組。
   * 提供簡短的組說明。
4. 在 [!UICONTROL Group Members]，按一下 **[!UICONTROL Add Users]** 選項，將其添加到組中。
5. 在 [!UICONTROL Group Permissions]，選擇 [性](../../features/traits/trait-details-page.md)。 [分部](../../features/segments/segments-purpose.md)或 [目標](../../features/destinations/destinations.md) 從 **[!UICONTROL Add Object]**。
這將開啟所選對象的權限窗口。
6. 選中希望組成員擁有的權限的複選框。
7. *（可選）* 分配 [通配符權限](../../features/administration/administration-overview.md#wild-card-permissions) 組。
8. 按一下 **[!UICONTROL Save Group]**.

## 理解 [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> 用戶帳戶管理正在移到 [Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。 要開始用戶遷移，我們建議所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager用戶遷移到Admin Console](admin-console-migration.md)。
> 
> 所有客戶都遷移後，此部分將消失。

簡化組權限管理 [!UICONTROL Wild Card Permissions]。

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 為組成員自動訪問與關聯的每個資料源 [!UICONTROL segment]。 [!UICONTROL destination]或 [!UICONTROL trait]。 通過比較，常規權限僅允許您指定特定 [!UICONTROL data sources] 這些物體中的一個。 當你添加新 [!UICONTROL data sources]，組成員無法訪問這些新源。

您必須開啟組權限並分配這些新權限 [!UICONTROL data sources] 組。 [!UICONTROL Wild Card Permissions] 讓您避免使用本手冊 [!UICONTROL data source] 更新進程。 組 [!UICONTROL Wild Card Permissions] 獲取新 [!UICONTROL data sources] 沒有明確的授權。

![](assets/wild-card.png)

請閱讀下面，瞭解每個 [!UICONTROL wildcard permission] 指：

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS`  — 用戶可以選擇 [!UICONTROL traits] 作為 [!UICONTROL models]。
* `EDIT_ALL_TRAITS`  — 用戶可以編輯所有 [!UICONTROL traits] 在公司帳戶中設定。
* `VIEW_ALL_TRAITS`  — 用戶可以查看所有 [!UICONTROL traits] 在公司帳戶中設定。
* `DELETE_ALL_TRAITS`  — 用戶可刪除所有 [!UICONTROL traits] 在公司帳戶中設定。
* `CREATE_ALL_ALGO_TRAITS`  — 用戶可以建立 [!UICONTROL algorithmic traits]。
* `MAP_ALL_TO_SEGMENTS`  — 用戶可以添加 [!UICONTROL traits] 屬於 [!UICONTROL segments]。
* `CREATE_ALL_TRAITS`  — 用戶可以建立 [!UICONTROL traits]。

**[!UICONTROL Models]**

* `VIEW_MODELS`  — 用戶有權查看 [!UICONTROL models] 屬於他們公司。

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS`  — 用戶可以查看 [!UICONTROL derived signals] 屬於他們公司。
* `CREATE_DERIVED_SIGNALS`  — 用戶可以建立 [!UICONTROL derived signals]。
* `EDIT_DERIVED_SIGNALS`  — 用戶可以編輯 [!UICONTROL derived signals] 屬於他們公司。
* `DELETE_DERIVED_SIGNALS`  — 用戶可以刪除 [!UICONTROL derived signals] 屬於他們公司。

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS`  — 用戶可以編輯 [!UICONTROL destinations] 在公司帳戶中設定。
* `CREATE_DESTINATIONS`  — 用戶可以建立 [!UICONTROL destinations]。
* `VIEW_ALL_DESTINATIONS`  — 用戶可以查看 [!UICONTROL destinations] 在公司帳戶中設定。
* `DELETE_ALL_DESTINATIONS`  — 用戶可以刪除 [!UICONTROL destinations] 在公司帳戶中設定。

**[!UICONTROL Tags]**

* `VIEW_TAGS`  — 用戶可以執行其上的所有操作（查看、建立、編輯、刪除） [!UICONTROL Tag Containers]。

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS`  — 用戶可以執行其上的所有操作（查看、建立、編輯、刪除） [!UICONTROL Audience Lab] test組。

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS`  — 用戶可以建立段。
* `DELETE_ALL_SEGMENTS`  — 用戶可以刪除公司帳戶中設定的所有段。
* `MAP_ALL_TO_DESTINATIONS`  — 用戶可以將屬於公司的任何段映射到目標。
* `EDIT_ALL_SEGMENTS`  — 用戶可以編輯其公司帳戶中設定的所有段。
* `MAP_ALL_SEGMENTS_TO_MODELS`  — 用戶可以選擇段作為模型的基線。
* `VIEW_ALL_SEGMENTS`  — 用戶可以查看其公司帳戶中設定的所有段。

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS`  — 用戶可以查看捕獲到的所有信號 [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md)。

## 使用個案 {#use-cases}

### 監視用戶訪問 {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] 可以幫助您監視用戶登錄狀態，讓您清楚地瞭解誰可以訪問您的Audience Manager實例。

根據您的業務要求，您可以根據需要啟用和禁用用戶帳戶。

![監視用戶訪問](assets/monitor-user-access.png)

### 確保對敏感內容的訪問保護 [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

您可以配置 [!UICONTROL Role-Based Access Control] 在 [!UICONTROL trait]、段和 [!UICONTROL destination] 級別，用於每個用戶組。

此功能可幫助您管理用戶查看、建立、讀取、寫入和編輯特定資料集的方式，甚至限制用戶訪問不應由他們訪問的資料集。

![訪問保護](assets/access-protection.png)
