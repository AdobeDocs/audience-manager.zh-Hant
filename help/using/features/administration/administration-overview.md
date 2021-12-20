---
description: 「管理」功能表下的選項可讓您建立Audience Manager使用者，並將其指派給群組。 您也可以檢視限制（特徵、區段、目的地和模型）。
keywords: rbac;RBAC；角色型；角色型；角色型存取控制
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

# [!UICONTROL Administration] （RBAC控制） {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> 使用者帳戶管理正在移至 [Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html). 若要開始移轉使用者，我們要求所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager使用者移轉至Admin Console](admin-console-migration.md).
> 
> 所有客戶都完成移轉後，本檔案的使用者管理區段將會消失。


下列選項 [!UICONTROL Administration] 功能表，您可以建立Audience Manager使用者並將其指派至群組。 您也可以檢視限制（特徵、區段、目的地和模型）。

企業客戶使用 [!DNL Audience Manager] 需要一個資料管理平台來管理其所有資料，但必須能夠控制不同資料元素對特定業務部門的可見性。 您可以使用群組權限來完成此操作，亦稱為 [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC])。

[!DNL Audience Manager] 使用群組來指派權限。 未在使用者層級指派權限。 群組權限會系結至物件([!UICONTROL traits]、區段等) 以及可對這些對象執行的操作（編輯、查看等）。 這些控制項也可透過Audience ManagerREST API使用。 請參閱 [使用者管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [群組管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)，和 [權限管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API方法。

## 建立使用者 {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> 使用者帳戶管理正在移至 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). 若要開始移轉使用者，我們要求所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager使用者移轉至Admin Console](admin-console-migration.md).
> 
> 所有客戶都完成移轉後，本檔案的使用者管理區段就會消失。
在中建立使用者 [!DNL Audience Manager] 並指定使用者詳細資訊、登入狀態，以及將使用者指派至群組。

1. 按一下 **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. 按一下 ![](assets/icon_add.png) 顯示 [!UICONTROL Create New User] 頁面。
1. 在 **[!UICONTROL User Details]**，填寫欄位：
   * **[!UICONTROL Username]:** 指定唯一的Audience Manager使用者名稱。
   * **[!UICONTROL First Name]:** 指定使用者的名字。
   * **[!UICONTROL Last Name]:** 指定使用者的姓氏。
   * **[!UICONTROL Email Address]:** 指定使用者的電子郵件地址。 [!DNL Audience Manager] 不會定期傳送通知給使用者。 [!DNL Audience Manager] 管理員可存取使用者的電子郵件地址，並可視需要手動傳送電子郵件給使用者。 例如，如果用戶忘記了其密碼，則此欄位中指定的電子郵件地址用於發送臨時密碼和重置密碼的指示。
   * **[!UICONTROL Phone Number]:** 指定使用者的電話號碼。
   * **[!UICONTROL Is Admin]:** 指定此使用者是否為 [!DNL Audience Manager] 管理員。 管理員使用者可以管理使用者（建立、編輯等） 和群組（建立、指派權限等）。 非管理員使用者只能控制自己的使用者設定檔，包括編輯其電子郵件地址和重設自己的密碼。 如需詳細資訊，請參閱 [編輯帳戶設定](../../features/administration/edit-account-settings.md).
1. 在 **[!UICONTROL Login]**，選擇所需的狀態：
   * **[!UICONTROL Active]:**  活動使用者可存取 [!DNL Audience Manager] 和擁有群組成員資格所授予的權限。
   * **[!UICONTROL Deactivated]:**  已停用的使用者無法存取 [!DNL Audience Manager] 和沒有任何權限。 如果您停用使用者，其使用者資訊會保留在 [!DNL Audience Manager] 如有必要，您可以簡單地重新啟用它們。 如果您移除使用者，則必須重新建立使用者（如果他們需要使用） [!DNL Audience Manager] 在未來。
   * **[!UICONTROL Expired]:** 用戶的密碼早於90天。
   * **[!UICONTROL Pending]:** 用戶具有臨時密碼，例如在密碼重置後或作為全新帳戶，並且他們尚未設定永久密碼。
   * **[!UICONTROL Locked Out]:** 5次不正確的登入嘗試會鎖定使用者。
1. 在 **[!UICONTROL Assigned Groups]**，從下拉式清單中，選取您要指派此使用者的所需群組。
如需群組和權限的詳細資訊，請參閱 [建立群組](../../features/administration/administration-overview.md#create-group).
1. 按一下 **[!UICONTROL Save]**.

## 建立 [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> 使用者帳戶管理正在移至 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). 為了開始移轉使用者，我們建議所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager使用者移轉至Admin Console](admin-console-migration.md).
> 
> 所有客戶都完成移轉後，此區段就會消失。

A *群組* 是共用存取權的使用者集合 [!UICONTROL destination], [!UICONTROL segment]，和 [!UICONTROL trait] 對象。 您可以僅將組限制為單個對象，或授予它們對不同對象組合的廣泛訪問權限。

<!-- t_create_groups.xml -->

要建立群組:

1. 按一下 **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. 按一下  ![](assets/icon_add.png) 開啟 [!UICONTROL Group Settings] 頁面。
3. 在 [!UICONTROL Group Details]:
   * 為群組命名。
   * 提供簡短的群組說明。
4. 在 [!UICONTROL Group Members]，按一下 **[!UICONTROL Add Users]** 選項將其新增至群組。
5. 在 [!UICONTROL Group Permissions]，選取 [特徵](../../features/traits/trait-details-page.md), [區段](../../features/segments/segments-purpose.md)，或 [目的地](../../features/destinations/destinations.md) 從 **[!UICONTROL Add Object]**.
這會開啟您所選物件的權限視窗。
6. 選取您要群組成員擁有的權限核取方塊。
7. *（可選）* 指派 [萬用字元權限](../../features/administration/administration-overview.md#wild-card-permissions) 加入小組。
8. 按一下 **[!UICONTROL Save Group]**.

## 了解 [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> 使用者帳戶管理正在移至 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). 為了開始移轉使用者，我們建議所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager使用者移轉至Admin Console](admin-console-migration.md).
> 
> 所有客戶都完成移轉後，此區段就會消失。

使用簡化群組權限管理 [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 授予群組成員對與 [!UICONTROL segment], [!UICONTROL destination]，或 [!UICONTROL trait]. 相較之下，一般權限僅可讓您指派特定 [!UICONTROL data sources] 這些物體。 當您新增 [!UICONTROL data sources]，群組成員將無法存取這些新來源。

您必須開啟群組權限並指派這些新權限 [!UICONTROL data sources] 加入小組。 [!UICONTROL Wild Card Permissions] 讓您避免使用本手冊 [!UICONTROL data source] 更新程式。 群組 [!UICONTROL Wild Card Permissions] 存取新 [!UICONTROL data sources] 沒有明確的授權。

![](assets/wild-card.png)

請閱讀下文，了解各自的 [!UICONTROL wildcard permission] 表示：

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS`  — 使用者可選擇 [!UICONTROL traits] 作為 [!UICONTROL models].
* `EDIT_ALL_TRAITS`  — 使用者可以編輯所有 [!UICONTROL traits] 在其公司帳戶內設定。
* `VIEW_ALL_TRAITS`  — 使用者可檢視全部 [!UICONTROL traits] 在其公司帳戶內設定。
* `DELETE_ALL_TRAITS`  — 使用者可刪除所有 [!UICONTROL traits] 在其公司帳戶內設定。
* `CREATE_ALL_ALGO_TRAITS`  — 使用者可建立 [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS`  — 使用者可新增 [!UICONTROL traits] 屬於 [!UICONTROL segments].
* `CREATE_ALL_TRAITS`  — 使用者可建立 [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS`  — 使用者有權檢視 [!UICONTROL models] 屬於他們的公司。

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS`  — 使用者可檢視 [!UICONTROL derived signals] 屬於他們的公司。
* `CREATE_DERIVED_SIGNALS`  — 使用者可建立 [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS`  — 使用者可編輯 [!UICONTROL derived signals] 屬於他們的公司。
* `DELETE_DERIVED_SIGNALS`  — 使用者可以刪除 [!UICONTROL derived signals] 屬於他們的公司。

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS`  — 使用者可編輯 [!UICONTROL destinations] 在其公司帳戶內設定。
* `CREATE_DESTINATIONS`  — 使用者可建立 [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS`  — 使用者可檢視 [!UICONTROL destinations] 在其公司帳戶內設定。
* `DELETE_ALL_DESTINATIONS`  — 使用者可刪除 [!UICONTROL destinations] 在其公司帳戶內設定。

**[!UICONTROL Tags]**

* `VIEW_TAGS`  — 使用者可執行其上的所有工作（檢視、建立、編輯、刪除） [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS`  — 使用者可執行其上的所有工作（檢視、建立、編輯、刪除） [!UICONTROL Audience Lab] 測試群組。

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS`  — 使用者可建立區段。
* `DELETE_ALL_SEGMENTS`  — 使用者可以刪除其公司帳戶中設定的所有區段。
* `MAP_ALL_TO_DESTINATIONS`  — 使用者可將屬於其公司的任何區段對應至目的地。
* `EDIT_ALL_SEGMENTS`  — 使用者可以編輯其公司帳戶中設定的所有區段。
* `MAP_ALL_SEGMENTS_TO_MODELS`  — 使用者可選取區段作為模型的基線。
* `VIEW_ALL_SEGMENTS`  — 使用者可檢視其公司帳戶內設定的所有區段。

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS`  — 使用者可檢視擷取到 [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## 使用個案 {#use-cases}

### 監控使用者存取 {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] 可協助您監視使用者登入狀態，清楚掌握誰可以存取您的Audience Manager例項。

您可以視需要啟用和停用使用者帳戶，視您的業務需求而定。

![monitor-user-access](assets/monitor-user-access.png)

### 確保對敏感的訪問保護 [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

您可以設定 [!UICONTROL Role-Based Access Control] at [!UICONTROL trait]、區段和 [!UICONTROL destination] 層級，適用於每個使用者群組。

此功能可協助您管理使用者檢視、建立、讀取、寫入和編輯特定資料集的方式，甚至限制使用者存取不應提供給他們的資料集。

![訪問保護](assets/access-protection.png)
