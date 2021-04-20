---
description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-title: 預測受眾報表
solution: Audience Manager
title: 預測受眾報表
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
translation-type: tm+mt
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 6%

---

# 預測受眾報表

保存[!UICONTROL Predictive Audiences]模型後，Audience Manager開始進行培訓。 在幾小時內，計算模型將開始分析[資料收集伺服器](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)上的觀眾。 報告將於次日提供。

若要查看[!UICONTROL Predictive Audiences]分類的結果，請前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，然後在清單中按一下您的模型。

使用左側的篩選選項來搜尋模型名稱或根據模型類型篩選結果。

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

模型表格顯示以下資訊：

* **[!UICONTROL ID]**:模型ID可唯一識別Audience Manager帳戶中的每個模型；
* **[!UICONTROL Name]**:在模型建立步驟中提供的名稱；
* **[!UICONTROL Description]**:在模型建立步驟中提供的說明；
* **[!UICONTROL Model Type]**:每個模型([!UICONTROL Look-Alike Modeling] 或 [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**:每個模型的狀態：
   * **[!UICONTROL Pending]**:模型正在初始化，很快就會開始產生結果；
   * **[!UICONTROL Active]**:模型運行成功，取得了成效；
   * **[!UICONTROL Warning]**:由於資料不足（即基線數量低，用戶配置檔案不豐富），模型無法產生結果；
   * **[!UICONTROL Error]**:模型無法運行。您應聯絡Adobe代表。

## 模型概述報告{#model-report}

在您選擇模型後，其報表頁面將會載入。 在頁面頂端，您可以根據1天的即時實現，看到前5大預測區段，即模型已依據分類目標對象。 **[!UICONTROL Other]**&#x200B;類別包含其餘角色，這些角色未包含在前5大預測性群體中。

Audience Manager會為[!UICONTROL Predictive Audiences]顯示彩色編碼環圈圖和時間軸圖。

按一下頁面頂端的角色標籤，會從圖表和圖形中新增或移除角色標籤。

環圈圖顯示您目標對象的個人化劃分，而圖表則顯示過去6天預測區段的1天即時人口趨勢。

如果模型狀態為[!UICONTROL Pending]、[!UICONTROL Warning]或[!UICONTROL Error]，則會顯示模型狀態，而非圖形。

![智慧型人格報告](assets/predictive-audiences-report.png)

報表表格顯示每個[!UICONTROL Predictive Audiences]區段的下列資訊。

1. **[!UICONTROL SEGMENT ID]**:與每個角色關聯的自動建立區段的區段ID;
1. **[!UICONTROL NAME]**:人名；
1. **[!UICONTROL STATUS]**:區段的狀 [!UICONTROL Predictive Audiences] 態：
   * **[!UICONTROL Succeeded]**:使用者被分類至此區段；
   * **[!UICONTROL Pending]**:區段仍在初始化中；
   * **[!UICONTROL Insufficient Training Data]**:由於資料不足，使用者未分類至此區段。總基線人口太低，無法提供足夠的資料供您學習。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**:過去24小時內每個角色的區段實現數。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**:過去24小時內，每個角色的細分實現佔模型總人口的百分比。

## 影響特徵{#influential-traits}

[!UICONTROL Influential Traits] 是演算法發 [!UICONTROL Predictive Audiences] 現為最強的預測器，用以判斷訪客的個人分類。

其符號會指出特徵的存在會增加(+)或降低(-)使用者屬於所選角色的可能性。

若要檢視您所有角色的影響力特徵，請按一下[!UICONTROL View All Influential Traits]。

[!UICONTROL Influential Traits]窗口顯示選定模型中每個角色的以下資訊：

![影響特徵](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**:選定人物每個影響特徵的特徵ID;
1. **[!UICONTROL NAME]**:選定角色的每個影響特徵的名稱；
1. **[!UICONTROL DESCRIPTION]**:描述選定人物的每個影響特徵；
1. **[!UICONTROL WEIGHT]**:所選角色的每個影響特徵的權重。[!UICONTROL Influential Traits] 依預設依權重排序，依遞減順序排列。權重值表示其預測能力。 符號會指出特徵的存在會增加(+)或降低(-)屬於個人的可能性。
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**:過去30天內，所選角色中每個影響特徵的獨特特徵實現次數。
