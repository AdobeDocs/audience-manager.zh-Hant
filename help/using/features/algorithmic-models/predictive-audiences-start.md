---
description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-description: 預測受眾可協助您運用資料科學，將未知的受眾即時分類為不重複角色。
seo-title: 管理預測性對象
solution: Audience Manager
title: 預測受眾快速入門
feature: 演算法模型
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
translation-type: tm+mt
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 7%

---

# 預測受眾快速入門 {#predictive-audiences-getting-started}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

## 建立預測性觀眾模型{#create-predictive-audiences}

在建立[!UICONTROL Predictive Audiences]模型之前，您必須決定要將[!UICONTROL Predictive Audiences]特徵和區段指派給哪個第一方資料來源。 您可以使用現有的第一方資料來源，或建立新的資料來源。 如需如何建立新第一方資料來源的詳細資訊，請參閱[管理資料來源](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html)。

一旦您知道要使用哪個資料來源，請遵循下列步驟。

1. 前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**。
1. 在[!UICONTROL Predictive Audiences]區段中，按一下&#x200B;**[!UICONTROL Add New]**。

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. 接著，定義您要依據對象分類的角色。 您可以選擇特徵或群體來建立角色， 使用畫面左上角的[!UICONTROL Traits]和[!UICONTROL Segments]標籤，在特徵和區段目錄之間切換。 在您識別要用作角色的特徵或群體後，按一下[!UICONTROL Action]欄中對應的&#x200B;**[!UICONTROL Add]**圖示。
   ![智慧型人選角色](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >您必須為基準角色選擇至少兩個特徵或兩個群體。 您無法同時使用特徵和區段的組合。
1. 定義角色後，按一下&#x200B;**[!UICONTROL Next]**。
1. 接著，選取您要分類的第一方對象，方法是為此對象選擇第一方特徵或群體。 使用畫面左上角的[!UICONTROL Traits]和[!UICONTROL Segments]標籤，在特徵和區段目錄之間切換。 選取您想要用作對象的第一方特徵或群體，以將其新增至模型。
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. 在您選擇對象後，按一下&#x200B;**[!UICONTROL Next]**。
1. 填寫模型詳細資料：
   * **[!UICONTROL Model Name]**:為模型輸入描述性名稱，這將幫助您稍後識別它。由模型生成的段的名稱將以模型的名稱開頭。
   * **[!UICONTROL Description]**:輸入有助於識別其使用案例的模型說明。
   * **[!UICONTROL Data Source]**:選取您要將此模型中的區段指 [!UICONTROL Predictive Audiences] 派給的第一方資料來源。
   * **[!UICONTROL Profile Merge Rule]**:為此模 [!UICONTROL Profile Merge Rule] 型建立的所有預測性 [!UICONTROL segments] 選擇要指派的。如果您選取的目標對象是[!UICONTROL segment]，我們建議選取目標對象的相同[!UICONTROL Profile Merge Rule]。
      ![predictive-audiences-save](assets/predictive-audiences-save.png)
1. 按一下 **[!UICONTROL Save]**.

## 克隆和編輯預測性受眾模型{#clone-predictive-audiences}

Audience Manager不支援編輯現有的[!UICONTROL Predictive Audiences]型號。 要更改模型的配置，可建立現有模型的克隆並對其進行編輯。 以下是您如何做到的：

1. 前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**。
2. 按一下要克隆的[!UICONTROL Predictive Audiences]模型的名稱。
3. 按一下畫面左上方的&#x200B;**[!UICONTROL Clone]**按鈕。
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. 克隆模型後，將轉至克隆模型的[!DNL Save & Configure]頁。 在此頁中，可以更改模型的[!UICONTROL data source]和已分配的[!UICONTROL Profile Merge Rule]。 要編輯克隆模型的角色和目標對象，請使用[!UICONTROL Back]和[!UICONTROL Next]按鈕在三個頁籤之間導航，或按一下三個頁籤名稱

   ![predictive-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. 編輯完模型後，按一下&#x200B;**[!UICONTROL Save]**。

## 刪除預測性對象{#delete-predictive-audiences}

要刪除[!UICONTROL Predictive Audiences]模型，請轉至&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，查找要刪除的模型，然後按一下&#x200B;**[!UICONTROL Delete]**&#x200B;表徵圖。
