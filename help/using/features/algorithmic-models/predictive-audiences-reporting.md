---
description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: 預測受眾報表
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---

# 預測受眾報表

保存後 [!UICONTROL Predictive Audiences] 模型，Audience Manager開始訓練它。 在幾小時內，計算模型將開始分析 [資料收集伺服器](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)。 報告將在第二天提供。

查看您的 [!UICONTROL Predictive Audiences] 分類，轉到 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，然後按一下清單中的模型。

使用左側的篩選選項搜索模型名稱或根據模型類型篩選結果。

![預測受眾 — 篩選](assets/predictive-audiences-filter-models.png)

「模型」(models)表格顯示以下資訊：

* **[!UICONTROL ID]**:模型ID唯一標識您的Audience Manager帳戶中的每個模型；
* **[!UICONTROL Name]**:在模型建立步驟中提供的名稱；
* **[!UICONTROL Description]**:在模型建立步驟中提供的說明；
* **[!UICONTROL Model Type]**:每個模型的類型([!UICONTROL Look-Alike Modeling] 或 [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**:每個模型的狀態：
   * **[!UICONTROL Pending]**:模型正在初始化，很快將開始產生結果；
   * **[!UICONTROL Active]**:模型運行成功，取得了成效；
   * **[!UICONTROL Warning]**:由於資料不足（即基線數量低，用戶配置檔案不豐富），模型未能產生結果；
   * **[!UICONTROL Error]**:模型無法運行。 您應聯繫Adobe代表。

## 模型概述報告{#model-report}

選擇模型後，其報告頁將載入。 在頁面頂部，您可以看到前5個最大的預測段，這些預測段基於1天的即時實現，即模型已按目標受眾分類。 的 **[!UICONTROL Other]** 類別包括其餘人員，這些人員未包括在前5個最大預測段中。

Audience Manager顯示顏色編碼的環形圖和時間軸圖 [!UICONTROL Predictive Audiences]。

按一下頁面頂部的角色頁籤會在圖表和圖形中添加或刪除它們。

甜甜圈圖顯示了目標受眾基於個人的細分，而圖表顯示了過去6天預測段的1天即時人口趨勢。

如果模型狀態為 [!UICONTROL Pending]。 [!UICONTROL Warning]或 [!UICONTROL Error]，將顯示模型狀態，而不顯示圖形。

![智慧人物報告](assets/predictive-audiences-report.png)

報表表顯示了每個 [!UICONTROL Predictive Audiences] 段。

1. **[!UICONTROL SEGMENT ID]**:與每個角色相關聯的自動建立段的段ID;
1. **[!UICONTROL NAME]**:姓名；
1. **[!UICONTROL STATUS]**:的狀態 [!UICONTROL Predictive Audiences] 分部：
   * **[!UICONTROL Succeeded]**:用戶被划入此分類；
   * **[!UICONTROL Pending]**:該段仍在初始化；
   * **[!UICONTROL Insufficient Training Data]**:由於資料不足，用戶未被分類到此段。 總基線人口太低，無法提供足夠的資料來學習。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**:過去24小時內每個角色的段實現數。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**:過去24小時內每個角色的細分佔模型總人口的百分比。

## 影響性{#influential-traits}

[!UICONTROL Influential Traits] 是那些 [!UICONTROL Predictive Audiences] 算法被發現是確定訪問者個人分類的最強預測器。

它們的符號指示特徵的存在是增加(+)還是減少(-)用戶屬於所選角色的可能性。

要查看所有角色的影響特徵，請按一下 [!UICONTROL View All Influential Traits]。

的 [!UICONTROL Influential Traits] 窗口顯示選定模型中每個角色的以下資訊：

![影響性](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**:對選定的人物個性，每個影響特徵的特徵ID;
1. **[!UICONTROL NAME]**:選定角色的每個影響因素的名稱；
1. **[!UICONTROL DESCRIPTION]**:對所選人物的每個影響特徵的描述；
1. **[!UICONTROL WEIGHT]**:所選角色的每個影響因素的權重。 [!UICONTROL Influential Traits] 預設按重量按降序排序。  權重的值表示其預測能力。 該符號指示特徵的存在是增加(+)還是降低(-)屬於個人的可能性。
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**:在過去30天中，每個選定角色的特性都實現了獨特的特性。
