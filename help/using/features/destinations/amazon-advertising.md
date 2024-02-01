---
description: 本文說明如何為新整合和現有整合設定Amazon Advertising。
solution: Audience Manager
title: 將Amazon Advertising設定為自助服務以裝置為基礎的目的地
source-git-commit: 01f3c2d813a91b8541bd8ba8a8b030f67a4f979e
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 1%

---


# 設定 [!DNL Amazon Advertising] 作為自助服務以裝置為基礎的目的地 {#configure-amazon}

本文說明如何設定整合，透過 [Amazon Advertising](https://advertising.amazon.com/API/docs/en-us).

## 必備條件 {#prerequisites}

設定前 [!DNL Amazon Advertising] 目的地，請確定您符合下列必要條件。

* 您的 [!DNL Amazon] 帳戶必須符合廣告資格。
* 建立第一個 [!DNL Amazon Advertising] 目的地在您的Audience Manager執行個體中，請聯絡Adobe諮詢或客戶服務，以啟用 [!DNL Amazon] 您的帳戶的ID同步(資料來源ID = 139200)。 這是Audience Manager和之間正確同步的必要條件 [!DNL Amazon].
* 建立新的資料提供者對象後，您應： [更新他們的中繼資料](https://advertising.amazon.com/API/docs/en-us/data-provider/openapi#tag/Metadata/paths/~1v2~1dp~1audiencemetadata~1%7BaudienceId%7D/put) 並新增 **[!DNL audience fees]**. 針對此作業，您可以使用 [Amazon Ads API](https://advertising.amazon.com/API/docs/en-us/guides/onboarding/apply-for-access) 或 [Amazon Advertising UI](https://advertising.amazon.com/).

## 新增 [!DNL Amazon Advertising] 目的地 {#add-new-amazon-destination}

本節說明在設定以裝置為基礎的新目的地時，必須遵循的步驟。 [!DNL Amazon Advertising]. 此情境假設您沒有現有的 [!DNL Amazon Advertising] 透過您的Adobe顧問或客戶服務設定的目的地。

### 步驟 1.驗證方式 [!DNL Amazon Advertising] {#step1-authenticate-with-amazon}

在新增以裝置為基礎的目的地之前，您需要先連結Audience Manager和 [!DNL Amazon Advertising] 帳戶。 以下是其操作方式：

1. 登入您的Audience Manager帳戶並移至 **[!UICONTROL Administration > Integrated Accounts]**. 如果您先前設定好與目的地平台的整合，您應會看到此頁面所列的專案。 否則，頁面會是空的。
1. 選取 **[!UICONTROL Add Account]**.
1. 選取 [!UICONTROL Amazon Data Provider].

   ![整合平台](assets/dbd-amazon-without-options.png)

1. 選取其中一項 **[!UICONTROL Amazon Data Provider]** 選項視您所在 [!DNL Amazon Ads] 已建立帳戶（北美、歐洲或遠東），然後按一下 **[!DNL Confirm]** 重新導向至「驗證」頁面。

   ![整合平台](assets/dbd-amazon-with-options.png)

1. 驗證之後，您會重新導向至Audience Manager，應該會看到相關廣告商帳戶的位置。 選取您要使用的廣告商帳戶，然後按一下 **[!UICONTROL Confirm]**. 藉由執行此動作，您即授權Audience Manager的存取權以傳送對象的更新。

### 步驟 2.建立以裝置為基礎的新目的地 {#step2-create-new-destination}

連結Audience Manager與 [!DNL Amazon Advertising] 帳戶，您可以建立新的目的地。 以下是其操作方式：

>[!NOTE]
>
>您無法變更現有的以裝置為基礎的目的地名稱。 請務必提供有助於您正確識別目的地的名稱。

1. 登入您的Audience Manager帳戶，前往 **[!UICONTROL Audience Data > Destinations]**，並選取 **[!UICONTROL Create Destination]**.
1. 在 **[!UICONTROL Basic Information]** 區段，輸入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** ，並使用下列設定：

   ![設定](assets/dbd-new-account-amazon.png)

1. 選取 **[!UICONTROL Next]**.
1. 選擇 [資料匯出標籤](/help/using/features/data-export-controls.md#controls-labels) 要為此目的地設定的屬性。
1. 選取 **[!UICONTROL Save]**.
1. 在 **[!UICONTROL Segment Mappings]** 區段，選取您要傳送至此目的地的對象區段。
1. 儲存目的地。

## 符合率考量事項 {#match-rates-considerations}

Audience Manager與之間的整合 [!DNL Amazon Advertising] 支援歷史對象回填。 所有區段資格皆會傳送至 [!DNL Amazon] 建立目的地時。

## 疑難排解 {#troubleshooting}

設定資料或將資料傳送至 [!DNL Amazon Advertising] 目的地，您可能會遇到下列錯誤。 本節說明可能導致錯誤的原因以及如何修正錯誤。

| 錯誤訊息 | 發生次數/原因 | 解決方法 |
|---|---|---|
| `Internal server error` | 嘗試新增時，Audience ManagerUI中會顯示此錯誤訊息 [!DNL Amazon] 使用過時版本Amazon API的帳戶。 | 請聯絡Adobe客戶服務。 |
| `Amazon Error: Account XXXXXXXXX was not found` | 為目的地設定的認證未獲授權存取對應的Amazon Ads帳戶時，此錯誤訊息會顯示在Audience ManagerUI中。 | <ul><li>確定您使用的帳戶認證符合 [必備條件](#prerequisites).</li><li>使用相同的認證導覽至Amazon Ads UI，並檢查對應的帳戶下是否顯示正確的對象。 </li></ul> |
