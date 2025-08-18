---
description: 預測客群可協助您運用資料科學，將未知的客群即時分類為不重複角色。
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Managing Predictive Audiences
solution: Audience Manager
title: 預測受眾快速入門
feature: Algorithmic Models
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 2%

---

# 預測受眾快速入門 {#predictive-audiences-getting-started}

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 此處未包含任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

## 建立預測受眾模型 {#create-predictive-audiences}

建立[!UICONTROL Predictive Audiences]模型之前，您必須先決定要將[!UICONTROL Predictive Audiences]特徵和區段指派給哪個第一方資料來源。 您可以使用現有的第一方資料來源，或建立新的資料來源。 如需有關如何建立新的第一方資料來源的詳細資訊，請參閱[管理資料來源](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html?lang=zh-Hant)。

知道要使用哪個資料來源後，請遵循下列步驟。

1. 前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**。
1. 在[!UICONTROL Predictive Audiences]區段中，按一下&#x200B;**[!UICONTROL Add New]**。

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. 接著，定義您要用來分類對象的角色。 您可以透過選擇要從中建置角色的特徵或區段來執行此操作。 使用畫面左上角的[!UICONTROL Traits]和[!UICONTROL Segments]索引標籤，在特徵和區段目錄之間切換。 識別您要做為角色的特徵或區段後，請按一下「**[!UICONTROL Add]**」欄中對應的「[!UICONTROL Action]」圖示。
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >您必須至少為基線角色選擇兩個特徵或兩個區段。 您無法同時使用特徵和區段。
1. 在您定義角色後，請按一下「**[!UICONTROL Next]**」。
1. 接著，為此對象選擇第一方特徵或區段，以選取您要分類的第一方對象。 使用畫面左上角的[!UICONTROL Traits]和[!UICONTROL Segments]索引標籤，在特徵和區段目錄之間切換。 選取您要當作對象的第一方特徵或區段，以將其新增至模型。
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. 在您選擇對象後，請按一下「**[!UICONTROL Next]**」。
1. 填寫模型詳細資料：
   * **[!UICONTROL Model Name]**：輸入模型的描述性名稱，以協助您稍後識別。 模型產生的區段名稱將以模型名稱開頭。
   * **[!UICONTROL Description]**：輸入模型的描述，以協助您識別其使用案例。
   * **[!UICONTROL Data Source]**：選取您要指派此模型之[!UICONTROL Predictive Audiences]區段的第一方資料來源。
   * **[!UICONTROL Profile Merge Rule]**：選取要指派給此模型建立的所有預測性[!UICONTROL Profile Merge Rule]的[!UICONTROL segments]。 如果您選取的目標對象是[!UICONTROL segment]，我們建議您選取目標對象的相同[!UICONTROL Profile Merge Rule]。
     ![predictive-audiences-save](assets/predictive-audiences-save.png)
1. 按一下 **[!UICONTROL Save]**。

## 複製和編輯預測對象模型 {#clone-predictive-audiences}

Audience Manager不支援編輯現有[!UICONTROL Predictive Audiences]模型。 若要變更模型的組態，您可以建立現有模型的複製並加以編輯。 以下說明如何執行此操作：

1. 前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**。
2. 按一下您要複製的[!UICONTROL Predictive Audiences]模型名稱。
3. 按一下畫面左上角的&#x200B;**[!UICONTROL Clone]**&#x200B;按鈕。
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. 複製模型後，就會進入複製模型的[!DNL Save & Configure]頁面。 您可以在此頁面變更模型的[!UICONTROL data source]和指派的[!UICONTROL Profile Merge Rule]。 若要編輯複製模型的角色和目標對象，請使用[!UICONTROL Back]和[!UICONTROL Next]按鈕在三個標籤之間導覽，或按一下三個標簽名稱

   ![predictive-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. 當您完成編輯模型時，請按一下&#x200B;**[!UICONTROL Save]**。

## 刪除預測對象 {#delete-predictive-audiences}

若要刪除[!UICONTROL Predictive Audiences]模型，請前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Models]**，尋找您要刪除的模型，然後按一下&#x200B;**[!UICONTROL Delete]**&#x200B;圖示。
