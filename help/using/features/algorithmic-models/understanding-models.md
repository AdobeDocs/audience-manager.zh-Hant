---
description: 構建和管理在外觀相似建模中使用的特徵或段。
keywords: 相對重量，長相相似
seo-description: Build and manage the traits or segments used in look-alike modeling.
seo-title: About Look-Alike Modeling
solution: Audience Manager
title: 關於外觀相似建模
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1576'
ht-degree: 1%

---

# 理解 [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## 查找新用戶 [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] 通過自動資料分析幫助您發現新的、獨特的受眾。 當您選擇 [!UICONTROL trait] 或 [!UICONTROL segment]、時間間隔，以及第一和第三方 [!UICONTROL data sources]。 你的選擇為算法模型提供輸入。 當分析進程運行時，它根據所選人口中的共用特徵查找合格用戶。 完成後，此資料可在 [特性生成器](../../features/traits/about-trait-builder.md) 你可以用它來建立 [精確到](../../features/traits/trait-accuracy-reach.md)。 此外，您還可以構建將算法特性與 [!UICONTROL rules-based traits] 並添加其他資格要求 [!DNL Boolean] 表達式和比較運算子。 [!UICONTROL Look-Alike Modeling] 為您提供了從所有可用特性資料中提取值的動態方法。

## 優勢 {#advantages}

使用 [!UICONTROL Look-Alike Modeling] 包括：

* **資料準確性：** 算法定期運行，有助於保持結果的最新和相關性。
* **自動化：** 您不必管理大量靜態規則。 算法會為你找到觀眾。
* **節省時間並減少工作量：** 通過我們的建模過程，你不必猜測 [!UICONTROL traits]/[!UICONTROL segments] 可能會在活動上工作或花費時間來發現新的受眾。 模型可以為您執行此操作。
* **可靠性：** 建模與伺服器端的發現和鑑定過程配合使用，這些過程評估您自己的資料和您有權訪問的選定第三方資料。 這意味著您不必在網站上看到訪問者，就可以確認他們的某種特性。

## 工作流程 {#workflow}

您在 **[!UICONTROL Audience Data > Models]**。 在高級別上，工作流進程涉及以下內容：

* 選擇希望算法計算的基線資料。 這包括 [!UICONTROL trait] 或 [!UICONTROL segment]、時間範圍和 [!UICONTROL data sources] (您自己的資料和您已有權訪問的第三方資料 [!DNL Audience Manager])。 在模型建立工作流中，可以排除 [!UICONTROL traits] 你不想干涉你的模型。
* 保存模型。 一旦保存，算法評估過程將自動運行。 但請注意，此過程可能需要7天才能完成。 [!DNL Audience Manager] 算法完成後，結果可供使用時向您發送電子郵件 [!UICONTROL trait] 建立。
* 生成算法 [!UICONTROL traits] 在 [!UICONTROL Trait Builder]。
* 組合 [!UICONTROL traits] 入 [!UICONTROL segments] 在 [!UICONTROL Segment Builder]。
* 建立和發送 [!UICONTROL segment] 資料到 [!UICONTROL destination]。

## 疑難排解 {#troubleshooting}

我們停用任何 [!UICONTROL Look-Alike Model] 連續三次運行無法生成資料。 請注意，以後不能將模型的狀態設定回活動狀態。 為確保模型生成資料，我們建議您使用足夠的資料源構建模型 [!UICONTROL traits] 從中積累資料。

## 理解 [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] 是專為發現 [!UICONTROL traits] 的下界。 它比較 [!UICONTROL trait] 資料 [!UICONTROL traits] 和 [!UICONTROL segments] 與您有權訪問的所有其他第一和第三方資料 [!DNL Audience Manager]。 請參閱本節，瞭解 [!UICONTROL TraitWeight] 算法發現過程。

![](assets/algo_model.png)

以下步驟介紹 [!UICONTROL TraitWeight] 評估過程。

### 步驟1:生成基線 [!UICONTROL Trait] 比較

要構建基線， [!UICONTROL TraitWeight] 測量所有 [!UICONTROL traits] 在30、60或90天間隔內與受眾關聯。 接下來，它 [!UICONTROL traits] 根據它們的頻率和相關性。 頻率計數度量通用性。 關聯度量 [!UICONTROL trait] 只出現在基線觀眾中。 [!UICONTROL Traits] 通常顯示的是高通用性，這是在與 [!UICONTROL traits] 已發現 [!UICONTROL data sources]。

### 步驟2:查找相同 [!UICONTROL Traits] 的 [!UICONTROL Data Source]

建立比較基線後，算法會查找相同的 [!UICONTROL traits] 在 [!UICONTROL data sources]。 在這一步， [!UICONTROL TraitWeight] 執行所有已發現的頻率計數 [!UICONTROL traits] 並與基線進行比較。 但是，與基線不同， [!UICONTROL traits] 排名比那些更頻繁的排名高。 稀有 [!UICONTROL traits] 都顯示出高度的特異性。 [!UICONTROL TraitWeight] 評估共同基線組合 [!UICONTROL traits] 不常見（高度特定） [!UICONTROL data source] [!UICONTROL traits] 比 [!UICONTROL traits] 兩個資料集通用。 事實上，我們的模型識別了這些 [!UICONTROL traits] 並且不會為關聯度高的資料集指定過多優先順序。 稀有 [!UICONTROL traits] 獲得更高的優先順序，因為他們更可能代表新的、獨特的用戶，而不是 [!UICONTROL traits] 通用性強。

### 第3步：分配權重

在這一步， [!UICONTROL TraitWeight] 新發現的 [!UICONTROL traits] 影響力或慾望。 重量比是0%到100%的百分比。 [!UICONTROL Traits] 排名接近100%意味著他們更像你的基線人口中的觀眾 此外， [!UICONTROL traits] 非常有價值，因為它們代表的是新的、獨特的用戶，他們的行為可能與已建立的基線受眾類似。 記住， [!UICONTROL TraitWeight] 考慮 [!UICONTROL traits] 基線通用性強，比較資料源的特異性高，比 [!UICONTROL traits] 在每個資料集中都很常見。

### 第4步：評分用戶

選定的每個用戶 [!UICONTROL data sources] 給出一個用戶分數，該分數等於所有影響力權重之和 [!UICONTROL traits] 用戶的個人資料。 然後，將用戶分數標準化為0%到100%。

### 第5步：顯示和處理結果

[!DNL Audience Manager] 顯示加權模型結果 [!UICONTROL Trait Builder]。 當您要構建 [!UICONTROL algorithmic trait]。 [!UICONTROL Trait Builder] 允許建立 [!UICONTROL traits] 根據算法在資料運行期間生成的加權得分。 您可以選擇更高的準確性，以僅限定用戶分數非常高的用戶，因此與基線受眾非常相似，而不是其他受眾。 如果想接觸更多的受眾（接觸），可以降低準確性。

### 步驟6:重新評價 [!UICONTROL Trait] 跨處理週期

定期， [!UICONTROL TraitWeight] 重新評估 [!UICONTROL trait] 根據人口規模和變化 [!UICONTROL trait]。 當符合此條件的用戶數時，就會發生這種情況 [!UICONTROL trait] 隨著時間的推移而增加或減少。 這種行為在那些變得非常大的特質中表現得最為明顯。 例如，假設算法使用 [!UICONTROL trait A] 為建模。 作為 [!UICONTROL trait A] 增加， [!UICONTROL TraitWeight] 重新評估其重要性 [!UICONTROL trait] 或者忽略分數。 在這個例子中， [!UICONTROL trait A] 太常見或太大，無法對其人口做出任何重大的評價。 之後 [!UICONTROL TraitWeight] 減少 [!UICONTROL trait A] （或者在模型中忽略它），算法特徵的數量減少。 影響力清單 [!UICONTROL traits] 反映了基線人口的演變。 使用有影響力的 [!UICONTROL traits] 來理解這些變化的原因。

相關連結：

* [模型生成器](../../features/algorithmic-models/create-model.md)
* [精確度和觸及](../../features/traits/trait-accuracy-reach.md)

## 更新計畫 [!UICONTROL Look-Alike Models] 和 [!UICONTROL Traits] {#update-schedule}

建立和更新新計畫或現有計畫 [!UICONTROL algorithmic models] 和 [!UICONTROL traits]。

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
   <td colname="col2"> <p>對於新的或克隆的 [!UICONTROL Look-Alike Models]，建立過程每天運行一次，時間： 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 東部時間下午5點（11月 — 3月） </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 美國東部夏令時下午6點（3月–11月） </li> 
     </ul> </p> <p>在建立截止日期後生成或克隆的模型將在第二天進行處理。 </p> <p>如果模型的第一次運行不生成任何資料，則將在第二天再次運行。 如果第二次嘗試也未生成任何資料，則第三次嘗試，即第二天。 如果第三次嘗試也未生成任何資料，則模型將停止運行。 在這種情況下，我們會停用模型。 查看更多資訊 <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> 對外觀相似的模型進行故障排除</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>更新模型</b> </td> 
   <td colname="col2"> <p>在理想條件下，現有模型在工作日運行，至少每7天運行一次。 例如，如果在星期一建立模型（截止時間），則最遲會在下星期一更新模型。 </p> <p>如果模型滿足以下任一條件，將重新運行該模型： </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">上次運行未成功。 </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">它在運行之前已成功運行，過去7天裡一直未運行。模型至少附有一個活動特性。 </li>
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
   <td colname="col1"> <b>建立特性</b> </td> 
   <td colname="col2"> <p>特質創造過程每天，從星期一到星期五。 通常，新算法特徵在48小時內出現在用戶介面上。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>更新特性</b> </td> 
   <td colname="col2"> <p>現有特徵至少每7天更新一次，並遵循模型更新的計畫。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模型清單視圖 {#models-list-view}

清單視圖是一個中心工作區，可幫助您建立、查看和管理模型。

的 [!UICONTROL Models] 清單頁包含有助於您的功能和工具：

* 建立新模型。
* 管理現有模型（編輯、暫停、刪除或克隆）。
* 按名稱搜索模型。
* 建立 [!UICONTROL algorithmic traits] 使用任何給定模型。

## 模型摘要視圖 {#models-summary-view}

摘要頁面顯示模型詳細資訊，如名稱、到達/準確度、處理歷史記錄和 [!UICONTROL traits] 從模型建立。 該頁還包括允許您建立和管理模型的設定。 按一下摘要清單中的模型名稱以查看其詳細資訊。

模型摘要頁面包括以下部分。

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
   <td colname="col2"> <p>包括有關模型的基本資訊，如模型名稱和上次運行時間。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型的距離和精度</span> </p> </td> 
   <td colname="col2"> <p>顯示 <a href="../../features/traits/trait-accuracy-reach.md"> 精確到</a> 上次模型運行的資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型處理歷史記錄</span> </p> </td> 
   <td colname="col2"> <p>顯示最近10次運行的處理日期和時間以及這些運行是否生成了資料。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 影響性</span> </p> </td> 
   <td colname="col2"> <p>的 <span class="wintitle"> 影響性</span> 表： </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 列出模型基線人口中最能代表的前50個影響力特徵。 </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">將每個特徵按其順序排序 <span class="wintitle"> 相對權重</span> 排名。 的 <span class="wintitle"> 相對權重</span> 根據影響力或可取性對新發現的特徵進行分類。 重量比是0%到100%的百分比。 排名接近100%的特性意味著他們更像你的基本群體中的觀眾 請參閱 <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> 瞭解特質權重</a>。 </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">顯示30天單位和每個特徵的總特徵群體。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 使用模型的特徵</span> </p> </td>
   <td colname="col2"> <p>顯示基於所選模型的算法特性清單。 按一下特徵名稱或特徵ID以瞭解有關特徵的詳細資訊。 選擇 <b><span class="uicontrol"> 使用模型建立新特性</span></b> 進入算法特徵創造過程。 </p> <p>截面標籤會根據模型的名稱進行更改。 例如，假設您建立模型並將其命名為模型A。載入摘要頁面時，此節的名稱將更改為 <span class="wintitle"> 使用模型A的特徵</span>。 </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [目的地](../../features/destinations/destinations.md)
>* [特徵](../../features/traits/trait-details-page.md)
>* [區段](../../features/segments/segments-purpose.md)

