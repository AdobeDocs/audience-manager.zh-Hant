---
description: 建立並管理相似模型中使用的特徵或區段。
keywords: relative weight, lookalike
seo-description: 建立並管理相似模型中使用的特徵或區段。
seo-title: 關於相似模型
solution: Audience Manager
title: 關於相似模型
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1590'
ht-degree: 1%

---


# 瞭解[!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## 查找[!UICONTROL Look-Alike Modeling] {#find-new-users}的新用戶

[!UICONTROL Look-Alike Modeling] 協助您透過自動化資料分析，發掘新的獨特受眾。當您選擇[!UICONTROL trait]或[!UICONTROL segment]、時間間隔，以及第一方和第三方[!UICONTROL data sources]時，流程就會開始。 您的選擇為演算模型提供輸入。 當分析程式執行時，它會根據所選人口的共用特性，尋找符合資格的使用者。 完成時，此資料可在[特徵產生器](../../features/traits/about-trait-builder.md)中取用，您可在此使用它根據[準確度建立特徵並達到](../../features/traits/trait-accuracy-reach.md)。 此外，您還可以建立結合演算特性與[!UICONTROL rules-based traits]的區段，並新增其他使用[!DNL Boolean]運算式與比較運算子的資格要求。 [!UICONTROL Look-Alike Modeling] 提供您從所有可用特徵資料擷取值的動態方式。

## 優勢 {#advantages}

使用[!UICONTROL Look-Alike Modeling]的主要優點包括：

* **資料正確性：** 演算法會定期執行，有助於保持結果的最新性和相關性。
* **自動化：** 您不需要管理大量的靜態規則。演算法會為您尋找受眾。
* **節省時間並減少工作量：使用** 我們的模型建立程式，您不必猜測哪些 [!UICONTROL traits]功[!UICONTROL segments] 能可行，或花時間在促銷活動上，即可發現新的受眾。模型可以為您執行此操作。
* **可靠性：** 模型可與伺服器端的發現和資格認定程式搭配使用，以評估您自己的資料和您可存取的所選第三方資料。這表示您不必查看網站上的訪客，即可讓他們符合某個特徵的資格。

## 工作流程 {#workflow}

在&#x200B;**[!UICONTROL Audience Data > Models]**&#x200B;中管理模型。 在高層，工作流進程涉及以下內容：

* 選取您要演算法評估的基線資料。 這包括[!UICONTROL trait]或[!UICONTROL segment]、時間範圍和[!UICONTROL data sources]（您自己的資料和您已透過[!DNL Audience Manager]存取的第三方資料）。 在模型建立工作流中，可以排除不想干擾模型的[!UICONTROL traits]。
* 保存模型。 儲存後，演算法評估程式就會自動執行。 但請注意，此程式最長需要7天才能完成。 [!DNL Audience Manager] 演算法完成且結果可供建立時，會傳送電子郵件給 [!UICONTROL trait] 您。
* 在[!UICONTROL Trait Builder]中建立演算法[!UICONTROL traits]。
* 在[!UICONTROL Segment Builder]中將[!UICONTROL traits]組合到[!UICONTROL segments]。
* 建立並傳送[!UICONTROL segment]資料至[!UICONTROL destination]。

## 疑難排解 {#troubleshooting}

我們會停用任何無法產生連續三個執行之資料的[!UICONTROL Look-Alike Model]。 請注意，不能將模型的狀態設定回活動狀態。 為確保您的模型產生資料，我們建議您從資料來源建立具備[!UICONTROL traits]的模型，以累積資料。

## 瞭解[!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] 是專為自動發現新功能而設計的專 [!UICONTROL traits] 屬演算法。它會將您目前[!UICONTROL traits]和[!UICONTROL segments]的[!UICONTROL trait]資料與您可透過[!DNL Audience Manager]存取的所有其他第一方和第三方資料進行比較。 有關[!UICONTROL TraitWeight]演算法發現過程的說明，請參閱本節。

![](assets/algo_model.png)

以下步驟說明[!UICONTROL TraitWeight]評估過程。

### 步驟1:建立[!UICONTROL Trait]比較的基準

若要建立基線，[!UICONTROL TraitWeight]會測量與觀眾相關的所有[!UICONTROL traits]，間隔為30、60或90天。 接著，根據其頻率和相關性對[!UICONTROL traits]進行排序。 頻率計數會測量通用性。 關聯會測量[!UICONTROL trait]僅出現在基準讀者中的可能性。 [!UICONTROL Traits] 通常會顯示高通用性，這是用來設定加權分數的重要特性，並結合在您選取的 [!UICONTROL traits] 項目中發現 [!UICONTROL data sources]。

### 步驟2:在[!UICONTROL Data Source]中尋找相同的[!UICONTROL Traits]

在建立基準以進行比較後，演算法會在您選取的[!UICONTROL data sources]中尋找相同的[!UICONTROL traits]。 在此步驟中，[!UICONTROL TraitWeight]會執行所有已發現[!UICONTROL traits]的頻率計數，並將它們與基線進行比較。 但是，與基線不同，不常見的[!UICONTROL traits]排名高於較常出現的排名。 所述稀有[!UICONTROL traits]顯示出高度特異性。 [!UICONTROL TraitWeight] 評估共同基準和不 [!UICONTROL traits] 常見（高度特定）的組 [!UICONTROL data source] [!UICONTROL traits] 合比兩個資料集 [!UICONTROL traits] 的共同更有影響力或更可取。事實上，我們的模型會辨識這些大型且常見的[!UICONTROL traits]，而且不會指派過多的優先順序給關聯性較高的資料集。 少有的[!UICONTROL traits]會獲得更高的優先順序，因為它們代表新的獨特用戶的可能性比[!UICONTROL traits]更大，而且在整個主板上具有高度的通用性。

### 步驟3:指定權重

在此步驟中，[!UICONTROL TraitWeight]會依影響或期望順序排列新發現的[!UICONTROL traits]。 重量級數是從0%到100%的百分比。 [!UICONTROL Traits] 排名接近100%表示他們更像您基準人口中的觀眾。此外，重量[!UICONTROL traits]的重要性在於它們代表新的獨特使用者，其行為可能與您現有的基準讀者類似。 請記住，[!UICONTROL TraitWeight]認為[!UICONTROL traits]在基線中具有高通用性，而在比較的資料源中具有高特異性，這比每個資料集中的[!UICONTROL traits]更有價值。

### 步驟4:計分使用者

選取的[!UICONTROL data sources]中的每個使用者會獲得一個使用者分數，該分數等於該使用者描述檔上有影響力的[!UICONTROL traits]所有權重的總和。 然後，將用戶分數標準化為0到100%。

### 步驟5:顯示並處理結果

[!DNL Audience Manager] 在中顯示加權模型結果 [!UICONTROL Trait Builder]。當您要建立[!UICONTROL algorithmic trait]時，[!UICONTROL Trait Builder]可讓您根據演算法在資料執行期間產生的加權分數來建立[!UICONTROL traits]。 您可以選擇更高的準確度，以僅限符合使用者分數極高且因此與基準讀者非常相似的使用者，而非其他對象。 如果您想要觸及到更廣的觀眾（觸及），則可降低精確度。

### 步驟6:重新評估處理週期中[!UICONTROL Trait]的重要性

[!UICONTROL TraitWeight]會定期根據[!UICONTROL trait]的人口大小和變化重新評估[!UICONTROL trait]的重要性。 當符合該[!UICONTROL trait]資格的使用者人數隨著時間增加或減少時，就會發生此情況。 這種行為在變大的特徵中最為明顯。 例如，假設演算法使用[!UICONTROL trait A]進行建模。 隨著[!UICONTROL trait A]的人口增加，[!UICONTROL TraitWeight]會重新評估該[!UICONTROL trait]的重要性，並可指派較低的分數或忽略它。 在此情況下，[!UICONTROL trait A]太常見或太大，無法對其人口發表任何顯著評論。 在[!UICONTROL TraitWeight]降低[!UICONTROL trait A]的值（或在模型中忽略它）後，演算法特徵的人口數會減少。 影響[!UICONTROL traits]的清單反映了基線人口的演變。 使用有影響力的[!UICONTROL traits]清單，瞭解發生這些變更的原因。

相關連結：

* [模型產生器](../../features/algorithmic-models/create-model.md)
* [精確度和觸及](../../features/traits/trait-accuracy-reach.md)

## 更新[!UICONTROL Look-Alike Models]和[!UICONTROL Traits] {#update-schedule}的排程

建立和更新新或現有[!UICONTROL algorithmic models]和[!UICONTROL traits]的排程。

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
   <td colname="col1"> <b>建立或克隆模型</b> </td>
   <td colname="col2"> <p>對於新的或克隆的[!UICONTROL相似模型]，建立過程每天運行一次，網址為： 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 東部時間下午5點（11月- 3月） </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 美國東部夏令時間下午6點（3月- 11月） </li> 
     </ul> </p> <p>在建立截止日期之後構建或克隆的模型將在第二天進行處理。 </p> <p>如果模型的首次運行未生成任何資料，則它將在次日運行第二次。 如果第二次嘗試也未產生任何資料，則第三次嘗試，即第二天。 如果第三次嘗試也未產生任何資料，模型將停止執行。 在這種情況下，我們會停用模型。 請參閱<a href="../../features/algorithmic-models/understanding-models.md#troubleshooting">類似機型疑難排解</a>中的更多資訊。 </p> </td>
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
   <td colname="col2"> <p>特徵建立程式會每天執行，週一到週五。 通常，新演算法特徵會在48小時內出現在UI中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>更新特徵</b> </td> 
   <td colname="col2"> <p>現有特徵至少每7天更新一次，並依照模型更新的排程進行。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模型清單視圖{#models-list-view}

清單檢視是一個集中工作區，可協助您建立、檢視及管理模型。

[!UICONTROL Models]清單頁面包含可協助您：

* 建立新模型。
* 管理現有模型（編輯、暫停、刪除或仿製）。
* 依名稱搜尋模型。
* 使用任何給定型號建立[!UICONTROL algorithmic traits]。

## 模型摘要視圖{#models-summary-view}

摘要頁面會顯示模型詳細資訊，例如名稱、觸及／準確度、處理歷史記錄，以及從模型建立的[!UICONTROL traits]。 該頁還包含可讓您建立和管理模型的設定。 按一下摘要清單中的模型名稱以查看其詳細資訊。

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
   <td colname="col2"> <p>顯示上次模型運行的<a href="../../features/traits/trait-accuracy-reach.md">準確度和</a>資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型處理歷史記錄</span> </p> </td> 
   <td colname="col2"> <p>顯示最近10次執行的處理日期和時間，以及這些執行上是否產生資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 影響力特徵</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">影響特徵</span>表： </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 列出模型基線人口中最具影響力的50項最佳特徵。 </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">依其<span class="wintitle">相對權重</span>排名來排名每個特徵。 <span class="wintitle">相對權重</span>會依影響或可取性排序新發現的特徵。 重量級數是從0%到100%的百分比。 排名接近100%的特徵意味著它們更像您基線人口中的受眾。 請參閱<a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight">瞭解TraitWeight</a>。 </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">顯示每個特徵的30天獨特值和特徵總人口。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 使用模型的特徵</span> </p> </td>
   <td colname="col2"> <p>顯示根據所選模型的演算法特徵清單。 按一下特徵名稱或特徵ID，以取得特徵的詳細資訊。 選取「使用Model<b><span class="uicontrol">建立新特徵」，以前往演算法特徵建立程式。</span></b> </p> <p>截面標籤會根據模型名稱而改變。 例如，假設您建立模型並將其命名為模型A。載入摘要頁面時，此區段的名稱會變更為「使用模型A<span class="wintitle">的特徵」。</span> </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [目的地](../../features/destinations/destinations.md)
>* [特徵](../../features/traits/trait-details-page.md)
>* [區段](../../features/segments/segments-purpose.md)

