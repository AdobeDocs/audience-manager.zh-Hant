---
description: 此程式會逐步引導您完成在Audience Lab中建立、編輯或刪除測試群組所需的步驟
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: 管理測試群組
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---

# 管理測試群組 {#manage-test-groups}

此程式會逐步引導您完成在[!UICONTROL Audience Lab]中建立、編輯或刪除測試群組所需的步驟。

## 建立區段測試群組 {#create-test-groups}

### 必備條件

<!-- create-test-group.xml -->

* 您必須設定至少一個&#x200B;**轉換特徵**。 您可以選取&#x200B;**轉換**&#x200B;作為事件型別，在[特徵產生器](../../features/traits/create-onboarded-rule-based-traits.md)中設定轉換特徵。 如需有關轉換特徵及其設定方式的詳細資訊，我們為您準備了[影片](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html)。

  >[!IMPORTANT]
  >
  >[資料夾特徵](../../features/traits/about-folder-traits.md) **不受[!UICONTROL Audience Lab]支援**。 將資料夾特徵的[事件型別](../../features/traits/create-onboarded-rule-based-traits.md)設定為&#x200B;**轉換**，將不會在[!UICONTROL Audience Lab]中產生該特定資料夾特徵的任何資料。

* 針對使用[角色型存取控制](../../features/administration/administration-overview.md)的公司：將[!UICONTROL Audience Lab] [萬用字元許可權](../../features/administration/administration-overview.md#wild-card-permissions)指派給&#x200B;**[!UICONTROL User Groups]**&#x200B;以提供存取權。 此許可權可讓使用者建立和檢視測試的結果。 使用者將只能使用他們具有&#x200B;**讀取**&#x200B;和&#x200B;**對應到目的地**&#x200B;許可權的資料來源區段。 使用者將只能使用他們擁有&#x200B;**「讀取」**&#x200B;許可權的資料來源的轉換特徵。 使用者也只能檢視他們有權存取的目的地。 因此，在將[!DNL Audience Lab]萬用字元許可權新增到群組之前，請確定群組具有：
   * 存取權以讀取相關的轉換特徵；
   * 存取可讀取及對應測試的相關區段；
   * 相關目的地的存取權。

若要建立新的[!UICONTROL Segment Test Group]：

1. 在[!UICONTROL Audience Lab]儀表板中選取&#x200B;**[!UICONTROL Create New Test Group]**&#x200B;以啟動精靈。
1. **[!UICONTROL Basic Info & Choose Segment]**

   * 填寫&#x200B;**[!UICONTROL Test Group Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
   * 透過在檔案瀏覽器中導覽或輸入搜尋列來選擇&#x200B;**[!UICONTROL Base Segment]**，按下&#x200B;**[!UICONTROL Choose Segment.]**&#x200B;進行確認
   * 您可以將測試群組另存為草稿，稍後再繼續處理。
   * 如果您選取的基本區段已用於其他測試群組，則會顯示警報。 兩次使用基礎區段可能會扭曲兩個測試的轉換結果。

1. **[!UICONTROL Allocate Test Segments]**

   * 您可以建立最多&#x200B;**15個測試區段**，並依需要分配裝置百分比。
   * 您可以按一下測試區段來編輯其名稱。
   * 配置新測試區段時，百分比會自動平均分配為100%。 然後您可以手動編輯百分比。 在編輯百分比後按一下核取方塊，並確認百分比已增加至100%，否則您將無法繼續下一個步驟。

1. **[!UICONTROL Set a Control Segment]**

   * 如果您要預留區段的特定部分作為控制組，請選取控制區段。 控制組可讓您檢視比較基準時您建立的測試區段所產生的影響。
   * 您可以在下拉式清單中選取測試區段作為控制區段，也可以選擇&#x200B;**[!UICONTROL None]**&#x200B;作為無控制項。
   * 完成時，按一下「**[!UICONTROL Next]**」。

1. **[!UICONTROL Select Conversion Traits]**

   * 在轉換特徵視窗中輸入，即可新增轉換特徵。 這是&#x200B;**強制性**&#x200B;步驟，除非您新增至少一個轉換特徵，否則您無法繼續下一個步驟。
   * 您最多可以新增5個轉換特徵（如果需要）。
   * 如果您選取的轉換特徵已用於其他測試群組，則會顯示警報。
   * 請注意，Audience Manager不支援使用[資料夾特徵](/help/using/features/traits/about-folder-traits.md)作為轉換特徵。 將資料夾特徵選取為轉換特徵會導致0彙總和趨勢報表顯示在測試中。

1. **[!UICONTROL Choose Destinations & Dates]**

   * 在搜尋欄位中輸入所需的目的地，或使用下拉式箭頭。 可以將[!UICONTROL Audience Lab]測試區段傳送至URL、Cookie或伺服器對伺服器目的地。
   * 將區段拖放至目的地。
   * 將區段拖曳到目的地後，請填入盲圖中的&#x200B;**[!UICONTROL Destination Mapping Value]**。
   * 您可以將相同的測試區段傳送至多個目的地，也可以將多個測試區段新增至單一目的地。
   * 如果目的地無法用於根據[資料匯出控制](../../features/data-export-controls.md)的特定測試區段，則目的地會呈現灰色。
   * 使用者只會根據他們所屬的[RBAC使用者群組](../../features/administration/administration-overview.md)，看到他們有權存取的目的地。
   * 最後，您必須為測試群組選取開始日期。 此日期會標籤測試群組發佈至目的地期間的開始。 選取&#x200B;**無結束日期**&#x200B;以無限期比較測試區段。

   >[!NOTE]
   >
   >具有已驗證設定檔的[!UICONTROL Profile Merge Rules]僅在即時目的地中受支援。 如果具有該設定的設定檔合併規則的測試區段傳送至檔案式伺服器對伺服器目的地，則對象可能不會填入。

   按一下&#x200B;**[!UICONTROL Next]**&#x200B;以檢閱並完成您的測試群組。

1. **[!UICONTROL Summary & Finalize]**

   * 檢閱您在先前步驟中新增的資訊，並選取&#x200B;**[!UICONTROL Finalize Group]**。
   * 請記住，完成測試群組後，可以複製或刪除該群組，但不能進行編輯。

   >[!NOTE]
   >* 您可以在建立過程中隨時儲存測試群組，並稍後返回精靈。 測試群組狀態將為&#x200B;**[!UICONTROL Draft]**，而且在您完成區段測試群組之前，測試群組不會傳送任何資料至目的地。
   >* 對於草稿測試，您可以在主要[!UICONTROL Audience Lab]檢視中按一下測試群組卡片中的&#x200B;**[!UICONTROL Edit]**，返回並編輯測試群組。

## 編輯區段測試群組 {#edit-test-groups}

在[!UICONTROL Audience Lab]中，您只能編輯草稿測試群組。 在[!UICONTROL Create Segment Test Group]精靈中，您可以將測試群組儲存為草稿，稍後再繼續處理。

1. 導覽至[!UICONTROL Audience Lab]主檢視。
1. 搜尋您的草稿測試群組，並選取測試群組卡片中的&#x200B;**[!UICONTROL Edit]**&#x200B;控制項。
1. 繼續[建立區段測試群組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)精靈，並在完成時選取&#x200B;**[!UICONTROL Finalize Group]**。

## 刪除區段測試群組 {#delete-test-groups}

1. 導覽至[!UICONTROL Audience Lab]主檢視。
1. 尋找您要刪除的測試群組。 您可以：

   * 按測試群組卡片中的&#x200B;**[!UICONTROL Delete]**&#x200B;控制項，或
   * 按下測試群組卡片中的測試群組標題，以移至[測試群組資訊](../../features/audience-lab/audience-lab-information-view.md)檢視，然後按標題列中的&#x200B;**[!UICONTROL Delete]**&#x200B;控制項。

1. 對於[已完成的測試區段](../../features/audience-lab/audience-lab.md#status)，如果您願意，警示會提示您下載CSV檔案以儲存報告。
