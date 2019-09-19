---
description: 建立並管理演算法模型中使用的特徵或區段，也稱為相似模型。 模型功能位於「對象資料>模型」中。
keywords: 相對重量，相似
seo-description: 建立並管理演算法模型中使用的特徵或區段，也稱為相似模型。 模型功能位於「對象資料>模型」中。
seo-title: 關於演算法模型
solution: Audience Manager
title: 關於演算法模型
topic: DIL API
uuid: 39441e72-5316-453d-9aff-0e0b633abang 39441e72-5316-453d-9aff-0e0b633abang
translation-type: tm+mt
source-git-commit: 73d670225fb4170d02428a1dd163f442540e3415

---


# 關於演算法模型 {#about-algorithmic-models}

建立並管理演算法模型中使用的特徵或區段，也稱為相似模型。 模型特徵位於中 **[!UICONTROL Audience Data > Models]**。

<!-- c_models.xml -->

## 瞭解演算模型 {#understanding-models}

以下各節代表對中演算法模型的審查 [!DNL Audience Manager]。 它們說明模型的運作方式、優點和工作流程。

<!-- understanding-models.xml -->

## 使用演算法模型尋找新使用者 {#find-new-users}

演算法模型可協助您透過自動化資料分析，發掘新的獨特受眾。 當您選取特徵或區段、時間間隔以及第一方和第三方資料來源時，程式就會開始。 您的選擇為演算模型提供輸入。 當分析程式執行時，它會根據所選人口的共用特性，尋找符合資格的使用者。 完成時，此資料可在 [Trait Builder](../../features/traits/about-trait-builder.md) ，您可在此處使用，以根據正確性和觸及度 [建立特徵](../../features/traits/trait-accuracy-reach.md)。 此外，您還可以建立結合演算法特徵和規則型特徵的區段，並使用布林運算式和比較運算子新增其他資格要求。 演算法模型提供您動態方式，從所有可用的特徵資料中擷取價值。

## 優勢 {#advantages}

使用模型的主要優 [!DNL Audience Manager] 點包括：

* **** 資料準確性：演算法會定期執行，有助於讓結果保持最新且相關。
* **** 自動化：您不需要管理大量的靜態規則。 演算法會為您尋找受眾。
* **** 節省時間並減少工作量：透過我們的模型建立程式，您不必猜測哪些特性／區段可行，或將時間資源花在促銷活動上，即可發現新的受眾。 模型可以為您執行此操作。
* **** 可靠性：模型可與伺服器端的發現和資格鑑定程式搭配使用，這些程式會評估您自己的資料和您有權存取的所選第三方資料。 這表示您不必查看網站上的訪客，即可讓他們符合某個特徵的資格。

## 工作流程 {#workflow}

您可在中管理模型 **[!UICONTROL Audience Data > Models]**。 在高層，工作流進程涉及以下內容：

* 選取您要演算法評估的基線資料。 這包括特徵或區段、時間範圍和資料來源(您自己的資料和您已透過存取的第三方資 [!DNL Audience Manager]料)。 在模型建立工作流程中，您可以排除不想干擾模型的特徵。
* 保存模型。 儲存後，演算法評估程式就會自動執行。 但請注意，此程式最長需要7天才能完成。 [!DNL Audience Manager] 演算法完成時傳送電子郵件給您，而且結果可用於特徵建立。
* 在中建立演算法特 [!UICONTROL Trait Builder]性。
* 將特徵合併為群體 [!UICONTROL Segment Builder]。
* 建立區段資料並傳送至目標。

## 疑難排解 {#troubleshooting}

我們會停用任何無法產生連續三次執行資料的演算法模型。 請注意，不能將模型的狀態設定回活動狀態。 為確保您的模型產生資料，我們建議您從資料來源建立具備足夠特性的模型，以便從中累積資料。

>[!MORE_LIKE_THIS]
>
>* [目的地](../../features/destinations/destinations.md)
>* [特徵](../../features/traits/trait-details-page.md)
>* [區段](../../features/segments/segments-purpose.md)


## 瞭解特徵權重 {#understanding-traitweight}

[!UICONTROL TraitWeight] 是專屬的演算法，可自動發現新特性。 它會將您目前特徵和區段的特徵資料與您透過存取的所有其他第一方和第三方資料進行比較 [!DNL Audience Manager]。 請參閱本節，以取得演算法探索程 [!UICONTROL TraitWeight] 序的說明。

<!-- traitweight.xml -->

![](assets/algo_model.png)

以下步驟說明評估 [!UICONTROL TraitWeight] 程式。

### 步驟1:建立特徵比較的基準

若要建立基線， [!UICONTROL TraitWeight] 請在30、60或90天間隔內測量與對象相關的所有特徵。 其次，根據特徵的頻率和相關性對特徵進行排序。 頻率計數會測量通用性。 關聯會測量特徵僅出現在基準讀者中的可能性。 通常出現的特徵都顯示出高度的通用性，這是用來設定加權分數的重要特性，當與您在選取的資料來源中發現的特徵結合時。

### 步驟2:在資料來源中尋找相同特徵

在建立基準以進行比較後，演算法會在您選取的資料來源中尋找相同的特徵。 在此步驟中， [!UICONTROL TraitWeight] 會執行所有已發現特徵的頻率計數，並將它們與基線進行比較。 但是，與基線不同，不常見特徵的排名高於經常出現的特徵。 據說稀有性狀表現出高度特異性。 [!UICONTROL TraitWeight] 將常見基線特徵和不常見（高度特定）資料源特徵的組合評估為比兩個資料集共同的特徵更有影響力或更可取。 事實上，我們的模型會識別這些大型的共同特徵，並不會將過多的優先順序指派給高關聯的資料集。 稀有特性優先順序較高，因為它們更可能代表新的獨特使用者，而非具備高度通用性的特性。

### 步驟3:指定權重

在此步驟中，依 [!UICONTROL TraitWeight] 照影響力或期望來排列新發現的特徵。 重量級數是從0%到100%的百分比。 排名接近100%的特徵意味著它們更像您基線人口中的受眾。 此外，重度加權特徵也很有價值，因為它們代表的是新的獨特使用者，其行為可能與您現有的基準受眾類似。 請記住， [!UICONTROL TraitWeight] 將基線中具有高通用性的特徵和比較資料源中具有高特異性的特徵視為比每個資料集中具有高價值的特徵。

### 步驟4:計分使用者

選取資料來源中的每個使用者都會獲得一個使用者分數，該分數等於該使用者描述檔上影響特性的所有權重的總和。 然後，將用戶分數標準化為0到100%。

### 步驟5:顯示並處理結果

Audience manager會在中顯示您的加權模型結果 [!UICONTROL Trait Builder]。 當您想要建立演算法特徵時， [!UICONTROL Trait Builder] 可讓您根據演算法在資料執行期間產生的加權分數來建立特徵。 您可以選擇更高的準確度，以僅限符合使用者分數極高且因此與基準讀者非常相似的使用者，而非其他對象。 如果您想要觸及到更廣的觀眾（觸及），則可降低準確性。

### 步驟6:重新評估特徵在處理週期中的重要性

定期 [!UICONTROL TraitWeight] 地，根據特徵人口的大小和變化，重新評估特徵的重要性。 當符合該特徵的使用者人數隨著時間增加或減少時，就會發生此情況。 這種行為在變大的特徵中最為明顯。 例如，假設演算法使用特徵A進行建模。 隨著特徵A的人數增加， [!UICONTROL TraitWeight] 請重新評估該特徵的重要性，並指派較低的分數或忽略它。 在這種情況下，特徵A太常見或太大，無法對其人口做出任何顯著的評價。 在 [!UICONTROL TraitWeight] 降低特徵A的值（或在模型中忽略它）後，演算法特徵的人口數會減少。 影響力特徵清單反映了基線人口的演化。 使用影響特徵清單，瞭解這些變更發生的原因。

相關連結：

* [模型產生器](../../features/algorithmic-models/create-model.md)
* [準確性與觸及性](../../features/traits/trait-accuracy-reach.md)

## 演算法模型和特徵的更新排程 {#update-schedule}

建立和更新新或現有演算法模型與特徵的排程。

<!-- c_model_update_schedule.xml -->

### 演算法模型建立與更新排程

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> 活動類型 </th>
   <th colname="col2" class="entry"> 說明 </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>建立或克隆模型</b> </td>
   <td colname="col2"> <p>對於新的或克隆的演算法模型，建立程式每天執行一次，網址為： 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 東部時間下午5點（11月- 3月） </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 美國東部夏令時間下午6點（3月- 11月） </li> 
     </ul> </p> <p>在建立截止日期之後構建或克隆的模型將在第二天進行處理。 </p> <p>如果模型的首次運行未生成任何資料，則它將在次日運行第二次。 如果第二次嘗試也未產生任何資料，則第三次嘗試，即第二天。 如果第三次嘗試也未產生任何資料，模型將停止執行。 在這種情況下，我們會停用模型。 請參閱演算法模型 <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> 疑難排解中的更多資訊</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>更新模型</b> </td> 
   <td colname="col2"> <p>在理想條件下，現有的模型在工作日運行，至少每7天運行一次。 例如，如果您在星期一（截止日期）建立模型，則最遲會在下星期一更新模型。 </p> <p>如果模型滿足以下任一條件，則其將重新運行： </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">上次運行未成功。 </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">它在過去7天內根本沒有運行，而且模型至少附有一個活動特徵。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 演算法特徵建立和更新排程

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 活動類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>建立特徵</b> </td> 
   <td colname="col2"> <p>特徵建立程式會每天執行，週一到週五。 通常，新演算法特徵會在48小時內出現在UI中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>更新特徵</b> </td> 
   <td colname="col2"> <p>現有特徵至少每7天更新一次，並依照模型更新的排程進行。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模型清單視圖 {#models-list-view}

清單檢視是一個集中工作區，可協助您建立、檢視及管理模型。

<!-- c_models_list_view.xml -->

「模型」(Models)清單頁包含有助於您：

* 建立新模型。
* 管理現有模型（編輯、暫停、刪除或仿製）。
* 依名稱搜尋模型。
* 使用任何特定模型建立演算法特徵。

## 模型摘要視圖 {#models-summary-view}

摘要頁面會顯示模型詳細資訊，例如名稱、觸及／準確度、處理歷史記錄以及從模型建立的特徵。 該頁還包含可讓您建立和管理模型的設定。 按一下摘要清單中的模型名稱以查看其詳細資訊。

<!-- c_models_summary.xml -->

模型摘要頁包括以下幾節。

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 區域 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> 基本資訊</span> </p> </td>
   <td colname="col2"> <p>包含模型的基本資訊，例如其名稱和上次執行時間。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型觸及度與精確度</span> </p> </td> 
   <td colname="col2"> <p>顯示 <a href="../../features/traits/trait-accuracy-reach.md"> 上次模型執行</a> ，其精確度和觸及資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型處理歷史記錄</span> </p> </td> 
   <td colname="col2"> <p>顯示最近10次執行的處理日期和時間，以及這些執行上是否產生資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 影響力特徵</span> </p> </td> 
   <td colname="col2"> <p>The <span class="wintitle"> Affolment Traits</span> table: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 列出模型基線人口中最具影響力的50項最佳特徵。 </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">依其相對權重排名來排 <span class="wintitle"> 名每個特徵</span> 。 「相 <span class="wintitle"> 對權重</span> 」會根據影響或期望對新發現的特徵進行排序。 重量級數是從0%到100%的百分比。 排名接近100%的特徵意味著它們更像您基線人口中的受眾。 請參閱 <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> 瞭解TraitWeight</a>。 </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">顯示每個特徵的30天獨特值和特徵總人口。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 使用模型的特徵</span> </p> </td>
   <td colname="col2"> <p>顯示根據所選模型的演算法特徵清單。 按一下特徵名稱或特徵ID，以取得特徵的詳細資訊。 選取 <b><span class="uicontrol"> 「使用模型建立新特徵</span></b> 」，以前往演算法特徵建立程式。 </p> <p>截面標籤會根據模型名稱而改變。 例如，假設您建立模型並將其命名為模型A。載入摘要頁面時，此區段的名稱會變更為「使用模 <span class="wintitle"> 型A的特徵」</span>。 </p> </td>
  </tr>
 </tbody>
</table>