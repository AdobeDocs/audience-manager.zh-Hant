---
description: 此程式會逐步引導您完成在Audience Lab中建立、編輯或刪除測試群組所需的步驟
seo-description: 此程式會逐步引導您完成在Audience Lab中建立、編輯或刪除測試群組所需的步驟
seo-title: 管理測試群組
solution: Audience Manager
title: 管理測試群組
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 1%

---

# 管理測試群組 {#manage-test-groups}

此過程將引導您完成在[!UICONTROL Audience Lab]中建立、編輯或刪除測試組所需的步驟。

## 建立區段測試群組{#create-test-groups}

### 必要條件

<!-- create-test-group.xml -->

* 您至少需要設定一個&#x200B;**轉換特徵**。 您可以在[特徵產生器](../../features/traits/create-onboarded-rule-based-traits.md)中設定轉換特徵，方法是選取&#x200B;**轉換**&#x200B;作為事件類型。 如需轉換特徵的詳細資訊及如何設定，我們已為您準備[video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html)。

   >[!IMPORTANT]
   >
   >[不](../../features/traits/about-folder-traits.md) 支援 **資** 料夾 [!UICONTROL Audience Lab]。將資料夾特徵的[事件類型](../../features/traits/create-onboarded-rule-based-traits.md)設定為&#x200B;**轉換**&#x200B;將不會為該特定資料夾特徵在[!UICONTROL Audience Lab]中產生任何資料。

* 對於使用[基於角色的訪問控制](../../features/administration/administration-overview.md)的公司：將[!UICONTROL Audience Lab] [萬用字元權限](../../features/administration/administration-overview.md#wild-card-permissions)指派至&#x200B;**[!UICONTROL User Groups]**&#x200B;以提供存取權。 此權限可讓使用者建立和檢視測試結果。 使用者只能使用其&#x200B;**read**&#x200B;和&#x200B;**對應至目的地**&#x200B;權限的資料來源區段。 使用者只能使用來自其擁有&#x200B;**&quot;read&quot;**&#x200B;權限之資料來源的轉換特徵。 使用者也只能看到其有權存取的目的地。 因此，在將[!DNL Audience Lab]萬用字元權限添加到組之前，請確保組具有：
   * 存取相關轉換特徵；
   * 存取讀取並映射測試的相關區段；
   * 存取相關目的地。

要建立新的[!UICONTROL Segment Test Group]，請執行以下操作：

1. 在[!UICONTROL Audience Lab]控制面板中選擇&#x200B;**[!UICONTROL Create New Test Group]**&#x200B;以啟動嚮導。
1. **[!UICONTROL Basic Info & Choose Segment]**

   * 填寫&#x200B;**[!UICONTROL Test Group Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
   * 在檔案瀏覽器中導覽或在搜尋列中輸入，以選擇&#x200B;**[!UICONTROL Base Segment]** ，然後按&#x200B;**[!UICONTROL Choose Segment.]**&#x200B;確認
   * 您可以將測試群組儲存為草稿，稍後繼續處理。
   * 如果您選取的基本區段已用於其他測試群組，則會顯示警報。 兩次使用基區段可能會扭曲兩個測試的轉換結果。

1. **[!UICONTROL Allocate Test Segments]**

   * 您可以建立最多15個測試區段&#x200B;**，並視需要劃分裝置百分比。**
   * 您可以按一下測試區段的名稱來編輯這些區段。
   * 分配新測試區段時，百分比會自動平均分配至100%。 然後，您可以手動編輯百分比。 編輯百分比後，請按一下核取方塊，確認加總高達100%，否則您將無法繼續進行下一個步驟。

1. **[!UICONTROL Set a Control Segment]**

   * 如果您想要預留區段的特定部分以用作控制組，請選取控制段。 控制組可讓您比較您建立的測試區段與基準的影響。
   * 您可以在下拉式清單中選取測試區段作為控制區段，或選擇&#x200B;**[!UICONTROL None]**&#x200B;以無控制。
   * 完成後，按一下&#x200B;**[!UICONTROL Next]**。

1. **[!UICONTROL Select Conversion Traits]**

   * 在轉換特徵視窗中輸入內容，即可新增轉換特徵。 這是&#x200B;**必填**&#x200B;步驟，除非您至少新增一個轉換特徵，否則您無法繼續進行下一個步驟。
   * 您可以視需要新增最多5個轉換特徵。
   * 若您選取已用於其他測試群組的轉換特徵，則會顯示警報。
   * 請注意，Audience Manager不支援使用[資料夾特徵](/help/using/features/traits/about-folder-traits.md)作為轉換特徵。 選取資料夾特徵作為轉換特徵，會在測試中顯示0個匯總和趨勢報表。

1. **[!UICONTROL Choose Destinations & Dates]**

   * 在搜尋欄位中輸入所需目的地，或使用下拉式箭頭。 [!UICONTROL Audience Lab] 測試區段可以傳送至URL、Cookie或伺服器對伺服器目的地。
   * 拖放區段至目的地。
   * 在目的地中放置區段後，在盲區中填入&#x200B;**[!UICONTROL Destination Mapping Value]**。
   * 您可以傳送相同的測試區段至多個目的地，並且可以新增多個測試區段至單一目的地。
   * 如果目的地無法用於根據[資料匯出控制項](../../features/data-export-controls.md)的特定測試區段，則其會反灰。
   * 使用者只會根據其所屬的[RBAC使用者群組](../../features/administration/administration-overview.md)查看其有權存取的目的地。
   * 最後，您必須選取測試群組的開始日期。 此日期會標籤將測試群組發佈至目的地的期間開始。 選取「**無結束日期**」 ，即可無限期比較測試區段。

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] 只有即時目的地支援搭配已驗證的設定檔。如果具有該設定之設定檔合併規則的測試區段傳送至檔案式伺服器對伺服器目的地，則可能不會填入對象。

   按一下&#x200B;**[!UICONTROL Next]**&#x200B;以檢閱並完成您的測試群組。

1. **[!UICONTROL Summary & Finalize]**

   * 查看在前面的步驟中添加的資訊，並選擇&#x200B;**[!UICONTROL Finalize Group]**。
   * 請記住，一旦您完成測試群組，該群組即可複製或刪除，但無法編輯。

   >[!NOTE]
   >* 您可以在建立過程中的任何時間點保存測試組，並稍後返回嚮導。 測試群組狀態將為&#x200B;**[!UICONTROL Draft]**，而測試群組在您完成區段測試群組之前不會傳送任何資料至目的地。
   >* 對於草稿測試，您可以按一下主[!UICONTROL Audience Lab]檢視中測試群組卡片中的&#x200B;**[!UICONTROL Edit]** ，返回並編輯測試群組。


## 編輯段測試組{#edit-test-groups}

在[!UICONTROL Audience Lab]中，您只能編輯草稿測試群組。 在[!UICONTROL Create Segment Test Group]精靈中，您可以將測試群組儲存為草稿，並稍後繼續處理。

1. 導覽至[!UICONTROL Audience Lab]主檢視。
1. 搜尋草稿測試群組，並在測試群組卡片中選取&#x200B;**[!UICONTROL Edit]**&#x200B;控制項。
1. 繼續[建立區段測試群組](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)精靈，並在完成時選取&#x200B;**[!UICONTROL Finalize Group]**。

## 刪除段測試組{#delete-test-groups}

1. 導覽至[!UICONTROL Audience Lab]主檢視。
1. 找出您要刪除的測試群組。 您可以:

   * 按測試組卡中的&#x200B;**[!UICONTROL Delete]**&#x200B;控制項，或
   * 按測試組卡中的測試組標題，轉至[測試組資訊](../../features/audience-lab/audience-lab-information-view.md)視圖，然後按標題欄中的&#x200B;**[!UICONTROL Delete]**&#x200B;控制項。

1. 對於[已完成的測試區段](../../features/audience-lab/audience-lab.md#status)，警報會提示您下載CSV檔案以儲存報表（如果您想要）。
