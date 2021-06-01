---
description: 建立及管理相似建模中使用的特徵或區段。
keywords: 相對重量，相似者
seo-description: 建立及管理相似建模中使用的特徵或區段。
seo-title: 關於相似建模
solution: Audience Manager
title: 關於相似建模
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: 演算法模型
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1595'
ht-degree: 1%

---

# 了解[!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## 查找[!UICONTROL Look-Alike Modeling] {#find-new-users}的新用戶

[!UICONTROL Look-Alike Modeling] 可協助您透過自動化資料分析，探索新的不重複受眾。當您選取[!UICONTROL trait]或[!UICONTROL segment]、時間間隔，以及第一方和第三方[!UICONTROL data sources]時，流程就會開始。 您的選擇為演算法模型提供輸入。 分析程式執行時，會根據所選母體的共用特性，尋找符合資格的使用者。 完成後，此資料可在[特徵產生器](../../features/traits/about-trait-builder.md)中使用，您可在此處根據[正確度建立特徵並達到](../../features/traits/trait-accuracy-reach.md)。 此外，您也可以建立區段，將演算法特徵與[!UICONTROL rules-based traits]結合，並使用[!DNL Boolean]運算式和比較運算子新增其他資格要求。 [!UICONTROL Look-Alike Modeling] 可讓您以動態方式從所有可用的特徵資料中擷取值。

## 優勢 {#advantages}

使用[!UICONTROL Look-Alike Modeling]的主要好處包括：

* **資料正確性：** 演算法會定期執行，有助於讓結果保持最新且相關。
* **自動化：** 您不需要管理大量靜態規則。演算法會為您尋找對象。
* **節省時間並減少工作量：** 透過我們的模型程式，您不必猜測什麼/可 [!UICONTROL traits][!UICONTROL segments] 能有效，或將時間資源花在行銷活動上以探索新對象。模型可以為您執行此操作。
* **可靠性：** 模型可與伺服器端探索和資格認證程式搭配使用，以評估您自己的資料和您有權存取的所選第三方資料。這表示您不必在網站上看見訪客，即可讓他們符合特徵的資格。

## 工作流程 {#workflow}

在&#x200B;**[!UICONTROL Audience Data > Models]**&#x200B;中管理模型。 在高層面，工作流程程式包含下列項目：

* 選取要演算法評估的基線資料。 這包括[!UICONTROL trait]或[!UICONTROL segment]、時間範圍和[!UICONTROL data sources]（您已透過[!DNL Audience Manager]存取過的自己資料和第三方資料）。 在模型建立工作流程中，可以排除不想干預模型的[!UICONTROL traits]。
* 保存模型。 儲存後，演算法評估程式會自動執行。 但請注意，此程式最多可能需要7天才能完成。 [!DNL Audience Manager] 演算法完成後會傳送電子郵件給您，並提供建立 [!UICONTROL trait] 結果。
* 在[!UICONTROL Trait Builder]中建立演算法[!UICONTROL traits]。
* 在[!UICONTROL Segment Builder]中將[!UICONTROL traits]組合到[!UICONTROL segments]。
* 建立[!UICONTROL segment]資料並傳送至[!UICONTROL destination]。

## 疑難排解 {#troubleshooting}

我們會停用連續三次無法產生資料的任何[!UICONTROL Look-Alike Model]。 請注意，您無法在之後將模型的狀態設回「活動」(active)。 為確保模型產生資料，建議您從資料來源建立模型，且[!UICONTROL traits]足夠，以便累積資料。

## 了解[!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] 是專屬的演算法，用於自動 [!UICONTROL traits] 探索。它會將您目前[!UICONTROL traits]和[!UICONTROL segments]的[!UICONTROL trait]資料與您透過[!DNL Audience Manager]存取的所有其他第一方和第三方資料進行比較。 如需[!UICONTROL TraitWeight]演算法探索程式的說明，請參閱本節。

![](assets/algo_model.png)

以下步驟描述[!UICONTROL TraitWeight]評估過程。

### 步驟1:建立[!UICONTROL Trait]比較的基線

若要建立基線， [!UICONTROL TraitWeight]會在30、60或90天間隔內測量與對象相關聯的所有[!UICONTROL traits]。 接著，根據其頻率及其相關性對[!UICONTROL traits]進行排名。 頻率計數可測量通用性。 關聯會測量[!UICONTROL trait]僅出現在基線對象中的機率。 [!UICONTROL Traits] 通常會說這些字元顯示出高通用性，這是當與您在所選內容中發現的加權分數結合時，用來設 [!UICONTROL traits] 定加權分數的重要 [!UICONTROL data sources]特性。

### 步驟2:在[!UICONTROL Data Source]中找到相同的[!UICONTROL Traits]

建立基線進行比較後，演算法會在您選取的[!UICONTROL data sources]中尋找相同的[!UICONTROL traits]。 在此步驟中， [!UICONTROL TraitWeight]執行所有發現的[!UICONTROL traits]的頻率計數，並將它們與基線進行比較。 但是，與基線不同，不常見的[!UICONTROL traits]排名比較常出現的高。 所述稀有[!UICONTROL traits]表現出高度特異性。 [!UICONTROL TraitWeight] 將通用基準和不常見( [!UICONTROL traits] 高度特定)的組合評 [!UICONTROL data source] [!UICONTROL traits] 估為比兩個資料集共同 [!UICONTROL traits] 更具影響力或更可取。事實上，我們的模型可辨識這些大型且常見的[!UICONTROL traits]，且不會為具有高關聯性的資料集指派過多優先順序。 罕見[!UICONTROL traits]會獲得更高的優先順序，因為與[!UICONTROL traits]相比，它們更可能代表新的不重複用戶，而且整個板塊具有較高的通用性。

### 步驟3:指定權重

在此步驟中，[!UICONTROL TraitWeight]會根據影響或可取性來排名新發現的[!UICONTROL traits]。 重量等級是從0%到100%的百分比。 [!UICONTROL Traits] 接近100%的排名表示他們更像基線人口中的受眾。此外，重度加權[!UICONTROL traits]也很有價值，因為它們代表的是新的不重複使用者，其行為可能與您已建立的基準受眾類似。 請記住，[!UICONTROL TraitWeight]認為[!UICONTROL traits]在基線中具有較高的通用性，而在比較的資料源中具有較高的特異性，這比每個資料集中的[!UICONTROL traits]更有價值。

### 步驟4:計分使用者

所選[!UICONTROL data sources]中的每個用戶被賦予一個用戶分數，該分數等於該用戶配置檔案上具有影響力的[!UICONTROL traits]的所有權重的總和。 然後，將使用者分數標準化為0到100%。

### 步驟5:顯示和使用結果

[!DNL Audience Manager] 在中顯示加權模型結 [!UICONTROL Trait Builder]果。當您想要建立[!UICONTROL algorithmic trait]時， [!UICONTROL Trait Builder]可讓您根據演算法在資料執行期間產生的加權分數來建立[!UICONTROL traits]。 您可以選擇更高的準確度，僅限擁有非常高使用者分數的使用者，因此與基準對象非常類似，而非其餘對象。 如果您想觸及較大的對象（觸及），可以降低準確度。

### 步驟6:重新評估各處理週期[!UICONTROL Trait]的顯著性

[!UICONTROL TraitWeight]會定期根據[!UICONTROL trait]的母體大小和變化重新評估[!UICONTROL trait]的重要性。 符合該[!UICONTROL trait]資格的使用者人數會隨著時間而增加或減少，就會發生此情況。 這種行為在變大的特徵中最為明顯。 例如，假設演算法使用[!UICONTROL trait A]進行建模。 隨著[!UICONTROL trait A]母體的增加，[!UICONTROL TraitWeight]會重新評估該[!UICONTROL trait]的重要性，並可能指派較低的分數或忽略它。 在此情況下，[!UICONTROL trait A]太常或太大，無法對其人口發表任何顯著的評論。 [!UICONTROL TraitWeight]降低[!UICONTROL trait A]值後（或在模型中忽略），演算法特徵的母體會減少。 具影響力的[!UICONTROL traits]清單反映基線母體的演變。 使用具影響力的[!UICONTROL traits]清單來了解這些變更為何發生。

相關連結：

* [模型產生器](../../features/algorithmic-models/create-model.md)
* [精確度和觸及](../../features/traits/trait-accuracy-reach.md)

## 更新[!UICONTROL Look-Alike Models]和[!UICONTROL Traits] {#update-schedule}的排程

為新的或現有的[!UICONTROL algorithmic models]和[!UICONTROL traits]建立和更新計畫。

### [!UICONTROL Look-Alike Model] 建立和更新計畫

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
   <td colname="col2"> <p>若為新的或複製的[!UICONTROL相似模型]，建立程式每天會在下列位置執行一次： 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 東部標準時間下午5點（11月 — 3月） </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 美國東部夏令時間下午6點（3月 — 11月） </li> 
     </ul> </p> <p>在建立期限後建立或複製的模型，會在次日處理。 </p> <p>如果模型的首次執行未產生任何資料，則會第二次執行，即隔天。 如果第二次嘗試也未產生任何資料，則第三次嘗試，即第二天。 如果第三次嘗試也未產生任何資料，則模型將停止運行。 在這種情況下，我們將停用模型。 請參閱<a href="../../features/algorithmic-models/understanding-models.md#troubleshooting">相似模型疑難排解</a>中的更多資訊。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>更新模型</b> </td> 
   <td colname="col2"> <p>在理想條件下，現有模型會在工作日執行，至少每7天執行一次。 例如，如果您在星期一建立模型（截止日期），則最遲會在下星期一更新模型。 </p> <p>如果模型符合下列任一條件，則會重新執行： </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">上次運行不成功。 </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">在之前已成功執行，過去7天內完全未執行，而且模型至少附加一個作用中特徵。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] 建立和更新計畫

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
   <td colname="col2"> <p>特徵建立程式會每天執行，從星期一到星期五。 一般而言，新的演算法特徵會在48小時內出現在UI中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>更新特徵</b> </td> 
   <td colname="col2"> <p>現有特徵至少每7天更新一次，並依照模型更新排程進行。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模型清單視圖{#models-list-view}

清單檢視是可協助您建立、檢閱及管理模型的中央工作區。

[!UICONTROL Models]清單頁面包含有助於您：

* 建立新模型。
* 管理現有模型（編輯、暫停、刪除或原地複製）。
* 按名稱搜索模型。
* 使用任何給定模型建立[!UICONTROL algorithmic traits]。

## 模型摘要視圖{#models-summary-view}

摘要頁面會顯示模型詳細資訊，例如名稱、觸及/準確度、處理歷史記錄，以及從模型建立的[!UICONTROL traits]。 該頁面還包含可讓您建立和管理模型的設定。 按一下摘要清單中的模型名稱以查看其詳細資訊。

「模型摘要」(model summary)頁面包括以下部分。

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
   <td colname="col2"> <p>包括模型的基本資訊，如名稱和上次運行時間。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型觸及度和準確度</span> </p> </td> 
   <td colname="col2"> <p>顯示上次模型運行的<a href="../../features/traits/trait-accuracy-reach.md">準確度和達到</a>資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型處理歷史記錄</span> </p> </td> 
   <td colname="col2"> <p>顯示最近10次執行的處理日期和時間，以及這些執行上是否產生資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 具影響力的特徵</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">具影響力的特徵</span>表： </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 列出模型基線母體中最能代表的前50個具影響力的特徵。 </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">依照每個特徵的<span class="wintitle">相對權重</span>排名，對每個特徵進行排名。 <span class="wintitle">相對權數</span>會根據影響或可取性來排序新發現的特徵。 重量等級是從0%到100%的百分比。 特徵的排名接近100%，表示它們更像基線母體中的受眾。 請參閱<a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight">了解TraitWeight</a>。 </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">顯示每個特徵的30天不重複值和特徵母體總數。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 使用模型的特徵</span> </p> </td>
   <td colname="col2"> <p>根據選取的模型顯示演算法特徵清單。 按一下特徵名稱或特徵ID，以取得特徵的詳細資訊。 選取「使用模型建立新特徵」 <b><span class="uicontrol"> ，前往演算法特徵建立程式。</span></b> </p> <p>節標籤會根據模型名稱而改變。 例如，假設您建立模型，並將其命名為「模型A」。載入摘要頁面時，此區段的名稱會變更為「使用模型A</span>的特徵」。<span class="wintitle"> </span></p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [目的地](../../features/destinations/destinations.md)
* [特徵](../../features/traits/trait-details-page.md)
* [區段](../../features/segments/segments-purpose.md)

