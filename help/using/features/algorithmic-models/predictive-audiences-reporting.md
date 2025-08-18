---
description: 預測客群可協助您運用資料科學，將未知的客群即時分類為不重複角色。
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: 預測受眾報表
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 2%

---

# 預測受眾報表

儲存[!UICONTROL Predictive Audiences]模型後，Audience Manager會開始對其進行訓練。 在數小時內，計算模型將開始分析[資料收集伺服器](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)上的對象。 報告功能將於次日提供。

若要檢視[!UICONTROL Predictive Audiences]分類的結果，請前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，然後按一下清單中的模型。

使用左側的篩選選項來搜尋模型名稱或根據模型型別篩選結果。

![預測對象 — 篩選器](assets/predictive-audiences-filter-models.png)

模型表格會顯示下列資訊：

* **[!UICONTROL ID]**：模式ID會唯一識別Audience Manager帳戶中的每個模式；
* **[!UICONTROL Name]**：您在模型建立步驟中提供的名稱；
* **[!UICONTROL Description]**：您在模型建立步驟中提供的說明；
* **[!UICONTROL Model Type]**：每個模型的型別（[!UICONTROL Look-Alike Modeling]或[!UICONTROL Predictive Audiences]）；
* **[!UICONTROL Status]**：每個模型的狀態：
   * **[!UICONTROL Pending]**：模型正在初始化，很快就會開始產生結果；
   * **[!UICONTROL Active]**：模型已成功執行並產生結果；
   * **[!UICONTROL Warning]**：模型無法產生結果，因為資料不足（也就是基線母體低，使用者設定檔不豐富）；
   * **[!UICONTROL Error]**：模型無法執行。 請聯絡您的Adobe代表。

## 模型概觀報表{#model-report}

選擇模型後，其報告頁面即會載入。 在頁面頂端，您可以根據1天的即時實現，檢視前5個最大的預測區段，模型已依此分類您的目標對象。 **[!UICONTROL Other]**&#x200B;類別包含其他角色，這些角色未包含在前5個最大的預測區段中。

Audience Manager會同時顯示您[!UICONTROL Predictive Audiences]的彩色編碼環圈圖和時間軸圖表。

按一下頁面頂端的角色標籤可在圖表和圖形中新增或移除角色。

環形圖以人物為基礎顯示目標對象的劃分，而圖形則顯示過去6天預測區段的1天即時母體趨勢。

如果模型狀態為[!UICONTROL Pending]、[!UICONTROL Warning]或[!UICONTROL Error]，則會顯示模型狀態而非圖形。

![smart-persona-report](assets/predictive-audiences-report.png)

報告表格顯示每個[!UICONTROL Predictive Audiences]區段的下列資訊。

1. **[!UICONTROL SEGMENT ID]**：與每個角色相關聯之自動建立的區段的區段識別碼；
1. **[!UICONTROL NAME]**：角色名稱；
1. **[!UICONTROL STATUS]**： [!UICONTROL Predictive Audiences]區段的狀態：
   * **[!UICONTROL Succeeded]**：使用者正在分類至此區段；
   * **[!UICONTROL Pending]**：區段仍在初始化中；
   * **[!UICONTROL Insufficient Training Data]**：由於資料不足，使用者未分類到此區段。 總基線母體太低，提供的資料不足以供學習。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**：過去24小時內每個角色的區段實現次數。
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**：每個角色在過去24小時內的區段實現在模型母體總數中的百分比。

## 具影響力的特徵{#influential-traits}

[!UICONTROL Influential Traits]是[!UICONTROL Predictive Audiences]演演算法發現為判斷訪客角色分類最強之預測值的特徵。

其符號會指出特徵的存在會增加(+)或減少(-)使用者屬於所選角色的可能性。

若要檢視所有角色具有影響力的特徵，請按一下[!UICONTROL View All Influential Traits]。

[!UICONTROL Influential Traits]視窗會針對所選模型中的每個角色，顯示下列資訊：

![具影響力的特徵](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**：所選角色每個具影響力之特徵的特徵ID；
1. **[!UICONTROL NAME]**：所選角色每個具影響力之特徵的名稱；
1. **[!UICONTROL DESCRIPTION]**：所選角色每個具影響力之特徵的說明；
1. **[!UICONTROL WEIGHT]**：所選角色每個具影響力特徵的權重。 [!UICONTROL Influential Traits]預設會依權重遞減排序。  權重值代表其預測能力。 此符號代表特徵的存在會增加(+)或減少(-)屬於某個角色的可能性。
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**：所選角色每個具影響力之特徵在過去30天內的不重複特徵實現次數。
