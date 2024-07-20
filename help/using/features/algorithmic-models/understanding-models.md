---
description: 建立並管理用於相似建模的特徵或區段。
keywords: 相對權重、相似對象
seo-description: Build and manage the traits or segments used in look-alike modeling.
seo-title: About Look-Alike Modeling
solution: Audience Manager
title: 關於相似建模
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1602'
ht-degree: 0%

---

# 瞭解[!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## 尋找具有[!UICONTROL Look-Alike Modeling]的新使用者 {#find-new-users}

[!UICONTROL Look-Alike Modeling]可協助您透過自動化資料分析，探索新的不重複對象。 當您選取[!UICONTROL trait]或[!UICONTROL segment]、時間間隔以及第一方和第三方[!UICONTROL data sources]時，程式就會開始。 您的選擇會提供演演算法模型的輸入。 分析程式執行時，會根據所選母體的共用特性來尋找符合資格的使用者。 完成時，此資料可在[特徵產生器](../../features/traits/about-trait-builder.md)中使用，您可以在其中根據[精確度和觸及率](../../features/traits/trait-accuracy-reach.md)來建立特徵。 此外，您可以建立結合演演算法特徵與[!UICONTROL rules-based traits]的區段，並新增其他資格要求與[!DNL Boolean]運算式和比較運運算元。 [!UICONTROL Look-Alike Modeling]可讓您以動態方式從所有可用的特徵資料中擷取值。

## 優勢 {#advantages}

使用[!UICONTROL Look-Alike Modeling]的主要優點包括：

* **資料準確度：**&#x200B;演演算法會定期執行，有助於保持結果的最新和相關性。
* **自動化：**&#x200B;您不需要管理大量靜態規則。 演演算法會為您尋找對象。
* **節省時間並減少工作量：**&#x200B;使用我們的模型化程式，您不必猜測[!UICONTROL traits]/[!UICONTROL segments]可能會運作或花費時間資源在行銷活動上，以探索新對象。 模型可以為您執行此操作。
* **可靠性：**&#x200B;模型適用於伺服器端探索與資格驗證程式，以評估您自己的資料以及您有權存取的選取第三方資料。 這表示您不需要看見網站上的訪客，就能符合特徵資格。

## 工作流程 {#workflow}

您在&#x200B;**[!UICONTROL Audience Data > Models]**&#x200B;中管理模型。 從高層面來看，工作流程流程涉及以下內容：

* 選取您希望演演算法評估的基準資料。 這包括[!UICONTROL trait]或[!UICONTROL segment]、時間範圍和[!UICONTROL data sources] （您自己的資料和您透過[!DNL Audience Manager]已可存取的第三方資料）。 在模型建立工作流程中，您可以排除不想干擾模型的[!UICONTROL traits]。
* 儲存您的模型。 儲存後，演演算法評估程式會自動執行。 但請注意，此程式最多可能需要7天才能完成。 當演演算法完成且結果可用於建立[!UICONTROL trait]時，[!DNL Audience Manager]會傳送電子郵件給您。
* 在[!UICONTROL Trait Builder]中建置演演算法[!UICONTROL traits]。
* 在[!UICONTROL Segment Builder]中將[!UICONTROL traits]合併為[!UICONTROL segments]。
* 建立[!UICONTROL segment]資料並傳送至[!UICONTROL destination]。

## 疑難排解 {#troubleshooting}

我們會停用任何無法產生連續三個回合資料的[!UICONTROL Look-Alike Model]。 請注意，之後您無法將模型的狀態設定回「使用中」。 若要確保您的模型產生資料，建議您從資料來源建立模型，並具備足夠的[!UICONTROL traits]來累積資料。

## 瞭解[!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight]是專有的演演算法，用來自動探索新的[!UICONTROL traits]。 它會比較您目前[!UICONTROL traits]和[!UICONTROL segments]的[!UICONTROL trait]資料，與您透過[!DNL Audience Manager]存取的所有其他第一方和第三方資料。 請參閱本節以取得[!UICONTROL TraitWeight]演演算法探索程式的說明。

![](assets/algo_model.png)

下列步驟說明[!UICONTROL TraitWeight]評估程式。

### 步驟1：建立[!UICONTROL Trait]比較的基線

若要建置基準，[!UICONTROL TraitWeight]會以30、60或90天為間隔測量與對象相關聯的所有[!UICONTROL traits]。 接著，它會根據頻率和相關性對[!UICONTROL traits]排名。 頻率計數可測量通用性。 相互關聯會測量[!UICONTROL trait]僅存在於基線對象中的可能性。 經常出現的[!UICONTROL Traits]據說具有高通用性，這是當您與所選[!UICONTROL data sources]中發現的[!UICONTROL traits]結合時，用來設定加權分數的重要特性。

### 步驟2：在[!UICONTROL Data Source]中找到相同的[!UICONTROL Traits]

在建置比較基準線後，演演算法會在您選取的[!UICONTROL data sources]中尋找相同的[!UICONTROL traits]。 在此步驟中，[!UICONTROL TraitWeight]會對所有發現的[!UICONTROL traits]執行頻率計數，並將它們與基準進行比較。 不過，與基準線不同，不常見的[!UICONTROL traits]的排名高於出現頻率較高的專案。 稀有[!UICONTROL traits]據說具有高度的特異性。 [!UICONTROL TraitWeight]會評估共同基準線[!UICONTROL traits]與不常見（高度特定） [!UICONTROL data source] [!UICONTROL traits]的組合，認為其比兩個資料集共用的[!UICONTROL traits]更具影響力或令人滿意。 事實上，我們的模型會辨識這些大型的通用[!UICONTROL traits]，不會將超額優先順序指派給具有高關聯性的資料集。 罕見的[!UICONTROL traits]獲得更高的優先順序，因為它們比[!UICONTROL traits]更可能代表新的、不重複的使用者，而且所有使用者都有較高的通用性。

### 步驟3：指定權重

在此步驟中，[!UICONTROL TraitWeight]將新發現的[!UICONTROL traits]排在影響或可取性的順序中。 重量刻度是從0%到100%的百分比。 [!UICONTROL Traits]的排名更接近於100%，這表示他們在您的基線母體中更像是對象。 此外，重度加權[!UICONTROL traits]很有價值，因為它們代表新的不重複使用者，其行為可能與您建立的基線對象類似。 請記住，[!UICONTROL TraitWeight]認為基準線中具有高通用性的[!UICONTROL traits]以及比較的資料來源中具有高特定性的比每個資料集中通用的[!UICONTROL traits]更有價值。

### 步驟4：評分使用者

所選[!UICONTROL data sources]中的每個使用者都會獲得使用者分數，該分數等於該使用者設定檔上具影響力[!UICONTROL traits]的所有權重總和。 接著，使用者分數會標準化為0到100%之間。

### 步驟5：顯示和使用結果

[!DNL Audience Manager]在[!UICONTROL Trait Builder]中顯示您的加權模型結果。 當您想要建置[!UICONTROL algorithmic trait]時，[!UICONTROL Trait Builder]可讓您根據資料執行期間演演算法產生的加權分數來建立[!UICONTROL traits]。 您可以選擇較高的準確度，以僅符合具有非常高使用者分數、因此與基線對象（而非其餘對象）非常類似的使用者資格。 如果您想要觸及更大的對象（觸及範圍），您可以降低準確度。

### 步驟6：重新評估[!UICONTROL Trait]在處理週期中的重要性

[!UICONTROL TraitWeight]會定期根據該[!UICONTROL trait]母體的大小和變更重新評估[!UICONTROL trait]的重要性。 符合該[!UICONTROL trait]資格的使用者數目會隨著時間增加或減少，而發生此情況。 在變得非常大的特徵中，這種行為表現得最為明顯。 例如，假設演演算法使用[!UICONTROL trait A]來建立模型。 隨著[!UICONTROL trait A]的母體增加，[!UICONTROL TraitWeight]會重新評估該[!UICONTROL trait]的重要性，並可能指派較低的分數或忽略該分數。 在這種情況下，[!UICONTROL trait A]太常見或太大，無法對其母體說出任何重要訊息。 在[!UICONTROL TraitWeight]減少[!UICONTROL trait A]的值（或在模型中忽略該值）之後，演演算法特徵的母體會減少。 具影響力的[!UICONTROL traits]清單反映基線母體的演化。 使用具影響力的[!UICONTROL traits]清單來瞭解發生這些變更的原因。

相關連結：

* [模型產生器](../../features/algorithmic-models/create-model.md)
* [精確度和觸及](../../features/traits/trait-accuracy-reach.md)

## [!UICONTROL Look-Alike Models]和[!UICONTROL Traits]的更新排程 {#update-schedule}

建立與更新新或現有[!UICONTROL algorithmic models]與[!UICONTROL traits]的排程。

### [!UICONTROL Look-Alike Model]建立和更新排程

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> 活動類型 </th>
   <th colname="col2" class="entry"> 說明 </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>建立或複製模型</b> </td>
   <td colname="col2"> <p>對於新的或複製的[!UICONTROL Look-Alike Models]，建立程式會在以下日期每天執行一次： 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 東部時間下午5點（11月到3月） </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 下午6點(EDT) （3月至11月） </li> 
     </ul> </p> <p>系統會在次日處理於建立期限之後建立或複製的模型。 </p> <p>如果模型的第一次執行未產生任何資料，則會於次日執行第二次。 如果第二次嘗試也未產生任何資料，則會在隔天進行第三次嘗試。 如果第三次嘗試也未產生任何資料，則模型將停止執行。 在此情況下，我們將停用模型。 在<a href="../../features/algorithmic-models/understanding-models.md#troubleshooting">疑難排解相似模型</a>中檢視更多資訊。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>更新模型</b> </td> 
   <td colname="col2"> <p>在理想的情況下，現有模型會在工作日執行，至少每7天執行一次。 例如，如果您在星期一建立模型（依截止日期），則模型最晚會更新下個星期一。 </p> <p>如果模型符合下列任一條件，則會重新執行： </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">它的最後一次執行未成功。 </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">它之前已順利執行，而且在過去7天內完全沒有執行，而且模型至少附加一個作用中特徵。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait]建立和更新排程

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
   <td colname="col2"> <p>特徵建立程式每天都會執行，星期一到星期五。 新演演算法特徵通常會在48小時內出現在UI中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>更新特徵</b> </td> 
   <td colname="col2"> <p>現有特徵至少每7天更新一次，並遵循模型更新排程。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模型清單檢視 {#models-list-view}

清單檢視是一個中央工作區，可協助您建立、檢閱和管理模型。

[!UICONTROL Models]清單頁面包含可協助您：

* 建立新模型。
* 管理現有模型（編輯、暫停、刪除或複製）。
* 依名稱搜尋模型。
* 使用任何指定模型建立[!UICONTROL algorithmic traits]。

## 模型摘要檢視 {#models-summary-view}

摘要頁面會顯示模型詳細資訊，例如，名稱、觸及率/準確度、處理歷史記錄，以及從模型建立的[!UICONTROL traits]。 此頁面也包含可讓您建立和管理模型的設定。 按一下摘要清單中的模型名稱以檢視其詳細資訊。

模型摘要頁面包含下列段落。

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 區域 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle">基本資訊</span> </p> </td>
   <td colname="col2"> <p>包括模型的基本資訊，例如名稱和上次執行時間。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">模型觸及範圍和準確度</span> </p> </td> 
   <td colname="col2"> <p>顯示上次模型執行的<a href="../../features/traits/trait-accuracy-reach.md">精確度和</a>資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">模型處理歷史記錄</span> </p> </td> 
   <td colname="col2"> <p>顯示最後10次執行的處理日期和時間，以及這些執行是否產生資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">個具影響力的特徵</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">具影響力的特徵</span>資料表： </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 列出在模型的基線母體中表現最佳的前50個具影響力的特徵。 </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">依照每個特徵的<span class="wintitle">相對權重</span>排名將特徵排名。 <span class="wintitle">相對權數</span>會依影響或可取性的順序排序新發現的特徵。 重量刻度是從0%到100%的百分比。 特徵排名接近100%，表示它們更像是基線人口中的受眾。 請參閱<a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight">瞭解TraitWeight</a>。 </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">顯示30天不重複值以及每個特徵的總特徵人口。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 使用模型</span>的<span class="wintitle">特徵 </p> </td>
   <td colname="col2"> <p>根據選取的模型顯示演演算法特徵清單。 按一下特徵名稱或特徵ID，即可取得特徵的詳細資訊。 選取「<b><span class="uicontrol">使用模型建立新特徵</span></b>」以前往演演算法特徵建立程式。 </p> <p>區段標籤會根據模型的名稱而變更。 例如，假設您建立模型並將其命名為「模型A」。載入摘要頁面時，此區段的名稱會使用模型A</span>變更為<span class="wintitle">特徵。 </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [目的地](../../features/destinations/destinations.md)
>* [特徵](../../features/traits/trait-details-page.md)
>* [區段](../../features/segments/segments-purpose.md)
