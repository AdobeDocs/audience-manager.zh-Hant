---
description: 「管理」功能表底下的選項可讓您建立Audience Manager使用者，並將其指派給群組。 您也可以檢視限制（特徵、區段、目的地和模型）。
keywords: RBAC；RBAC；角色型；角色型；角色型存取控制
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: 管理
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 0%

---

# [!UICONTROL Administration] （RBAC控制項） {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> 使用者帳戶管理正在移至[Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。 若要開始使用者移轉，我們要求所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager使用者移轉至Admin Console](admin-console-migration.md)。
> 
> 所有客戶都完成移轉後，本檔案的使用者管理部分將會消失。

>[!IMPORTANT]
>
> 在您可以使用[!DNL RBAC]之前，此功能必須由Adobe為您的組織啟用。 請洽詢您的帳戶團隊以要求[!DNL RBAC]啟用，或聯絡客戶服務。


[!UICONTROL Administration]功能表下的選項可讓您建立Audience Manager使用者，並將其指派給群組。 您也可以檢視限制（特徵、區段、目的地和模型）。

使用[!DNL Audience Manager]的企業客戶的所有資料都需要一個資料管理平台，但必須能夠控制特定業務單位中不同資料元素的可見度。 您可以使用群組許可權(也稱為[!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]))來達到此目的。

[!DNL Audience Manager]使用群組來指派許可權。 未在使用者層級指派許可權。 群組許可權繫結至物件（[!UICONTROL traits]、區段等）以及您可以對這些物件執行的動作（編輯、檢視等）。 這些控制項也可透過Audience Manager REST API取得。 請參閱[使用者管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)、[群組管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)和[許可權管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API方法。

## 建立使用者 {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> 使用者帳戶管理正在移至[Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。 若要開始使用者移轉，我們要求所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager使用者移轉至Admin Console](admin-console-migration.md)。
> 
> 所有客戶都完成移轉後，本檔案的使用者管理區段將會消失。
> 
在[!DNL Audience Manager]中建立使用者，並指定使用者詳細資料、登入狀態以及將使用者指派給群組。

1. 按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Users]**。
1. 按一下![](assets/icon_add.png)以顯示[!UICONTROL Create New User]頁面。
1. 在&#x200B;**[!UICONTROL User Details]**&#x200B;底下，填寫欄位：
   * **[!UICONTROL Username]：**&#x200B;請為Audience Manager指定唯一的使用者名稱。
   * **[!UICONTROL First Name]：**&#x200B;指定使用者的名字。
   * **[!UICONTROL Last Name]：**&#x200B;指定使用者的姓氏。
   * **[!UICONTROL Email Address]：**&#x200B;指定使用者的電子郵件地址。 [!DNL Audience Manager]未定期傳送通知給使用者。 [!DNL Audience Manager]管理員可存取使用者的電子郵件地址，並可視需要手動傳送電子郵件給使用者。 例如，如果使用者忘記密碼，會使用此欄位中指定的電子郵件地址來傳送臨時密碼和重設密碼的說明。
   * **[!UICONTROL Phone Number]：**&#x200B;指定使用者的電話號碼。
   * **[!UICONTROL Is Admin]：**&#x200B;指定此使用者是否為[!DNL Audience Manager]管理員。 管理員使用者可以管理使用者（建立、編輯等）和群組（建立、指派許可權等）。 非管理員使用者只能控制自己的使用者設定檔，包括編輯電子郵件地址和重設密碼。 如需詳細資訊，請參閱[編輯您的帳戶設定](../../features/administration/edit-account-settings.md)。
1. 在&#x200B;**[!UICONTROL Login]**&#x200B;下，選取所需的狀態：
   * **[!UICONTROL Active]：**&#x200B;作用中使用者可以存取[!DNL Audience Manager]並擁有群組成員資格所授予的許可權。
   * **[!UICONTROL Deactivated]：**&#x200B;已停用的使用者無法存取[!DNL Audience Manager]，且沒有任何許可權。 如果您停用使用者，其使用者資訊會保留在[!DNL Audience Manager]中，您可以視需要輕鬆地重新啟用他們。 如果您移除使用者，則必須在他們日後需要再次使用[!DNL Audience Manager]時重新建立這些使用者。
   * **[!UICONTROL Expired]：**&#x200B;使用者的密碼超過90天。
   * **[!UICONTROL Pending]：**&#x200B;使用者有暫時密碼，可能是密碼重設後或新帳戶，而且他們尚未設定永久密碼。
   * **[!UICONTROL Locked Out]：** 5次不正確的登入嘗試將會鎖定使用者。
1. 在&#x200B;**[!UICONTROL Assigned Groups]**下方的下拉式清單中，選取要指派此使用者的所需群組。
如需群組與許可權的詳細資訊，請參閱[建立群組](../../features/administration/administration-overview.md#create-group)。
1. 按一下 **[!UICONTROL Save]**。

## 建立[!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> 使用者帳戶管理正在移至[Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。 若要開始使用者移轉，我們建議所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager使用者移轉至Admin Console](admin-console-migration.md)。
> 
> 所有客戶都完成移轉後，此區段將會消失。

*群組*&#x200B;是共用[!UICONTROL destination]、[!UICONTROL segment]和[!UICONTROL trait]物件存取許可權的使用者集合。 您可以將群組限製為僅限單一物件，或賦予群組對不同物件組合的廣泛存取權。

<!-- t_create_groups.xml -->

若要建立群組：

1. 按一下&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Groups]**。
2. 按一下![](assets/icon_add.png)以開啟[!UICONTROL Group Settings]頁面。
3. 在[!UICONTROL Group Details]：
   * 為群組命名。
   * 提供簡短的群組說明。
4. 在[!UICONTROL Group Members]中，按一下&#x200B;**[!UICONTROL Add Users]**&#x200B;選項中的使用者，以將他們新增至群組。
5. 在[!UICONTROL Group Permissions]中，從[選取](../../features/traits/trait-details-page.md)特徵[、](../../features/segments/segments-purpose.md)區段[或](../../features/destinations/destinations.md)目的地&#x200B;**[!UICONTROL Add Object]**。
這會開啟您所選物件的許可權視窗。
6. 選取您希望群組成員擁有的許可權核取方塊。
7. *（選擇性）*&#x200B;指派[萬用字元許可權](../../features/administration/administration-overview.md#wild-card-permissions)給群組。
8. 按一下 **[!UICONTROL Save Group]**。

## 瞭解[!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> 使用者帳戶管理正在移至[Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。 若要開始使用者移轉，我們建議所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager使用者移轉至Admin Console](admin-console-migration.md)。
> 
> 所有客戶都完成移轉後，此區段將會消失。

使用[!UICONTROL Wild Card Permissions]簡化群組許可權管理。

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions]讓群組成員自動存取與[!UICONTROL segment]、[!UICONTROL destination]或[!UICONTROL trait]關聯的每個資料來源。 相較之下，一般許可權只允許您將特定[!UICONTROL data sources]指派給這些物件之一。 此外，當您新增新的[!UICONTROL data sources]時，群組成員無法存取這些新來源。

您必須開啟群組許可權，並將這些新[!UICONTROL data sources]指派給群組。 [!UICONTROL Wild Card Permissions]可讓您避免此手動[!UICONTROL data source]更新程式。 具有[!UICONTROL Wild Card Permissions]的群組未經明確授權即可存取新的[!UICONTROL data sources]。

![](assets/wild-card.png)

請閱讀下文，瞭解每個[!UICONTROL wildcard permission]的意義：

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` — 使用者可以選取[!UICONTROL traits]作為[!UICONTROL models]的基線。
* `EDIT_ALL_TRAITS` — 使用者可以編輯在其公司帳戶內設定的所有[!UICONTROL traits]。
* `VIEW_ALL_TRAITS` — 使用者可以檢視在其公司帳戶內設定的所有[!UICONTROL traits]。
* `DELETE_ALL_TRAITS` — 使用者可以刪除在其公司帳戶內設定的所有[!UICONTROL traits]。
* `CREATE_ALL_ALGO_TRAITS` — 使用者可以建立[!UICONTROL algorithmic traits]。
* `MAP_ALL_TO_SEGMENTS` — 使用者可以將屬於其公司的任何[!UICONTROL traits]新增到[!UICONTROL segments]。
* `CREATE_ALL_TRAITS` — 使用者可以建立[!UICONTROL traits]。

**[!UICONTROL Models]**

* `VIEW_MODELS` — 使用者擁有檢視屬於其公司的[!UICONTROL models]的許可權。

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` — 使用者可以檢視屬於其公司的所有[!UICONTROL derived signals]。
* `CREATE_DERIVED_SIGNALS` — 使用者可以建立[!UICONTROL derived signals]。
* `EDIT_DERIVED_SIGNALS` — 使用者可以編輯屬於其公司的所有[!UICONTROL derived signals]。
* `DELETE_DERIVED_SIGNALS` — 使用者可以刪除屬於其公司的任何[!UICONTROL derived signals]。

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` — 使用者可以編輯在其公司帳戶內設定的所有[!UICONTROL destinations]。
* `CREATE_DESTINATIONS` — 使用者可以建立[!UICONTROL destinations]。
* `VIEW_ALL_DESTINATIONS` — 使用者可以檢視在其公司帳戶內設定的所有[!UICONTROL destinations]。
* `DELETE_ALL_DESTINATIONS` — 使用者可以刪除在其公司帳戶內設定的所有[!UICONTROL destinations]。

**[!UICONTROL Tags]**

* `VIEW_TAGS` — 使用者可以在其[!UICONTROL Tag Containers]上執行所有動作（檢視、建立、編輯、刪除）。

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` — 使用者可以在其[!UICONTROL Audience Lab]測試群組上執行所有動作（檢視、建立、編輯、刪除）。

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` — 使用者可以建立區段。
* `DELETE_ALL_SEGMENTS` — 使用者可以刪除在其公司帳戶內設定的所有區段。
* `MAP_ALL_TO_DESTINATIONS` — 使用者可以將屬於其公司的任何區段對應到目的地。
* `EDIT_ALL_SEGMENTS` — 使用者可以編輯在其公司帳戶內設定的所有區段。
* `MAP_ALL_SEGMENTS_TO_MODELS` — 使用者可以選取區段作為模型的基準。
* `VIEW_ALL_SEGMENTS` — 使用者可以檢視在其公司帳戶內設定的所有區段。

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` — 使用者可以檢視[Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md)中擷取的所有訊號。

## 使用個案 {#use-cases}

### 監控使用者存取 {#monitoring-user-access}

[!UICONTROL Role-Based Access Control]可協助您監視使用者登入狀態，讓您清楚瞭解誰可以存取您的Audience Manager執行個體。

視您的業務需求而定，您可以視需要啟用和停用使用者帳戶。

![監視 — 使用者 — 存取](assets/monitor-user-access.png)

### 確定敏感[!UICONTROL Data Sources]的存取保護 {#protect-sensitive-data-sources}

您可以為每個使用者群組在[!UICONTROL Role-Based Access Control]、區段和[!UICONTROL trait]層級設定[!UICONTROL destination]。

此功能可協助您管理使用者如何檢視、建立、讀取、寫入及編輯特定資料集，甚至限制使用者存取不應向他們提供的資料集。

![存取保護](assets/access-protection.png)
