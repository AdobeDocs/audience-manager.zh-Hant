---
description: 此程序會逐步引導您完成Audience Lab中建立、編輯或刪除測試群組所需的步驟
seo-description: 此程序會逐步引導您完成Audience Lab中建立、編輯或刪除測試群組所需的步驟
seo-title: 管理測試群組
solution: Audience Manager
title: 管理測試群組
uuid: fadddeb-7574-4853-8c52-c58456582 c62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Test Groups {#manage-test-groups}

This procedure walks you through the steps needed to create, edit, or delete a test group in [!UICONTROL Audience Lab].

## Create Segment Test Groups {#create-test-groups}

### 必備條件

<!-- create-test-group.xml -->

* You need to have at least one **conversion trait** set up. You can set up conversion traits in the [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md), by selecting **conversion** as the event type. For more information on what conversion traits are and how to set them up, we prepared a [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) for you.

   >[!IMPORTANT]
   >
   >[資料夾特性](../../features/traits/about-folder-traits.md)**不受**[!UICONTROL Audience Lab]支援。Setting the [Event Type](../../features/traits/create-onboarded-rule-based-traits.md) of a folder trait to **conversion** will not generate any data in [!UICONTROL Audience Lab] for that specific folder trait.

* For companies using [Role-Based Access Control](../../features/administration/administration-overview.md): Assign the [!UICONTROL Audience Lab] [wildcard permission](../../features/administration/administration-overview.md#wild-card-permissions) to **[!UICONTROL User Groups]** to provide access. 此權限允許使用者建立並檢視測試結果。A user will only be able to use segments from a data source they have **read** and **map to destination** privileges for. The user will only be able to use conversion traits from a data source for which they have **"read"** permissions. 使用者只能看見他們也有權存取的目的地。So, before adding the [!DNL Audience Lab] wildcard permission to a group, make sure the group has:
   * 存取相關轉換特性；
   * 存取並映射測試相關區段；
   * 存取相關目的地。

To create a new [!UICONTROL Segment Test Group]:

1. Select **[!UICONTROL Create New Test Group]** in the [!UICONTROL Audience Lab] dashboard to start the wizard.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Fill in a **[!UICONTROL Test Group Name]** and a **[!UICONTROL Description]**.
   * Choose the **[!UICONTROL Base Segment]** either by navigating in the file browser or by typing in the search bar, confirm by pressing **[!UICONTROL Choose Segment.]**
   * 您可以將測試群組儲存為草稿，並稍後繼續處理。
   * 系統會顯示警報，以防您選取的基底區段已用於其他測試群組。使用基底區段兩次可能會扭曲兩個測試的轉換結果。

1. **[!UICONTROL Allocate Test Segments]**

   * You can create **up to 15 test segments** and divide the percentage of devices as you wish.
   * 您可以按一下測試區段的名稱來編輯。
   * 配置新測試區段時，百分比會自動分配給100%。然後您可以手動編輯百分比。編輯百分比後按一下核取方塊，確定其新增高達100%，否則無法繼續下一個步驟。

1. **[!UICONTROL Set a Control Segment]**

   * 如果您要設定區段的某部分作為控制群組，請選取控制區段。控制群組可讓您查看與基準比較建立的測試區段影響。
   * You can select a test segment as control segment in the drop-down list, or you can choose **[!UICONTROL None]** for no control.
   * Click **[!UICONTROL Next]** when you're done.

1. **[!UICONTROL Select Conversion Traits]**

   * 在轉換特徵視窗中輸入，以新增轉換特性。This is a **mandatory** step and you cannot proceed to the next step unless you add at least one conversion trait.
   * 您可以視需要新增最多個轉換特性。
   * 警報會顯示，以防您選取已用於其他測試群組的轉換特徵。

1. **[!UICONTROL Choose Destinations & Dates]**

   * 在搜尋欄位中鍵入所需目的地，或使用下拉式箭頭。[!UICONTROL Audience Lab] 測試區段可傳送至URL、Cookie或伺服器至伺服器目的地。
   * 將區段拖放至目的地。
   * After dropping a segment in a destination, fill in the **[!UICONTROL Destination Mapping Value]** in the blind.
   * 您可以將相同的測試區段傳送至多個目的地，也可以將多個測試區段新增至單一目的地。
   * Destinations are grayed out if they are not available for a certain test segment based on [Data Export Controls](../../features/data-export-controls.md).
   * Users will only see the destinations they have access to based on the [RBAC User Group](../../features/administration/administration-overview.md) they belong to.
   * 最後，您必須選取測試群組的開始日期。此日期標示您的測試群組將發佈至目的地的開始時間。Select **No End Date** for an indefinite comparison of the test segments.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] 僅支援已驗證的描述檔。如果將該組態的描述檔合併規則具有該組態的測試區段傳送至檔案型伺服器至伺服器目的地，則不會填入對象。

   Click **[!UICONTROL Next]** to review and finalize your test group.

1. **[!UICONTROL Summary & Finalize]**

   * Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.
   * 請記住，當您完成測試群組後，可以重復或刪除測試群組，但無法編輯。
   >[!NOTE]
   >* 您可以在建立程序的任何一點儲存測試群組，然後稍後返回精靈。The test group status will be **[!UICONTROL Draft]** and the test group will not send any data to destinations until you finalize the segment test group.
   >* For draft tests, you can go back and edit the test groups by clicking **[!UICONTROL Edit]** in the test group card in the main [!UICONTROL Audience Lab] view.


## Edit Segment Test Groups {#edit-test-groups}

In [!UICONTROL Audience Lab], you are only able to edit draft test groups. [!UICONTROL Create Segment Test Group] 在精靈中，您可以將測試群組儲存為草稿，並稍後繼續處理。

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Search for your draft test groups and select the **[!UICONTROL Edit]** control in the test group card.
1. Resume the [Create Segment Test Group](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) wizard and select **[!UICONTROL Finalize Group]** when you're done.

## Delete Segment Test Groups {#delete-test-groups}

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. 尋找您要刪除的測試群組。您可以:

   * press the **[!UICONTROL Delete]** control in the test group card, or
   * press the test group title in the test group card to go to the [Test Group Information](../../features/audience-lab/audience-lab-information-view.md) view and press the **[!UICONTROL Delete]** control in the title bar.

1. For [completed test segments](../../features/audience-lab/audience-lab.md#status), an alert will prompt you to download the CSV file to save the reporting if you wish.
