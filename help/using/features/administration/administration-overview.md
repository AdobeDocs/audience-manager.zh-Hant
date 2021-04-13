---
description: 「管理」(Administration)菜單下的選項可讓您建立Audience Manager用戶並將其分配給組。 您也可以檢視限制（特徵、區段、目的地和模型）。
keywords: rbac; RBAC；基於角色；基於角色；基於角色的訪問控制
seo-description: 「管理」(Administration)菜單下的選項可讓您建立Audience Manager用戶並將其分配給組。 您也可以檢視限制（特徵、區段、目的地和模型）。
seo-title: 管理
solution: Audience Manager
title: 管理
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: 管理
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1204'
ht-degree: 2%

---

# [!UICONTROL Administration] （RBAC控制）  {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> 用戶帳戶管理正在移至[Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。 為開始使用者移轉，我們要求所有Audience Manager客戶立即採取本文所述的必要措施：[Audience Manager用戶遷移到Admin Console](admin-console-migration.md)。
> 
> 在所有客戶都移轉後，本檔案的使用者管理區段將會消失。


[!UICONTROL Administration]功能表下的選項可讓您建立Audience Manager使用者，並指派給群組。 您也可以檢視限制（特徵、區段、目的地和模型）。

使用[!DNL Audience Manager]的企業客戶需要一個資料管理平台來處理其所有資料，但必須能夠控制不同資料元素對特定業務單位的可見性。 您可以使用群組權限(也稱為[!UICONTROL Role-Based Access Control]([!UICONTROL RBAC]))來完成此作業。

[!DNL Audience Manager] 使用群組來指派權限。在使用者層級不會指派權限。 群組權限系結至物件（[!UICONTROL traits]、區段等） 以及可對這些物件執行的動作（編輯、檢視等）。 這些控制項也可透過Audience ManagerREST API取得。 請參閱[使用者管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)、[群組管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)和[權限管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API方法。

## 建立用戶{#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> 用戶帳戶管理正在移至[Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)。 為開始使用者移轉，我們要求所有Audience Manager客戶立即採取本文所述的必要措施：[Audience Manager用戶遷移到Admin Console](admin-console-migration.md)。
> 
> 在所有客戶都完成移轉後，本檔案的使用者管理區段將會消失。

在[!DNL Audience Manager]中建立使用者，並指定使用者詳細資訊、登入狀態，以及指派使用者至群組。

1. 按一下 **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. 按一下![](assets/icon_add.png)以顯示[!UICONTROL Create New User]頁面。
1. 在&#x200B;**[!UICONTROL User Details]**&#x200B;下方，填寫欄位：
   * **[!UICONTROL Username]：指** 定Audience Manager的唯一用戶名。
   * **[!UICONTROL First Name]:** 指定使用者的名字。
   * **[!UICONTROL Last Name]:** 指定使用者的姓氏。
   * **[!UICONTROL Email Address]:** 指定使用者的電子郵件地址。[!DNL Audience Manager] 不會定期傳送通知給使用者。[!DNL Audience Manager] 管理員可存取使用者的電子郵件地址，並可視需要手動以電子郵件寄送使用者。例如，如果使用者忘記密碼，則此欄位中指定的電子郵件地址會用來傳送暫時密碼和重設密碼的指示。
   * **[!UICONTROL Phone Number]:** 指定使用者的電話號碼。
   * **[!UICONTROL Is Admin]：指** 定此使用者是否為管 [!DNL Audience Manager] 理員。管理員使用者可以管理使用者（建立、編輯等） 和群組（建立、指派權限等）。 非管理員使用者只能控制自己的使用者設定檔，包括編輯其電子郵件地址及重設自己的密碼。 如需詳細資訊，請參閱[編輯您的帳戶設定](../../features/administration/edit-account-settings.md)。
1. 在&#x200B;**[!UICONTROL Login]**&#x200B;下，選擇所要的狀態：
   * **[!UICONTROL Active]：作**  用中使用者可 [!DNL Audience Manager] 以存取並擁有群組成員資格的權限。
   * **[!UICONTROL Deactivated]：已**  停用的使用者無 [!DNL Audience Manager] 法存取，也沒有任何權限。如果您停用使用者，其使用者資訊會保留在[!DNL Audience Manager]中，如有需要，您可以輕鬆重新啟動使用者。 如果您移除使用者，如果使用者日後需要再次使用[!DNL Audience Manager]，您必須重新建立。
   * **[!UICONTROL Expired]:** 使用者的密碼早於90天。
   * **[!UICONTROL Pending]:** 使用者具有暫時密碼，例如重設密碼後或全新帳戶，但尚未設定永久密碼。
   * **[!UICONTROL Locked Out]:** 5錯誤的登入嘗試會鎖定使用者。
1. 在&#x200B;**[!UICONTROL Assigned Groups]**下方，從下拉式清單中選取您要指派此使用者的群組。
如需群組和權限的詳細資訊，請參閱[建立群組](../../features/administration/administration-overview.md#create-group)。
1. 按一下 **[!UICONTROL Save]**.

## 建立 [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> 用戶帳戶管理正在移至[Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)。 為開始使用者移轉，我們建議所有Audience Manager客戶立即採取本文所述的必要措施：[Audience Manager用戶遷移到Admin Console](admin-console-migration.md)。
> 
> 所有客戶都已移轉後，本節將會消失。

*group*&#x200B;是一組對[!UICONTROL destination]、[!UICONTROL segment]和[!UICONTROL trait]對象共用訪問權限的用戶。 您可以僅將群組限制為單一物件，或讓群組廣泛存取不同物件的組合。

<!-- t_create_groups.xml -->

要建立群組:

1. 按一下 **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. 按一下![](assets/icon_add.png)開啟[!UICONTROL Group Settings]頁。
3. 在 [!UICONTROL Group Details]:
   * 命名群組。
   * 提供簡短的群組說明。
4. 在[!UICONTROL Group Members]中，按一下&#x200B;**[!UICONTROL Add Users]**&#x200B;選項中的用戶，將其添加到組。
5. 在[!UICONTROL Group Permissions]中，從&#x200B;**[!UICONTROL Add Object]**&#x200B;中選擇[特徵](../../features/traits/trait-details-page.md)、[區段](../../features/segments/segments-purpose.md)或[目標](../../features/destinations/destinations.md)。
這會開啟您所選物件的權限視窗。
6. 選中您希望群組成員擁有的權限的核取方塊。
7. *（選用）* 指派 [萬用](../../features/administration/administration-overview.md#wild-card-permissions) 字元權限至群組。
8. 按一下 **[!UICONTROL Save Group]**.

## 瞭解[!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> 用戶帳戶管理正在移至[Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)。 為開始使用者移轉，我們建議所有Audience Manager客戶立即採取本文所述的必要措施：[Audience Manager用戶遷移到Admin Console](admin-console-migration.md)。
> 
> 所有客戶都已移轉後，本節將會消失。

使用[!UICONTROL Wild Card Permissions]簡化群組權限管理。

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 為群組成員提供與、或關聯的每個資料來源的自 [!UICONTROL segment]動 [!UICONTROL destination]存取權 [!UICONTROL trait]。比較而言，一般權限只能讓您指派特定[!UICONTROL data sources]至其中一個物件。 而且，當您新增[!UICONTROL data sources]時，群組成員無法存取這些新來源。

您必須開啟群組權限，並指派新的[!UICONTROL data sources]給群組。 [!UICONTROL Wild Card Permissions] 讓您避免手動更 [!UICONTROL data source] 新程式。具有[!UICONTROL Wild Card Permissions]的群組在沒有明確授權的情況下可存取新[!UICONTROL data sources]。

![](assets/wild-card.png)

請閱讀以下內容，瞭解每個[!UICONTROL wildcard permission]的含義：

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` -用戶可以 [!UICONTROL traits] 選擇作為基準 [!UICONTROL models]。
* `EDIT_ALL_TRAITS` -使用者可編輯其公 [!UICONTROL traits] 司帳戶內所有設定。
* `VIEW_ALL_TRAITS` -使用者可檢視其 [!UICONTROL traits] 公司帳戶內的所有設定。
* `DELETE_ALL_TRAITS` -使用者可刪除其公 [!UICONTROL traits] 司帳戶內所有設定。
* `CREATE_ALL_ALGO_TRAITS` -使用者可以建立 [!UICONTROL algorithmic traits]。
* `MAP_ALL_TO_SEGMENTS` -使用者可將屬於其公 [!UICONTROL traits] 司的任何項目新增至 [!UICONTROL segments]。
* `CREATE_ALL_TRAITS` -使用者可以建立 [!UICONTROL traits]。

**[!UICONTROL Reports]**

* `PTRREPORTS` -這指 [!UICONTROL wildcard permission] 的是過時的功能，不久將從Audience Manager用戶介面中刪除。

**[!UICONTROL Models]**

* `VIEW_MODELS` -使用者有權檢視屬 [!UICONTROL models] 於其公司的內容。

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` -使用者可檢視其公 [!UICONTROL derived signals] 司的所有資產。
* `CREATE_DERIVED_SIGNALS` -使用者可以建立 [!UICONTROL derived signals]。
* `EDIT_DERIVED_SIGNALS` -使用者可編輯其公 [!UICONTROL derived signals] 司的所有資產。
* `DELETE_DERIVED_SIGNALS` -用戶可以刪除屬於其公 [!UICONTROL derived signals] 司的任何一個。

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` -使用者可編輯其公 [!UICONTROL destinations] 司帳戶內的所有設定。
* `CREATE_DESTINATIONS` -使用者可以建立 [!UICONTROL destinations]。
* `VIEW_ALL_DESTINATIONS` -使用者可檢視其公 [!UICONTROL destinations] 司帳戶內的所有設定。
* `DELETE_ALL_DESTINATIONS` -使用者可刪除其公 [!UICONTROL destinations] 司帳戶內的所有設定。

**[!UICONTROL Tags]**

* `VIEW_TAGS` -使用者可以在其上執行一切（檢視、建立、編輯、刪除） [!UICONTROL Tag Containers]。

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` -使用者可對其測試群組執行一切(檢視、建立、編輯、刪 [!UICONTROL Audience Lab] 除)。

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` -使用者可以建立區段。
* `DELETE_ALL_SEGMENTS` -使用者可刪除其公司帳戶內設定的所有區段。
* `MAP_ALL_TO_DESTINATIONS` -使用者可將屬於其公司的任何區段對應至目標。
* `EDIT_ALL_SEGMENTS` -使用者可編輯其公司帳戶內設定的所有區段。
* `MAP_ALL_SEGMENTS_TO_MODELS` -使用者可選取區段作為模型的基準。
* `VIEW_ALL_SEGMENTS` -使用者可檢視其公司帳戶內設定的所有區段。

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` -用戶可以查看Data Explorer中捕獲的所有 [信號](/help/using/features/data-explorer/data-explorer-overview.md)。

## 使用個案 {#use-cases}

### 監視用戶訪問{#monitoring-user-access}

[!UICONTROL Role-Based Access Control] 可協助您監控使用者登入狀態，讓您清楚瞭解哪些人可以存取您的Audience Manager例項。

視您的業務需求而定，您可以視需要啟用和停用使用者帳戶。

![monitor-user-access](assets/monitor-user-access.png)

### 確保敏感[!UICONTROL Data Sources] {#protect-sensitive-data-sources}的訪問保護

您可以為每個使用者群組設定[!UICONTROL trait]、區段和[!UICONTROL destination]等級的[!UICONTROL Role-Based Access Control]。

此功能可協助您管理使用者檢視、建立、讀取、寫入和編輯特定資料集的方式，甚至限制使用者存取他們無法存取的資料集。

![接入保護](assets/access-protection.png)
