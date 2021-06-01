---
description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-title: 管理預測對象
solution: Audience Manager
title: 預測受眾快速入門
feature: 演算法模型
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 7%

---

# 預測受眾快速入門 {#predictive-audiences-getting-started}

>[!IMPORTANT]
>本文包含的產品檔案旨在引導您完成此功能的設定與使用。 這裡沒有任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

## 建立預測對象模型{#create-predictive-audiences}

建立[!UICONTROL Predictive Audiences]模型之前，您需要決定要將[!UICONTROL Predictive Audiences]特徵和區段指派給哪個第一方資料來源。 您可以使用現有的第一方資料來源，或建立新的資料來源。 如需如何建立新第一方資料來源的詳細資訊，請參閱[管理資料來源](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html)。

知道您要使用哪個資料來源後，請遵循下列步驟。

1. 前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**。
1. 在[!UICONTROL Predictive Audiences]區段中，按一下&#x200B;**[!UICONTROL Add New]**。

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. 接下來，定義要依據來分類對象的角色。 您可以選擇特徵或區段來建立角色，以達成此目的。 使用畫面左上角的[!UICONTROL Traits]和[!UICONTROL Segments]標籤，在特徵和區段目錄之間切換。 識別您要用作角色的特徵或區段後，按一下[!UICONTROL Action]欄中對應的&#x200B;**[!UICONTROL Add]**圖示。
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >您必須為基準角色選擇至少兩個特徵或兩個區段。 您無法同時使用特徵和區段的組合。
1. 定義角色後，按一下&#x200B;**[!UICONTROL Next]**。
1. 接下來，為此對象選擇第一方特徵或區段，以選取您要分類的第一方對象。 使用畫面左上角的[!UICONTROL Traits]和[!UICONTROL Segments]標籤，在特徵和區段目錄之間切換。 選取您要用來作為對象的第一方特徵或區段，以將其新增至模型。
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. 在您選擇對象後，按一下&#x200B;**[!UICONTROL Next]**。
1. 填寫模型詳細資訊：
   * **[!UICONTROL Model Name]**:為模型輸入描述性名稱，以便您稍後識別該名稱。由模型生成的段的名稱將以模型的名稱開頭。
   * **[!UICONTROL Description]**:輸入模型說明，以幫助您識別其使用案例。
   * **[!UICONTROL Data Source]**:選取您要將此模型中的區 [!UICONTROL Predictive Audiences] 段指派給的第一方資料來源。
   * **[!UICONTROL Profile Merge Rule]**:為此模 [!UICONTROL Profile Merge Rule] 型建立的所有預測性 [!UICONTROL segments] 選擇要分配的。如果您選取的目標對象是[!UICONTROL segment]，建議選取目標對象的相同[!UICONTROL Profile Merge Rule]。
      ![predictive-audiences — 儲存](assets/predictive-audiences-save.png)
1. 按一下 **[!UICONTROL Save]**.

## 複製和編輯預測對象模型{#clone-predictive-audiences}

Audience Manager不支援編輯現有的[!UICONTROL Predictive Audiences]模型。 要更改模型的配置，可以建立現有模型的克隆並進行編輯。 以下是您可以這麼做的方式：

1. 前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**。
2. 按一下要克隆的[!UICONTROL Predictive Audiences]模型的名稱。
3. 按一下畫面左上方的&#x200B;**[!UICONTROL Clone]**按鈕。
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. 複製模型後，會將您帶至複製模型的[!DNL Save & Configure]頁面。 在此頁中，可以更改模型的[!UICONTROL data source]和已分配的[!UICONTROL Profile Merge Rule]。 若要編輯複製模型的角色和目標對象，請使用[!UICONTROL Back]和[!UICONTROL Next]按鈕在三個標籤之間導航，或按一下三個標籤名稱

   ![predictive-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. 編輯完模型後，按一下&#x200B;**[!UICONTROL Save]**。

## 刪除預測對象{#delete-predictive-audiences}

要刪除[!UICONTROL Predictive Audiences]模型，請轉至&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，找到要刪除的模型，然後按一下&#x200B;**[!UICONTROL Delete]**&#x200B;表徵圖。
