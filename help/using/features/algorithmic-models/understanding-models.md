---
description: 建立並管理演算法模型中使用的特徵或區段，也稱為外觀相似的模型。模型功能位於「對象資料>模型」中。
keywords: 相對粗細，類似
seo-description: 建立並管理演算法模型中使用的特徵或區段，也稱為外觀相似的模型。模型功能位於「對象資料>模型」中。
seo-title: 關於演算法模型
solution: Audience Manager
title: 關於演算法模型
topic: DIL API
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
translation-type: tm+mt
source-git-commit: 73d670225fb4170d02428a1dd163f442540e3415

---


# 關於演算法模型 {#about-algorithmic-models}

建立並管理演算法模型中使用的特徵或區段，也稱為外觀相似的模型。模型功能 **[!UICONTROL Audience Data > Models]**&#x200B;位於。

<!-- c_models.xml -->

## 瞭解演算法模型 {#understanding-models}

以下章節代表演算法模型的審查 [!DNL Audience Manager]。它們說明模型運作方式、優點和工作流程。

<!-- understanding-models.xml -->

## 使用演算法模型尋找新使用者 {#find-new-users}

演算法模型可協助您透過自動化資料分析發掘新的獨特受眾。當您選取特徵或區段、時間間隔以及第一方和第三方資料來源時，會啓動程序。您的選擇會提供演算法模型的輸入。分析程序執行時，會根據所選人口的共用特性尋找符合資格的使用者。在完成後，您可在 [「特徵產生器」中使用此資料，](../../features/traits/about-trait-builder.md) 您可在此使用它來根據 [準確度和觸及來建立特性](../../features/traits/trait-accuracy-reach.md)。此外，您還可以建立區段，將演算法特性與規則特徵結合，並使用布林運算式和比較運算子新增其他資格要求。演算法模型可讓您動態擷取所有可用特徵資料的值。

## 優勢 {#advantages}

[!DNL Audience Manager] 使用模型的主要優點包括：

* **資料精確性：** 演算法會定期執行，有助於維持結果和相關性。
* **自動化：** 您不需要管理大量的靜態規則。演算法會為您尋找對象。
* **節省時間和精力：** 透過我們的模型流程，您無需猜測哪些特性/區段可以在促銷活動上運作，或在促銷活動上花費時間資源來發掘新受眾。模型可為您執行此動作。
* **可靠性：** 模型可與伺服器端發現和資格程序搭配使用，可評估您自己的資料和所選的第三方資料。這表示您無需查看網站上的訪客以符合特徵。

## 工作流程 {#workflow}

您可以管理模型 **[!UICONTROL Audience Data > Models]**。從高層級開始，工作流程程序包括：

* 選取您要評估的基準資料。這包括特徵或區段、時間範圍和資料來源(您自己已存取的 [!DNL Audience Manager]資料和第三方資料)。在模型建立工作流程中，您可以排除不想要干擾模型的特性。
* 儲存模型。儲存後，演算評估程序就會自動執行。但是，請注意，此程序可能需要天才能完成。[!DNL Audience Manager] 當演算法完成並可用於特徵建立時，會傳送電子郵件給您。
* 建立演算法特徵 [!UICONTROL Trait Builder]。
* 將特徵合併為細分 [!UICONTROL Segment Builder]。
* 建立並傳送區段資料至目的地。

## 疑難排解 {#troubleshooting}

我們停用任何無法產生三個連續執行資料的演算法模型。請注意，您無法將模型狀態設定回作用中。為了確保模型產生資料，建議您從具有足夠特性的資料來源建立模型，以累積資料。

>[!MORE_贊_ this]
>
>* [目的地](../../features/destinations/destinations.md)
>* [特徵](../../features/traits/trait-details-page.md)
>* [區段](../../features/segments/segments-purpose.md)


## 瞭解TritWeight {#understanding-traitweight}

[!UICONTROL TraitWeight] 是專門用來探索新特性的專有演算法。它會將特徵資料與您目前存取的所有其他第一方和第三方資料相比較的特徵資料進行比較 [!DNL Audience Manager]。請參閱本節以瞭解 [!UICONTROL TraitWeight] 演算法探索程序的說明。

<!-- traitweight.xml -->

![](assets/algo_model.png)

以下步驟說明 [!UICONTROL TraitWeight] 評估程序。

### 步驟1：建立特徵比較的基準

若要建立基準， [!UICONTROL TraitWeight] 請測量30、60或90天間隔內與觀眾相關的所有特性。接著，它會根據其頻率及其關聯來排名特徵。頻率計數會測量共性。關聯會測量僅在基準對象中呈現特徵的可能性。常出現的特性通常表示高共同性，這是結合在選定資料來源中所發現特徵時用來設定加權分數的重要特性。

### 步驟2：在資料來源中尋找相同特徵

建立基準以進行比較後，演算法會尋找所選資料來源中相同的特性。在此步驟中 [!UICONTROL TraitWeight] ，對所有發現的特徵執行頻率計數，並將它們與基準進行比較。不過，與基準不同的是，不常見特徵的排名高於經常出現的特徵。據說稀有特徵表現出高度的特異性。[!UICONTROL TraitWeight] 評估常見基準特徵和非常見(高度特定)資料來源特徵的組合，其影響或喜好大於這兩個資料集通用的特性。事實上，我們的模型識別了這些大型、常見特徵，並不指派高關聯資料集的優先順序。稀有特徵會得到較高的優先順序，因為在展示板中，比起具有高共通度特徵的特性，他們更有可能代表新的獨特使用者。

### 步驟3：指派權重

在此步驟中， [!UICONTROL TraitWeight] 依照影響或可擴充性排列新發現的特徵。加權等級是從0%到100%的百分比。特徵排名接近100%意味著它們更像基準人口中的觀眾。此外，重度加權特徵很有價值，因為它們代表了新的獨特使用者，其行為可能類似於您現有的基準對象。請記住， [!UICONTROL TraitWeight] 在比較資料來源中具有高相關性的特徵和比較資料來源的高相關性，相較於每個資料集中常見的特性。

### 步驟4：計分使用者

所選資料來源中的每位使用者都會得到使用者分數，等於該使用者個人資料上具有影響力特徵之所有權重的總和。然後，使用者分數會標準化到100%之間。

### 步驟5：顯示並使用結果

Audience Manager會顯示您的加權模型 [!UICONTROL Trait Builder]。當您想要建立演算法特徵時， [!UICONTROL Trait Builder] 可讓您根據演算法在執行資料期間產生的加權分數來建立特徵。您可以選擇較高的準確性，僅限擁有非常高使用者分數的使用者，因此與基準對象非常相似，而非其他對象。如果您想要觸及更廣大的觀眾(觸及)，可以降低精確度。

### 步驟6：重新評估特徵跨處理週期的重要性

定期評估 [!UICONTROL TraitWeight] 特徵的重要性，以根據該特徵中的人數和變更來重新評估特徵。這會發生在符合該特徵的使用者人數增加或減少的情況下。這種行為在變得很大的特性中最為明顯。例如，假設演算法使用特徵A做為模型。當特徵A增加時， [!UICONTROL TraitWeight] 會重新評估該特徵的重要性，並指定較低分數或忽略分數。在這種情況下，特徵A太常或很大，對其人口族群說得很重要。[!UICONTROL TraitWeight] 在降低特徵A的值(或忽略模型)後，演算法特徵的人口會減少。具影響力特徵的清單反映基準人口的演變。使用具影響力的特性清單，瞭解這些變更為何發生。

相關連結：

* [Model Builder](../../features/algorithmic-models/create-model.md)
* [正確性與觸及面](../../features/traits/trait-accuracy-reach.md)

## 演算法模型和特徵的更新排程 {#update-schedule}

建立和更新新的演算法模型和特徵的排程。

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
   <td colname="col1"> <b>建立或仿制模型</b> </td>
   <td colname="col2"> <p>對於新的或仿制的演算法模型，建立程序每天執行一次： 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> PM EST(11月-月) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> PM EDT(月-11月) </li> 
     </ul> </p> <p>建立或複製之後，在建立截止日期後的模型。 </p> <p>如果第一個模型的執行不產生任何資料，則會第二天執行第二次。如果第二次嘗試也沒有產生任何資料，則會在第二天嘗試第三次嘗試。如果第三個嘗試也沒有產生任何資料，模型將停止執行。在此情況下，我們將停用模型。請參閱 <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> 疑難排解演算法模型中的更多</a>資訊。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>更新模型</b> </td> 
   <td colname="col2"> <p>在理想狀況下，現有的模型會在工作日執行，每個天至少執行一次。例如，如果您在星期一建立模型(截止日期)，則會在星期一更新下一個星期一。 </p> <p>如果模型符合下列任何條件，則會重新執行模型： </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">上次執行失敗。 </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">它已順利執行，而且過去天都無法執行，而且模型至少會附加一個作用中特徵。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 演算法特徵建立與更新排程

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
   <td colname="col2"> <p>特徵建立程序會每天執行，週一到週五。一般而言，新的演算法特徵會在48小時內顯示在UI中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>更新特徵</b> </td> 
   <td colname="col2"> <p>現有特徵每個天至少更新一次，並依照模型更新的排程進行。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模型清單檢視 {#models-list-view}

清單檢視是一個中央工作區，可協助您建立、檢閱和管理模型。

<!-- c_models_list_view.xml -->

「模型」清單頁面包含可幫助您：

* 建立新模型。
* 管理現有模型(編輯、暫停、刪除或複製)。
* 依名稱搜尋模型。
* 使用任何指定的模型建立演算法特徵。

## 模型摘要檢視 {#models-summary-view}

摘要頁面會顯示模型詳細資訊，例如名稱、觸及/準確度、處理歷史記錄以及模型建立的特徵。此頁面也包含可讓您建立和管理模型的設定。按一下摘要清單中的模型名稱，以查看其詳細資料。

<!-- c_models_summary.xml -->

模型摘要頁面包含下列章節。

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
   <td colname="col2"> <p>包含模型的基本資訊，例如名稱和上次執行的時間。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型觸及與正確性</span> </p> </td> 
   <td colname="col2"> <p>顯示 <a href="../../features/traits/trait-accuracy-reach.md"> 最後一個模型執行的正確性和觸及</a> 資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型處理歷史記錄</span> </p> </td> 
   <td colname="col2"> <p>顯示最近10執行的處理日期和時間，以及是否在這些執行上產生資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 有影響力的特性</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 具影響力的特徵</span> 表格： </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 列出模型基準人口中最具代表性的50個重要特徵。 </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">依「 <span class="wintitle"> 相對權重</span> 」排名排列每個特徵的順序。<span class="wintitle"> 「相對加權</span> 」會依照影響或可預測性排序新發現的特徵。加權等級是從0%到100%的百分比。特徵排名接近100%意味著它們更像基準人口中的觀眾。請參閱 <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> 瞭解TritWeight</a>。 </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">顯示每個特徵的30天獨特訪客和特徵人口總數。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 使用模型的特性</span> </p> </td>
   <td colname="col2"> <p>顯示根據選取模型的演算法特性清單。按一下特徵名稱或特徵ID，以取得特徵的詳細資訊。選取 <b><span class="uicontrol"> 「建立新特徵」搭配模型</span></b> 進入演算法特徵建立程序。 </p> <p>區段標籤會根據模型的名稱而改變。例如，假設您建立模型並命名為Model A。載入摘要頁面時，此區域的名稱會使用模型A變更 <span class="wintitle"> 為特性</span>。 </p> </td>
  </tr>
 </tbody>
</table>