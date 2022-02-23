---
description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Managing Predictive Audiences
solution: Audience Manager
title: 預測受眾快速入門
feature: Algorithmic Models
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 4%

---

# 預測受眾快速入門 {#predictive-audiences-getting-started}

>[!IMPORTANT]
>本文包含旨在指導您完成此功能的設定和使用的產品文檔。 這裡沒有法律建議。 請咨詢您自己的法律顧問以獲得法律指導。

## 建立預測受眾模型 {#create-predictive-audiences}

建立之前 [!UICONTROL Predictive Audiences] 模型，您需要確定要分配的第一方資料源 [!UICONTROL Predictive Audiences] 特徵和片段。 您可以使用現有的第一方資料源，或建立新資料源。 請參閱 [管理資料源](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html) ，以瞭解有關如何建立新的第一方資料源的詳細資訊。

一旦知道要使用哪個資料源，請執行以下步驟。

1. 轉到 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**。
1. 在 [!UICONTROL Predictive Audiences] ，按一下 **[!UICONTROL Add New]**。

   ![智慧人物添加](assets/predictive-audiences-add.png)

1. 接下來，定義要將受眾分類的角色。 通過選擇特徵或片段來構建人物特徵，可以完成此操作。 使用 [!UICONTROL Traits] 和 [!UICONTROL Segments] 螢幕左上角的頁籤，以在特性目錄和段目錄之間切換。 確定要用作角色的特徵或段後，按一下相應的 **[!UICONTROL Add]** 的 [!UICONTROL Action] 的雙曲餘切值。
   ![智慧人物選擇人物](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >您必須為基線角色選擇至少兩個特徵或兩個段。 不能同時使用特徵和段的組合。
1. 按一下 **[!UICONTROL Next]** 在你定義了你的角色之後。
1. 接下來，通過為此受眾選擇第一方特性或段來選擇要分類的第一方受眾。 使用 [!UICONTROL Traits] 和 [!UICONTROL Segments] 螢幕左上角的頁籤，在特徵和段目錄之間切換。 選擇要用作受眾的第一方特性或段，以將其添加到模型中。
   ![精明個人選擇受眾](assets/predictive-audiences-audience.png)
1. 按一下 **[!UICONTROL Next]** 在你選好觀眾之後。
1. 填寫模型詳細資訊：
   * **[!UICONTROL Model Name]**:為模型輸入描述性名稱，以便稍後識別它。 由模型生成的段的名稱將以模型名稱開頭。
   * **[!UICONTROL Description]**:輸入有助於確定其使用案例的模型說明。
   * **[!UICONTROL Data Source]**:選擇要使用的第一方資料源 [!UICONTROL Predictive Audiences] 要分配給的模型段。
   * **[!UICONTROL Profile Merge Rule]**:選擇 [!UICONTROL Profile Merge Rule] 分配給所有預測 [!UICONTROL segments] 由此模型建立。 如果所選目標受眾是 [!UICONTROL segment]，建議選擇相同 [!UICONTROL Profile Merge Rule] 目標受眾的。
      ![預測受眾 — 保存](assets/predictive-audiences-save.png)
1. 按一下 **[!UICONTROL Save]**.

## 克隆和編輯預測受眾模型 {#clone-predictive-audiences}

Audience Manager不支援編輯現有 [!UICONTROL Predictive Audiences] 模型。 要更改模型的配置，可建立現有模型的克隆並對其進行編輯。 以下是您如何做到這一點：

1. 轉到 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**。
2. 按一下 [!UICONTROL Predictive Audiences] 要克隆的模型。
3. 按一下 **[!UICONTROL Clone]** 按鈕。
   ![預測受眾 — 克隆](assets/predictive-audiences-clone.png)
4. 克隆模型後，將轉到 [!DNL Save & Configure] 已克隆模型的頁面。 在此頁中，您可以更改 [!UICONTROL data source] 和分配的[!UICONTROL Profile Merge Rule] 模型。 要編輯克隆模型的角色和目標受眾，請使用 [!UICONTROL Back] 和 [!UICONTROL Next] 按鈕在三個頁籤之間導航，或按一下三個頁籤名稱

   ![預測受眾 — 克隆導航](assets/predictive-audiences-clone-navigate.png)

5. 編輯完模型後，按一下 **[!UICONTROL Save]**。

## 刪除預測受眾 {#delete-predictive-audiences}

刪除 [!UICONTROL Predictive Audiences] 模型，轉到 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，查找要刪除的模型，然後按一下 **[!UICONTROL Delete]** 表徵圖
