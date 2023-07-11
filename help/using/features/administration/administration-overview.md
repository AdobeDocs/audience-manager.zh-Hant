---
description: 「管理」選單下的選項可讓您建立Audience Manager使用者並將其指派給群組。 您也可以檢視限制（特徵、區段、目的地和模型）。
keywords: rbac；RBAC；角色型；角色型；角色型存取控制
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: 管理
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 2%

---

# [!UICONTROL Administration] （RBAC控制項） {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> 使用者帳戶管理即將移至 [Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html). 若要開始使用者移轉，我們要求所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager使用者移轉至Admin Console](admin-console-migration.md).
> 
> 所有客戶都完成移轉後，本檔案的使用者管理區段將會消失。

>[!IMPORTANT]
>
> 在您使用之前 [!DNL RBAC]，此功能必須由Adobe為您的組織啟用。 請聯絡您的帳戶團隊以要求 [!DNL RBAC] 啟用，或聯絡客戶服務。


下的選項 [!UICONTROL Administration] 功能表可讓您建立Audience Manager使用者並將其指派給群組。 您也可以檢視限制（特徵、區段、目的地和模型）。

使用的企業客戶 [!DNL Audience Manager] 其所有資料都需要一個資料管理平台，但必須能夠控制特定業務單位中不同資料元素的可見度。 您可以使用群組許可權(也稱為 [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC])。

[!DNL Audience Manager] 使用群組來指派許可權。 未在使用者層級指派許可權。 群組許可權繫結至物件([!UICONTROL traits]、區段等) 以及您可以對這些物件執行的動作（編輯、檢視等）。 這些控制項也可透過Audience ManagerREST API取得。 另請參閱 [User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)， [群組管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)、和 [許可權管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) api方法。

## 建立使用者 {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> 使用者帳戶管理即將移至 [Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html). 若要開始使用者移轉，我們要求所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager使用者移轉至Admin Console](admin-console-migration.md).
> 
> 所有客戶都完成移轉後，本檔案的使用者管理區段將會消失。
> 
在中建立使用者 [!DNL Audience Manager] 和指定使用者詳細資訊、登入狀態，以及將使用者指派給群組。

1. 按一下 **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. 按一下 ![](assets/icon_add.png) 以顯示 [!UICONTROL Create New User] 頁面。
1. 下 **[!UICONTROL User Details]**，填寫欄位：
   * **[!UICONTROL Username]：** 指定Audience Manager的唯一使用者名稱。
   * **[!UICONTROL First Name]：** 指定使用者的名字。
   * **[!UICONTROL Last Name]：** 指定使用者的姓氏。
   * **[!UICONTROL Email Address]：** 指定使用者的電子郵件地址。 [!DNL Audience Manager] 不會定期傳送通知給使用者。 [!DNL Audience Manager] 管理員可存取使用者的電子郵件地址，並可視需要手動傳送電子郵件給使用者。 例如，如果使用者忘記密碼，則在此欄位中指定的電子郵件地址用於傳送臨時密碼和重設密碼的說明。
   * **[!UICONTROL Phone Number]：** 指定使用者的電話號碼。
   * **[!UICONTROL Is Admin]：** 指定此使用者是否為 [!DNL Audience Manager] 管理員。 管理員使用者可以管理使用者（建立、編輯等） 和群組（建立、指派許可權等）。 非管理員使用者只能控制自己的使用者設定檔，包括編輯其電子郵件地址和重設其密碼。 如需詳細資訊，請參閱 [編輯您的帳戶設定](../../features/administration/edit-account-settings.md).
1. 下 **[!UICONTROL Login]**，選取所需的狀態：
   * **[!UICONTROL Active]：**  作用中使用者可以存取 [!DNL Audience Manager] 並擁有群組成員資格所授予的許可權。
   * **[!UICONTROL Deactivated]：**  已停用的使用者無法存取 [!DNL Audience Manager] 並且沒有任何許可權。 如果您停用使用者，其使用者資訊會保留在 [!DNL Audience Manager] 而且您可以視需要輕鬆地重新啟用它們。 如果您移除使用者，則必須在他們需要使用時重新建立他們 [!DNL Audience Manager] 未來再來一次。
   * **[!UICONTROL Expired]：** 使用者的密碼超過90天。
   * **[!UICONTROL Pending]：** 使用者有臨時密碼，例如在密碼重設後或作為全新帳戶，而且他們尚未設定永久密碼。
   * **[!UICONTROL Locked Out]：** 5次不正確的登入嘗試將會鎖定使用者。
1. 下 **[!UICONTROL Assigned Groups]**，從下拉式清單中，選取您要指派此使用者的群組。
如需群組與許可權的詳細資訊，請參閱 [建立群組](../../features/administration/administration-overview.md#create-group).
1. 按一下 **[!UICONTROL Save]**.

## 建立 [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> 使用者帳戶管理即將移至 [Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html). 若要開始使用者移轉，我們建議所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager使用者移轉至Admin Console](admin-console-migration.md).
> 
> 所有客戶都完成移轉後，此區段將會消失。

A *群組* 是對下列專案共用存取許可權的使用者集合 [!UICONTROL destination]， [!UICONTROL segment]、和 [!UICONTROL trait] 物件。 您可以將群組限製為僅限單一物件，或讓群組可廣泛存取不同物件的組合。

<!-- t_create_groups.xml -->

要建立群組:

1. 按一下 **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. 按一下  ![](assets/icon_add.png) 以開啟 [!UICONTROL Group Settings] 頁面。
3. 在 [!UICONTROL Group Details]:
   * 為群組命名。
   * 提供簡短的群組說明。
4. 在 [!UICONTROL Group Members]，按一下以下位置中的使用者： **[!UICONTROL Add Users]** 選項以將它們新增至群組。
5. 在 [!UICONTROL Group Permissions]，選取 [特徵](../../features/traits/trait-details-page.md)， [區段](../../features/segments/segments-purpose.md)，或 [目的地](../../features/destinations/destinations.md) 從 **[!UICONTROL Add Object]**.
這會為您選取的物件開啟許可權視窗。
6. 選取您希望群組成員擁有的許可權核取方塊。
7. *（可選）* 指派 [萬用字元許可權](../../features/administration/administration-overview.md#wild-card-permissions) 至群組。
8. 按一下 **[!UICONTROL Save Group]**.

## 瞭解 [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> 使用者帳戶管理即將移至 [Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html). 若要開始使用者移轉，我們建議所有Audience Manager客戶立即採取本文所述的必要措施： [Audience Manager使用者移轉至Admin Console](admin-console-migration.md).
> 
> 所有客戶都完成移轉後，此區段將會消失。

簡化群組許可權管理 [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 讓群組成員自動存取與相關的每個資料來源 [!UICONTROL segment]， [!UICONTROL destination]，或 [!UICONTROL trait]. 相較之下，一般許可權僅允許您指派特定 [!UICONTROL data sources] 至其中一個物件。 而且，當您新增時 [!UICONTROL data sources]，群組成員無法存取這些新來源。

您必須開啟群組許可權並指派這些新的許可權 [!UICONTROL data sources] 至群組。 [!UICONTROL Wild Card Permissions] 可讓您避免使用本手冊 [!UICONTROL data source] 更新程式。 群組 [!UICONTROL Wild Card Permissions] 取得新專案的存取權 [!UICONTROL data sources] 未經明確授權。

![](assets/wild-card.png)

請閱讀下文，瞭解各項功能的說明 [!UICONTROL wildcard permission] 表示：

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS`  — 使用者可以選擇 [!UICONTROL traits] 作為的基準線 [!UICONTROL models].
* `EDIT_ALL_TRAITS`  — 使用者可以編輯全部 [!UICONTROL traits] 在其公司帳戶中設定。
* `VIEW_ALL_TRAITS`  — 使用者可以檢視全部 [!UICONTROL traits] 在其公司帳戶中設定。
* `DELETE_ALL_TRAITS`  — 使用者可以刪除全部 [!UICONTROL traits] 在其公司帳戶中設定。
* `CREATE_ALL_ALGO_TRAITS`  — 使用者可以建立 [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS`  — 使用者可以新增任何 [!UICONTROL traits] 屬於其公司屬於 [!UICONTROL segments].
* `CREATE_ALL_TRAITS`  — 使用者可以建立 [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS`  — 使用者擁有檢視許可權 [!UICONTROL models] 屬於其公司。

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS`  — 使用者可檢視所有 [!UICONTROL derived signals] 屬於其公司。
* `CREATE_DERIVED_SIGNALS`  — 使用者可以建立 [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS`  — 使用者可編輯所有 [!UICONTROL derived signals] 屬於其公司。
* `DELETE_DERIVED_SIGNALS`  — 使用者可刪除任何 [!UICONTROL derived signals] 屬於其公司。

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS`  — 使用者可編輯所有 [!UICONTROL destinations] 在其公司帳戶中設定。
* `CREATE_DESTINATIONS`  — 使用者可以建立 [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS`  — 使用者可檢視所有 [!UICONTROL destinations] 在其公司帳戶中設定。
* `DELETE_ALL_DESTINATIONS`  — 使用者可以刪除所有 [!UICONTROL destinations] 在其公司帳戶中設定。

**[!UICONTROL Tags]**

* `VIEW_TAGS`  — 使用者可在其上執行任何動作（檢視、建立、編輯、刪除） [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS`  — 使用者可在其上執行任何動作（檢視、建立、編輯、刪除） [!UICONTROL Audience Lab] 測試群組。

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS`  — 使用者可建立區段。
* `DELETE_ALL_SEGMENTS`  — 使用者可以刪除在其公司帳戶內設定的所有區段。
* `MAP_ALL_TO_DESTINATIONS`  — 使用者可將屬於其公司的任何區段對應至目的地。
* `EDIT_ALL_SEGMENTS`  — 使用者可以編輯在其公司帳戶內設定的所有區段。
* `MAP_ALL_SEGMENTS_TO_MODELS`  — 使用者可以選擇區段作為模型的基線。
* `VIEW_ALL_SEGMENTS`  — 使用者可檢視在其公司帳戶內設定的所有區段。

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS`  — 使用者可檢視中擷取的所有訊號 [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## 使用個案 {#use-cases}

### 監控使用者存取 {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] 可協助您監控使用者登入狀態，讓您清楚瞭解誰可以存取您的Audience Manager執行個體。

視您的業務需求而定，您可以視需要啟用和停用使用者帳戶。

![monitor-user-access](assets/monitor-user-access.png)

### 確保敏感資料的存取保護 [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

您可以設定 [!UICONTROL Role-Based Access Control] 於 [!UICONTROL trait]、區段和 [!UICONTROL destination] 層級，適用於每個使用者群組。

此功能可協助您管理使用者如何檢視、建立、讀取、寫入和編輯特定資料集，甚至限制使用者存取不應向他們提供的資料集。

![存取保護](assets/access-protection.png)
