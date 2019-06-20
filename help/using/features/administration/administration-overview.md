---
description: 「管理」功能表下的選項可讓您建立Audience Manager使用者並指派給群組。您也可以檢視限制(特徵、區段、目的地和模型)。
keywords: rbac；RBAC；以角色為基礎；以角色為基礎；角色存取控制
seo-description: 「管理」功能表下的選項可讓您建立Audience Manager使用者並指派給群組。您也可以檢視限制(特徵、區段、目的地和模型)。
seo-title: 管理
solution: Audience Manager
title: 管理
topic: DIL API
uuid: 498e0316-cf-1b-43e9-88ba-338ee0 daf225
translation-type: tm+mt
source-git-commit: 9801bf6a1a4c2c2e7cc2aa8ab32cb81094368554

---


# Administration (RBAC Controls) {#administration}

![](assets/rbac-controls.png)

[!UICONTROL Administration] 功能表下的選項可讓您建立Audience Manager使用者並指派給群組。您也可以檢視限制(特徵、區段、目的地和模型)。

Enterprise customers using [!DNL Audience Manager] need one data management platform for all of their data, but must be able to control the visibility of the different data elements to specific business units. You can accomplish this using group permissions, also referred to as [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] 使用群組指派權限。權限不會指派給使用者層級。群組權限系結至物件(特徵、區段等)以及您可在這些物件上執行的動作(編輯、檢視等)。這些控制項也可透過Audience Manager REST API取得。See [User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Group Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md), and [Permissions Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API methods.

## Create Users {#create-users}

<!-- t_create_users.xml -->

Create users in [!DNL Audience Manager] and specify user details, login status, and assign users to groups.

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Users]**.
1. Click ![](assets/icon_add.png) to display the [!UICONTROL Create New User] page.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **使用者名稱：** 指定Audience Manager的唯一使用者名稱。
   * **名字：** 指定使用者的名字。
   * **姓氏：** 指定使用者的姓氏。
   * **電子郵件地址：** 指定使用者的電子郵件地址。[!DNL Audience Manager] 不會傳送定期通知給使用者。[!DNL Audience Manager] 管理員可存取使用者的電子郵件地址，並可視需要手動傳送使用者。例如，如果使用者忘記密碼，則會使用此欄位中指定的電子郵件地址來傳送暫時密碼和重設密碼的指示。
   * **電話號碼：** 指定使用者的電話號碼。
   * **是管理員：** 指定此使用者是否為 [!DNL Audience Manager] 管理員。管理員使用者可以管理使用者(建立、編輯等)和群組(建立、指派權限等)。非管理員使用者只能控制自己的使用者設定檔，包括編輯其電子郵件地址和重設密碼。For more information, see [Edit Your Account Settings](../../features/administration/edit-account-settings.md).
1. Under **[!UICONTROL Login]**, select the desired status:
   * **活動：** 主動使用者可以存取 [!DNL Audience Manager] 並擁有群組成員資格授予的權限。
   * **停用：** 停用的使用者無法存取 [!DNL Audience Manager] 且沒有任何權限。If you deactivate users, their user information remains in [!DNL Audience Manager] and you can simple reactivate them, if necessary. If you remove users, you must re-create them if they need to use [!DNL Audience Manager] again in the future.
   * **過期：** 使用者密碼大於90天。
   * **擱置中：** 使用者擁有暫時密碼，不論是重設密碼後或新帳戶後，都尚未設定永久密碼。
   * **已鎖定：** 不正確的登入嘗試會鎖定使用者。
1. Under **[!UICONTROL Assigned Groups]**, from the drop-down list, select the desired groups to which you want to assign this user.
For more information about groups and permissions, see [Create a Group](../../features/administration/administration-overview.md#create-group).
1. Click **[!UICONTROL Save]**.

## 建立群組 {#create-group}

*群組* 是一組使用者，可分享目的地、區段和特徵物件的存取權限。您只能將群組限制為單一物件，或讓它們廣泛存取不同物件的組合。

<!-- t_create_groups.xml -->

要建立群組:

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Groups]**.
1. Click  ![](assets/icon_add.png) to open the [!UICONTROL Group Settings] page.
1. 在 [!UICONTROL Group Details]:
   * 命名群組。
   * 提供簡短的群組說明。
1. In [!UICONTROL Group Members], click a user from **[!UICONTROL Add Users]** options to add them to the group.
1. In [!UICONTROL Group Permissions], select a [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md), or [destination](../../features/destinations/destinations.md) from **[!UICONTROL Add Object]**.
這樣會開啓您所選取物件的權限視窗。
1. 選取您要群組成員擁有的權限核取方塊。
1. *(選擇性)* 將 [「萬用字元權限](../../features/administration/administration-overview.md#wild-card-permissions) 」指派給群組。
1. Click **[!UICONTROL Save Group]**.

## Understanding Wild Card Permissions {#wild-card-permissions}

Simplify group rights management with [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 讓群組成員自動存取每個與區段、目的地或特徵關聯的資料來源。根據比較，一般權限只能讓您指派特定資料來源至其中一個物件。此外，當您新增資料來源時，群組成員無法存取這些新來源。

您必須開啓群組權限，並將這些新資料來源指派給群組。[!UICONTROL Wild Card Permissions] 可讓您避免此手動資料來源更新程序。Groups with [!UICONTROL Wild Card Permissions] get access to new data sources without explicit authorization.

![](assets/wild-card.png)

請參閱以下以瞭解每個萬用字元權限的意義：

**特性**

* `MAP_ALL_TRAITS_TO_MODELS` - 需要釐清嗎？
* `EDIT_ALL_TRAITS` - 使用者可以編輯屬於其公司的所有特性(PID)
* `VIEW_ALL_TRAITS` - 使用者可以檢視屬於其公司的所有特性(PID)
* `DELETE_ALL_TRAITS` - 使用者可以刪除屬於其公司(PID)的所有特性。
* `CREATE_ALL_ALGO_TRAITS` - 需要釐清
* `MAP_ALL_TO_SEGMENTS` - 使用者可以將屬於其公司的任何特性新增至區段。
* `CREATE_ALL_TRAITS` - 使用者可以建立特性。

**報表**

* `PTRREPORTS` - 這個萬用字元權限會參照過時的功能，很快就會從Audience Manager UI移除。

**模型**

* `VIEW_MODELS` - 使用者有權檢視屬於其公司的模型。

**衍生訊號**

* `VIEW_DERIVED_SIGNALS` - 使用者可以檢視屬於其公司的所有衍生訊號。
* `CREATE_DERIVED_SIGNALS` - 使用者可以建立衍生訊號。
* `EDIT_DERIVED_SIGNALS` - 使用者可以編輯屬於其公司的所有衍生訊號。
* `DELETE_DERIVED_SIGNALS` - 使用者可以刪除屬於其公司的任何衍生訊號。

**目標**

* `EDIT_ALL_DESTINATIONS` - 使用者可以編輯公司帳戶內設定的所有目的地。
* `CREATE_DESTINATIONS` - 使用者可以建立目的地。
* `VIEW_ALL_DESTINATIONS` - 使用者可以檢視公司帳戶內設定的所有目的地。
* `DELETE_ALL_DESTINATIONS` - 使用者可以刪除公司帳戶中設定的所有目的地。

**標記**

* `VIEW_TAGS` - 使用者可以在其標記容器上執行所有動作(檢視、建立、編輯、刪除)。

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` - 使用者可以在其Audience Lab測試群組上執行所有(檢視、建立、編輯、刪除)動作。

**區段**

* `CREATE_ALL_SEGMENTS` - 使用者可以建立區段。
* `DELETE_ALL_SEGMENTS` - 使用者可以刪除公司帳戶內設定的所有區段。
* `MAP_ALL_TO_DESTINATIONS` - 使用者可以將屬於其公司的任何區段對應至目的地。
* `EDIT_ALL_SEGMENTS` - 使用者可以編輯公司帳戶內設定的所有區段。
* `MAP_ALL_SEGMENTS_TO_MODELS` - 需要釐清嗎？
* `VIEW_ALL_SEGMENTS` - 使用者可以檢視公司帳戶內設定的所有區段。

**訊號**

* `VIEW_ALL_SIGNALS` - 使用者可以檢視 [資料總管中擷取的所有訊號](/help/using/features/data-explorer/data-explorer-overview.md)。