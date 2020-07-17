---
description: 此程式會逐步帶您完成在Audience Lab中建立、編輯或刪除測試群組所需的步驟
seo-description: 此程式會逐步帶您完成在Audience Lab中建立、編輯或刪除測試群組所需的步驟
seo-title: 管理測試群組
solution: Audience Manager
title: 管理測試群組
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 1%

---


# 管理測試群組 {#manage-test-groups}

此程式會逐步帶您完成在中建立、編輯或刪除測試群組所需的步驟 [!UICONTROL Audience Lab]。

## 建立區段測試群組 {#create-test-groups}

### 必要條件

<!-- create-test-group.xml -->

* 您必須至少設定一 **個轉換** 特徵。 您可以在「特徵產生器」中 [設定轉換特徵](../../features/traits/create-onboarded-rule-based-traits.md)，方法 **是選取轉換** 為事件類型。 如需轉換特性的詳細資訊以及如何設定，我們會為您準備 [影片](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) 。

   >[!IMPORTANT]
   >
   >[不支援](../../features/traits/about-folder-traits.md)**資料夾特徵** 。 [!UICONTROL Audience Lab]將資料 [夾特徵的「事件類型](../../features/traits/create-onboarded-rule-based-traits.md) 」設定為 **轉換時** ，不會針對該特定資料夾特徵 [!UICONTROL Audience Lab] 產生任何資料。

* 對於使用基於 [角色的訪問控制的公司](../../features/administration/administration-overview.md): 指派萬用 [!UICONTROL Audience Lab] 字元 [權限](../../features/administration/administration-overview.md#wild-card-permissions) ，以 **[!UICONTROL User Groups]** 提供存取權。 此權限可讓使用者建立並檢視測試結果。 使用者只能使用其具有讀取權限的資料來源 **的****區段並對應至目標** 權限。 使用者只能使用來自其具有「讀取」權限之資料來源的 **轉換特徵** 。 使用者也只能看到他們可存取的目的地。 因此，在將萬用字 [!DNL Audience Lab] 元權限新增至群組之前，請確定群組具有：
   * 讀取相關轉化特徵；
   * 存取讀取並對應相關區段以進行測試；
   * 存取相關目的地。

To create a new [!UICONTROL Segment Test Group]:

1. 在控 **[!UICONTROL Create New Test Group]** 制面板中 [!UICONTROL Audience Lab] 選擇以啟動嚮導。
1. **[!UICONTROL Basic Info & Choose Segment]**

   * 填寫 **[!UICONTROL Test Group Name]** 和 **[!UICONTROL Description]**。
   * 在檔案 **[!UICONTROL Base Segment]** 瀏覽器中導覽，或在搜尋列中輸入，然後按下確認，以選擇 **[!UICONTROL Choose Segment.]**
   * 您可將測試群組儲存為草稿，並稍後繼續處理。
   * 當您選取的基本區段已用於其他測試群組時，將會顯示警報。 兩次使用基本區段可能會扭曲兩個測試的轉換結果。

1. **[!UICONTROL Allocate Test Segments]**

   * 您最多可以 **建立15個測試區段** ，並視需要將裝置百分比除以。
   * 您可以按一下測試區段，以編輯其名稱。
   * 分配新測試區段時，百分比會自動平均分為100%。 然後您可以手動編輯百分比。 編輯百分比後，按一下核取方塊，並確定其加總為100%，否則您將無法繼續下一步。

1. **[!UICONTROL Set a Control Segment]**

   * 如果您想要保留區段的特定部分作為控制群組，請選取控制區段。 控制群組可讓您查看您建立的測試區段與基準的影響。
   * 您可以在下拉式清單中選取測試區段作為控制區段，或選擇不 **[!UICONTROL None]** 加控制。
   * 完 **[!UICONTROL Next]** 成時按一下。

1. **[!UICONTROL Select Conversion Traits]**

   * 在轉換特徵視窗中輸入以新增轉換特徵。 這是必 **備步驟** ，除非您新增至少一個轉換特徵，否則您無法繼續下一個步驟。
   * 如果您願意，最多可以新增5個轉換特徵。
   * 當您選取已用於其他測試群組的轉換特徵時，將會顯示警報。
   * 請注意，Audience Manager不支援將資料夾特 [徵用作](/help/using/features/traits/about-folder-traits.md) 轉換特徵。 選取資料夾特徵作為轉換特徵，會導致測試中顯示0個匯總和趨勢報表。

1. **[!UICONTROL Choose Destinations & Dates]**

   * 在搜尋欄位中輸入所要的目的地，或使用下拉箭頭。 [!UICONTROL Audience Lab] 測試區段可以傳送至URL、Cookie或伺服器對伺服器目的地。
   * 將區段拖放至目標。
   * 將區段拖曳至目的地後，請填入 **[!UICONTROL Destination Mapping Value]** 盲區。
   * 您可以傳送相同的測試區段至多個目的地，也可以將多個測試區段新增至單一目的地。
   * 如果目標無法用於基於「資料匯出控制」的特定測試區段，則 [其會變灰](../../features/data-export-controls.md)。
   * 用戶只會根據所屬的 [RBAC用戶組查看他們有權訪問的目標](../../features/administration/administration-overview.md) 。
   * 最後，您必須為測試群組選取開始日期。 此日期會標示測試群組將發佈至目的地的時段開始。 選 **取「無結束日期** 」，以無限期比較測試區段。

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] 只有即時目的地才支援已驗證的設定檔。 如果含有該設定之設定檔合併規則的測試區段會傳送至檔案型伺服器對伺服器目的地，則可能不會填入觀眾。

   按一 **[!UICONTROL Next]** 下以檢閱並完成您的測試群組。

1. **[!UICONTROL Summary & Finalize]**

   * 檢閱您在先前步驟中新增的資訊，並選取 **[!UICONTROL Finalize Group]**。
   * 請記住，一旦您完成測試群組，就可以複製或刪除，但不能編輯。

   >[!NOTE]
   >* 您可以在建立程式的任何時間點儲存測試群組，稍後再返回精靈。 測試群組狀態為， **[!UICONTROL Draft]** 且測試群組不會傳送任何資料至目的地，直到您完成區段測試群組為止。
   >* 對於草稿測試，您可以按一下主檢視中測試群組卡片中 **[!UICONTROL Edit]** 的，返回並編輯測試 [!UICONTROL Audience Lab] 群組。


## 編輯區段測試群組 {#edit-test-groups}

在 [!UICONTROL Audience Lab]中，您只能編輯草稿測試群組。 在精靈 [!UICONTROL Create Segment Test Group] 中，您可將測試群組儲存為草稿，稍後繼續處理。

1. 導覽至主 [!UICONTROL Audience Lab] 檢視。
1. 搜尋您的草稿測試群組，並選取測 **[!UICONTROL Edit]** 試群組卡中的控制項。
1. 繼續「 [建立區段測試群組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 」精靈， **[!UICONTROL Finalize Group]** 並在完成時選取。

## 刪除區段測試群組 {#delete-test-groups}

1. 導覽至主 [!UICONTROL Audience Lab] 檢視。
1. 尋找您要刪除的測試群組。 您可以:

   * 按測 **[!UICONTROL Delete]** 試群組卡中的控制項，或
   * 按測試組卡中的測試組標題可轉到「 [Test Group Information](../../features/audience-lab/audience-lab-information-view.md) (測試組資訊 **[!UICONTROL Delete]** )」視圖，然後按標題欄中的控制項。

1. 如果 [已完成測試區段](../../features/audience-lab/audience-lab.md#status)，警報會提示您下載CSV檔案以儲存報表。
