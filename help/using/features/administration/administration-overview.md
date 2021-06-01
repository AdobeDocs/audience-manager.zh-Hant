---
description: 「管理」功能表下的選項可讓您建立Audience Manager使用者，並將其指派給群組。 您也可以檢視限制（特徵、區段、目的地和模型）。
keywords: rbac;RBAC；角色型；角色型；角色型存取控制
seo-description: 「管理」功能表下的選項可讓您建立Audience Manager使用者，並將其指派給群組。 您也可以檢視限制（特徵、區段、目的地和模型）。
seo-title: 管理
solution: Audience Manager
title: 管理
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: 管理
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1204'
ht-degree: 2%

---

# [!UICONTROL Administration] （RBAC控制） {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> 使用者帳戶管理正在移至[Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。 若要開始移轉使用者，我們要求所有Audience Manager客戶立即採取本文所述的必要措施：[Audience Manager使用者移轉至Admin Console](admin-console-migration.md)。
> 
> 所有客戶都完成移轉後，本檔案的使用者管理區段將會消失。


[!UICONTROL Administration]功能表下的選項可讓您建立Audience Manager使用者，並將其指派給群組。 您也可以檢視限制（特徵、區段、目的地和模型）。

使用[!DNL Audience Manager]的企業客戶需要一個資料管理平台來管理其所有資料，但必須能夠控制不同資料元素對特定業務部門的可見性。 您可以使用群組權限來完成此操作，也稱為[!UICONTROL Role-Based Access Control]([!UICONTROL RBAC])。

[!DNL Audience Manager] 使用群組來指派權限。未在使用者層級指派權限。 群組權限會系結至物件（[!UICONTROL traits]、區段等） 以及可對這些對象執行的操作（編輯、查看等）。 這些控制項也可透過Audience ManagerREST API使用。 請參閱[使用者管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)、[群組管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)和[權限管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API方法。

## 建立用戶{#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> 使用者帳戶管理正在移至[Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)。 若要開始移轉使用者，我們要求所有Audience Manager客戶立即採取本文所述的必要措施：[Audience Manager使用者移轉至Admin Console](admin-console-migration.md)。
> 
> 所有客戶都完成移轉後，本檔案的使用者管理區段就會消失。

在[!DNL Audience Manager]中建立用戶，並指定用戶詳細資訊、登錄狀態，以及將用戶分配給組。

1. 按一下 **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. 按一下![](assets/icon_add.png)以顯示[!UICONTROL Create New User]頁面。
1. 在&#x200B;**[!UICONTROL User Details]**&#x200B;下，填寫欄位：
   * **[!UICONTROL Username]:** 指定唯一的Audience Manager使用者名稱。
   * **[!UICONTROL First Name]:** 指定使用者的名字。
   * **[!UICONTROL Last Name]:** 指定使用者的姓氏。
   * **[!UICONTROL Email Address]:** 指定使用者的電子郵件地址。[!DNL Audience Manager] 不會定期傳送通知給使用者。[!DNL Audience Manager] 管理員可存取使用者的電子郵件地址，並可視需要手動傳送電子郵件給使用者。例如，如果用戶忘記了其密碼，則此欄位中指定的電子郵件地址用於發送臨時密碼和重置密碼的指示。
   * **[!UICONTROL Phone Number]:** 指定使用者的電話號碼。
   * **[!UICONTROL Is Admin]:** 指定此使用者是否為管 [!DNL Audience Manager] 理員。管理員使用者可以管理使用者（建立、編輯等） 和群組（建立、指派權限等）。 非管理員使用者只能控制自己的使用者設定檔，包括編輯其電子郵件地址和重設自己的密碼。 如需詳細資訊，請參閱[編輯帳戶設定](../../features/administration/edit-account-settings.md)。
1. 在&#x200B;**[!UICONTROL Login]**&#x200B;下，選擇所需的狀態：
   * **[!UICONTROL Active]：作**  用中使用者可 [!DNL Audience Manager] 以存取，並擁有群組成員資格授予的權限。
   * **[!UICONTROL Deactivated]:**  已停用的使用者 [!DNL Audience Manager] 無法存取，也沒有任何權限。如果您停用使用者，其使用者資訊會保留在[!DNL Audience Manager]中，如有需要，您可以簡單地重新啟用使用者。 如果刪除用戶，則如果用戶將來需要再次使用[!DNL Audience Manager]，則必須重新建立用戶。
   * **[!UICONTROL Expired]:** 使用者的密碼早於90天。
   * **[!UICONTROL Pending]:** 使用者具有暫時密碼，例如重設密碼後或全新帳戶，且尚未設定永久密碼。
   * **[!UICONTROL Locked Out]:** 5錯誤的登入嘗試會鎖定使用者。
1. 在&#x200B;**[!UICONTROL Assigned Groups]**下，從下拉式清單中，選取您要指派此使用者的所需群組。
有關組和權限的詳細資訊，請參閱[建立組](../../features/administration/administration-overview.md#create-group)。
1. 按一下 **[!UICONTROL Save]**.

## 建立 [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> 使用者帳戶管理正在移至[Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)。 為了開始移轉使用者，我們建議所有Audience Manager客戶立即採取本文所述的必要措施：[Audience Manager使用者移轉至Admin Console](admin-console-migration.md)。
> 
> 所有客戶都完成移轉後，此區段就會消失。

*group*&#x200B;是共用[!UICONTROL destination]、[!UICONTROL segment]和[!UICONTROL trait]對象訪問權限的用戶集合。 您可以僅將組限制為單個對象，或授予它們對不同對象組合的廣泛訪問權限。

<!-- t_create_groups.xml -->

要建立群組:

1. 按一下 **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. 按一下![](assets/icon_add.png)以開啟[!UICONTROL Group Settings]頁面。
3. 在 [!UICONTROL Group Details]:
   * 為群組命名。
   * 提供簡短的群組說明。
4. 在[!UICONTROL Group Members]中，按一下&#x200B;**[!UICONTROL Add Users]**&#x200B;選項中的用戶，將其添加到組。
5. 在[!UICONTROL Group Permissions]中，從&#x200B;**[!UICONTROL Add Object]**&#x200B;中選擇[特徵](../../features/traits/trait-details-page.md)、[段](../../features/segments/segments-purpose.md)或[目標](../../features/destinations/destinations.md)。
這會開啟您所選物件的權限視窗。
6. 選取您要群組成員擁有的權限核取方塊。
7. *（選用）* 將萬 [用字元](../../features/administration/administration-overview.md#wild-card-permissions) 權限指派給群組。
8. 按一下 **[!UICONTROL Save Group]**.

## 了解[!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> 使用者帳戶管理正在移至[Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)。 為了開始移轉使用者，我們建議所有Audience Manager客戶立即採取本文所述的必要措施：[Audience Manager使用者移轉至Admin Console](admin-console-migration.md)。
> 
> 所有客戶都完成移轉後，此區段就會消失。

使用[!UICONTROL Wild Card Permissions]簡化組權限管理。

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 為群組成員提供與、或相關聯的每個資料來源 [!UICONTROL segment]的自 [!UICONTROL destination]動存取 [!UICONTROL trait]權。相較之下，一般權限僅可讓您指派特定[!UICONTROL data sources]給其中一個物件。 而且，當添加新[!UICONTROL data sources]時，組成員無法訪問這些新源。

您必須開啟群組權限，並將新[!UICONTROL data sources]指派給群組。 [!UICONTROL Wild Card Permissions] 讓您避免進行此手動 [!UICONTROL data source] 更新程式。具有[!UICONTROL Wild Card Permissions]的組無需顯式授權即可訪問新的[!UICONTROL data sources]。

![](assets/wild-card.png)

請閱讀以下內容，了解[!UICONTROL wildcard permission]各代表的意義：

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS`  — 使用者可 [!UICONTROL traits] 以選取作為基 [!UICONTROL models]線。
* `EDIT_ALL_TRAITS`  — 使用者可編輯其 [!UICONTROL traits] 公司帳戶內設定的所有設定。
* `VIEW_ALL_TRAITS`  — 使用者可檢視其 [!UICONTROL traits] 公司帳戶內所有設定。
* `DELETE_ALL_TRAITS`  — 使用者可刪除其 [!UICONTROL traits] 公司帳戶內設定的所有。
* `CREATE_ALL_ALGO_TRAITS`  — 使用者可建 [!UICONTROL algorithmic traits]立。
* `MAP_ALL_TO_SEGMENTS`  — 使用者可將屬於其公 [!UICONTROL traits] 司的任何項目新增 [!UICONTROL segments]至。
* `CREATE_ALL_TRAITS`  — 使用者可建 [!UICONTROL traits]立。

**[!UICONTROL Reports]**

* `PTRREPORTS`  — 這 [!UICONTROL wildcard permission] 是指過時的功能，不久將從Audience Manager使用者介面中移除。

**[!UICONTROL Models]**

* `VIEW_MODELS`  — 使用者有權檢視屬 [!UICONTROL models] 於其公司的內容。

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS`  — 使用者可檢視屬於 [!UICONTROL derived signals] 其公司的所有。
* `CREATE_DERIVED_SIGNALS`  — 使用者可建 [!UICONTROL derived signals]立。
* `EDIT_DERIVED_SIGNALS`  — 使用者可以編輯屬 [!UICONTROL derived signals] 於其公司的所有。
* `DELETE_DERIVED_SIGNALS`  — 使用者可以刪除屬於其 [!UICONTROL derived signals] 公司的任何項目。

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS`  — 使用者可編輯其公 [!UICONTROL destinations] 司帳戶內設定的所有。
* `CREATE_DESTINATIONS`  — 使用者可建 [!UICONTROL destinations]立。
* `VIEW_ALL_DESTINATIONS`  — 使用者可檢視其公 [!UICONTROL destinations] 司帳戶內所有設定。
* `DELETE_ALL_DESTINATIONS`  — 使用者可刪除其公 [!UICONTROL destinations] 司帳戶內設定的所有。

**[!UICONTROL Tags]**

* `VIEW_TAGS`  — 使用者可執行其上的所有操作(檢視、建立、編輯、刪 [!UICONTROL Tag Containers]除)。

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS`  — 使用者可以對其測試群組執行所有作業(檢視、建立、編輯、 [!UICONTROL Audience Lab] 刪除)。

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS`  — 使用者可建立區段。
* `DELETE_ALL_SEGMENTS`  — 使用者可以刪除其公司帳戶中設定的所有區段。
* `MAP_ALL_TO_DESTINATIONS`  — 使用者可將屬於其公司的任何區段對應至目的地。
* `EDIT_ALL_SEGMENTS`  — 使用者可以編輯其公司帳戶中設定的所有區段。
* `MAP_ALL_SEGMENTS_TO_MODELS`  — 使用者可選取區段作為模型的基線。
* `VIEW_ALL_SEGMENTS`  — 使用者可檢視其公司帳戶內設定的所有區段。

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS`  — 使用者可檢視Data Explorer中擷取的所 [有訊號](/help/using/features/data-explorer/data-explorer-overview.md)。

## 使用個案 {#use-cases}

### 監視用戶訪問{#monitoring-user-access}

[!UICONTROL Role-Based Access Control] 可協助您監視使用者登入狀態，清楚掌握誰可以存取您的Audience Manager例項。

您可以視需要啟用和停用使用者帳戶，視您的業務需求而定。

![monitor-user-access](assets/monitor-user-access.png)

### 確保敏感[!UICONTROL Data Sources] {#protect-sensitive-data-sources}的訪問保護

您可以為每個使用者群組在[!UICONTROL trait]、區段和[!UICONTROL destination]層級設定[!UICONTROL Role-Based Access Control]。

此功能可協助您管理使用者檢視、建立、讀取、寫入和編輯特定資料集的方式，甚至限制使用者存取不應提供給他們的資料集。

![訪問保護](assets/access-protection.png)
