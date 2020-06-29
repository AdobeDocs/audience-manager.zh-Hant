---
description: 「管理」功能表下的選項可讓您建立Audience Manager使用者並將其指派給群組。 您也可以檢視限制（特徵、區段、目的地和模型）。
keywords: rbac;RBAC;role based;role-based;role-based access controls
seo-description: 「管理」功能表下的選項可讓您建立Audience Manager使用者並將其指派給群組。 您也可以檢視限制（特徵、區段、目的地和模型）。
seo-title: 管理
solution: Audience Manager
title: 管理
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 1%

---


# [!UICONTROL Administration] （RBAC控制） {#administration}

![](assets/rbac-controls.png)

功能表下的選 [!UICONTROL Administration] 項可讓您建立Audience Manager使用者並將其指派給群組。 您也可以檢視限制（特徵、區段、目的地和模型）。

使用其所 [!DNL Audience Manager] 有資料的企業客戶需要一個資料管理平台，但必須能夠控制不同資料元素對特定業務單位的可見度。 您可以使用群組權限(也稱為( [!UICONTROL Role-Based Access Control][!UICONTROL RBAC]))來完成此作業。

[!DNL Audience Manager] 使用群組來指派權限。 在使用者層級不會指派權限。 群組權限會系結至物[!UICONTROL traits]件（、區段等） 以及可對這些物件執行的動作（編輯、檢視等）。 這些控制項也可透過Audience Manager REST API取得。 請參 [閱使用者](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)、 [群組管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)、權限 [管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API方法。

## Create Users {#create-users}

<!-- t_create_users.xml -->

在中建立使 [!DNL Audience Manager] 用者，並指定使用者詳細資訊、登入狀態，以及指派使用者至群組。

1. 按一下 **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. 按一 ![](assets/icon_add.png) 下以顯示 [!UICONTROL Create New User] 頁面。
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **[!UICONTROL Username]:**指定Audience Manager的唯一使用者名稱。
   * **[!UICONTROL First Name]:**指定使用者的名字。
   * **[!UICONTROL Last Name]:**指定使用者的姓氏。
   * **[!UICONTROL Email Address]:**指定使用者的電子郵件地址。[!DNL Audience Manager]不會定期傳送通知給使用者。[!DNL Audience Manager]管理員可存取使用者的電子郵件地址，並可視需要手動以電子郵件寄送使用者。 例如，如果使用者忘記密碼，則此欄位中指定的電子郵件地址會用來傳送暫時密碼和重設密碼的指示。
   * **[!UICONTROL Phone Number]:**指定使用者的電話號碼。
   * **[!UICONTROL Is Admin]:**指定此使用者是否為管[!DNL Audience Manager]理員。 管理員使用者可以管理使用者（建立、編輯等） 和群組（建立、指派權限等）。 非管理員使用者只能控制自己的使用者設定檔，包括編輯其電子郵件地址及重設自己的密碼。 如需詳細資訊，請參[閱編輯帳戶設定](../../features/administration/edit-account-settings.md)。
1. 在下 **[!UICONTROL Login]**&#x200B;方，選取所要的狀態：
   * **[!UICONTROL Active]:**作用中使用者可[!DNL Audience Manager]以存取並擁有群組成員資格的權限。
   * **[!UICONTROL Deactivated]:**已停用的使用者無[!DNL Audience Manager]法存取，也沒有任何權限。 如果您停用使用者，其使用者資訊會保留在中，[!DNL Audience Manager]而且您可以視需要輕鬆重新啟用使用者。 如果您移除使用者，則必須重新建立使用者(如果他們日後需要[!DNL Audience Manager]再次使用)。
   * **[!UICONTROL Expired]:**使用者的密碼早於90天。
   * **[!UICONTROL Pending]:**使用者具有暫時密碼，例如重設密碼後或全新帳戶，而且他們尚未設定永久密碼。
   * **[!UICONTROL Locked Out]:**5次不正確的登入嘗試會鎖定使用者。
1. 在 **[!UICONTROL Assigned Groups]**下方，從下拉式清單中，選取您要指派此使用者的所需群組。
如需群組和權限的詳細資訊，請參 [閱建立群組](../../features/administration/administration-overview.md#create-group)。
1. 按一下 **[!UICONTROL Save]**.

## 建立 [!UICONTROL Group] {#create-group}

群 *組* ，是共用對、對象和物件存取權的使 [!UICONTROL destination]用者 [!UICONTROL segment]集合 [!UICONTROL trait] 。 您可以僅將群組限制為單一物件，或讓群組廣泛存取不同物件的組合。

<!-- t_create_groups.xml -->

要建立群組:

1. 按一下 **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
1. 按一 ![](assets/icon_add.png) 下以開啟 [!UICONTROL Group Settings] 頁面。
1. 在 [!UICONTROL Group Details]:
   * 命名群組。
   * 提供簡短的群組說明。
1. 在中 [!UICONTROL Group Members]，從選項中按一下用戶， **[!UICONTROL Add Users]** 將其添加到組中。
1. 在中 [!UICONTROL Group Permissions]，選擇特 [徵](../../features/traits/trait-details-page.md)、 [特徵](../../features/segments/segments-purpose.md)區段 [、目的](../../features/destinations/destinations.md) 地 **[!UICONTROL Add Object]**。
這會開啟您所選物件的權限視窗。
1. 選中您希望群組成員擁有的權限的核取方塊。
1. *（選用）* 將萬用 [字元權限指派給群組](../../features/administration/administration-overview.md#wild-card-permissions) 。
1. 按一下 **[!UICONTROL Save Group]**.

## 瞭解 [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

使用簡化群組權限管理 [!UICONTROL Wild Card Permissions]。

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 為群組成員提供與、或關聯的每個資料來源的自 [!UICONTROL segment]動 [!UICONTROL destination]存取權 [!UICONTROL trait]。 相較之下，一般權限只能讓您指派 [!UICONTROL data sources] 特定至其中一個物件。 而且，當您新增新 [!UICONTROL data sources]的來源時，群組成員無法存取這些新來源。

您必須開啟群組權限，並將這些新權限指派 [!UICONTROL data sources] 給群組。 [!UICONTROL Wild Card Permissions] 讓您避免手動更新 [!UICONTROL data source] 程式。 具有新 [!UICONTROL Wild Card Permissions] 權限的群組可在未明確授 [!UICONTROL data sources] 權的情況下存取。

![](assets/wild-card.png)

請閱讀以下內容，以瞭解各自的 [!UICONTROL wildcard permission] 含義：

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` -用戶可以選 [!UICONTROL traits] 擇作為基準 [!UICONTROL models]。
* `EDIT_ALL_TRAITS` -使用者可編輯其公 [!UICONTROL traits] 司帳戶內所有設定。
* `VIEW_ALL_TRAITS` -使用者可檢視其公 [!UICONTROL traits] 司帳戶內的所有設定。
* `DELETE_ALL_TRAITS` -使用者可刪除其公 [!UICONTROL traits] 司帳戶內所有設定。
* `CREATE_ALL_ALGO_TRAITS` -使用者可以建立 [!UICONTROL algorithmic traits]。
* `MAP_ALL_TO_SEGMENTS` -使用者可將屬於其公司 [!UICONTROL traits] 的任何項目新增至 [!UICONTROL segments]。
* `CREATE_ALL_TRAITS` -使用者可以建立 [!UICONTROL traits]。

**[!UICONTROL Reports]**

* `PTRREPORTS` -這指 [!UICONTROL wildcard permission] 過時的功能，不久將從Audience Manager使用者介面移除。

**[!UICONTROL Models]**

* `VIEW_MODELS` -使用者有權檢視屬於 [!UICONTROL models] 其公司的內容。

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` -使用者可檢視屬於其公 [!UICONTROL derived signals] 司的所有內容。
* `CREATE_DERIVED_SIGNALS` -使用者可以建立 [!UICONTROL derived signals]。
* `EDIT_DERIVED_SIGNALS` -使用者可編輯其公 [!UICONTROL derived signals] 司的所有資產。
* `DELETE_DERIVED_SIGNALS` -用戶可以刪除屬於其公 [!UICONTROL derived signals] 司的任何一個。

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` -使用者可編輯其公 [!UICONTROL destinations] 司帳戶內的所有設定。
* `CREATE_DESTINATIONS` -使用者可以建立 [!UICONTROL destinations]。
* `VIEW_ALL_DESTINATIONS` -使用者可檢視其公 [!UICONTROL destinations] 司帳戶內的所有設定。
* `DELETE_ALL_DESTINATIONS` -使用者可刪除其公司 [!UICONTROL destinations] 帳戶內所有設定。

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

* `VIEW_ALL_SIGNALS` -使用者可檢視資料總管中擷取的所 [有訊號](/help/using/features/data-explorer/data-explorer-overview.md)。

## 使用個案 {#use-cases}

### 監視用戶訪問 {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] 可協助您監控使用者登入狀態，讓您清楚瞭解哪些人可以存取您的Audience Manager實例。

視您的業務需求而定，您可以視需要啟用和停用使用者帳戶。

![monitor-user-access](assets/monitor-user-access.png)

### 確保對敏感資料的訪問保護 [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

您可以針 [!UICONTROL Role-Based Access Control] 對每 [!UICONTROL trait]個使用者群組設定 [!UICONTROL destination] 位置、區段和層級。

此功能可協助您管理使用者檢視、建立、讀取、寫入和編輯特定資料集的方式，甚至限制使用者存取他們無法存取的資料集。

![接入保護](assets/access-protection.png)
