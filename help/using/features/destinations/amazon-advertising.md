---
description: 本文說明如何設定Amazon Advertising的新整合和現有整合。
solution: Audience Manager
title: 將Amazon Advertising設定為自助服務以裝置為基礎的目的地
exl-id: 049af52a-b425-493d-9e77-9ced7ba6d168
source-git-commit: bac3167927af0957e7081e1ea653464101affcb8
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 1%

---

# 將[!DNL Amazon Advertising]設定為自助式以裝置為基礎的目的地 {#configure-amazon}

本文說明如何設定與[Amazon Advertising](https://advertising.amazon.com/API/docs/en-us)的整合。

## 先決條件 {#prerequisites}

設定[!DNL Amazon Advertising]目的地之前，請確定您符合下列必要條件。

* 您的[!DNL Amazon]帳戶必須符合廣告資格。
* 在您的Audience Manager執行個體中建立第一個[!DNL Amazon Advertising]目的地時，請聯絡Adobe Consulting或客戶服務以啟用您帳戶的[!DNL Amazon] ID同步處理(資料Source ID = 139200)。 這是Audience Manager與[!DNL Amazon]之間正確同步所需。
* 建立新的資料提供者對象後，您應該[更新其中繼資料](https://advertising.amazon.com/API/docs/en-us/data-provider/openapi#tag/Metadata/paths/~1v2~1dp~1audiencemetadata~1%7BaudienceId%7D/put)並新增&#x200B;**[!DNL audience fees]**。 針對此作業，您可以使用[Amazon Ads API](https://advertising.amazon.com/API/docs/en-us/guides/onboarding/apply-for-access)或[Amazon Advertising UI](https://advertising.amazon.com/)。

## 新增新的[!DNL Amazon Advertising]目的地 {#add-new-amazon-destination}

本節說明為[!DNL Amazon Advertising]設定以裝置為基礎的新目的地時，必須遵循的步驟。 此情境假設您沒有透過您的Adobe顧問或客戶服務設定現有的[!DNL Amazon Advertising]目的地。

### 步驟 1.使用[!DNL Amazon Advertising]進行驗證 {#step1-authenticate-with-amazon}

在新增以裝置為基礎的目的地之前，您需要連結Audience Manager和您的[!DNL Amazon Advertising]帳戶。 以下是其操作方式：

1. 登入您的Audience Manager帳戶並移至&#x200B;**[!UICONTROL Administration > Integrated Accounts]**。 如果您先前設定好與目的地平台的整合，您應會看到此頁面所列的專案。 否則，頁面會是空的。
1. 選取&#x200B;**[!UICONTROL Add Account]**。
1. 選取[!UICONTROL Amazon Data Provider]。

   ![整合平台](assets/dbd-amazon-without-options.png)

1. 根據建立&#x200B;**[!UICONTROL Amazon Data Provider]**&#x200B;帳戶的地區（北美、歐洲或遠東）選取[!DNL Amazon Ads]選項之一，然後按一下&#x200B;**[!DNL Confirm]**&#x200B;以重新導向至驗證頁面。

   ![整合平台](assets/dbd-amazon-with-options.png)

1. 完成驗證後，系統會將您重新導向至Audience Manager，您應會在該處看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!UICONTROL Confirm]**。 藉由執行此操作，您已授權Audience Manager的存取權以傳送對象的更新。

### 步驟 2.建立以裝置為基礎的新目的地 {#step2-create-new-destination}

連結Audience Manager和[!DNL Amazon Advertising]帳戶後，您就可以建立新的目的地。 以下是其操作方式：

>[!NOTE]
>
>您無法變更現有的以裝置為基礎的目的地名稱。 請務必提供有助於您正確識別目的地的名稱。

1. 登入您的Audience Manager帳戶，前往&#x200B;**[!UICONTROL Audience Data > Destinations]**，然後選取&#x200B;**[!UICONTROL Create Destination]**。
1. 在&#x200B;**[!UICONTROL Basic Information]**&#x200B;區段中，輸入您新目的地的&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**，並使用下列設定：

   ![安裝程式](assets/dbd-new-account-amazon.png)

1. 選取&#x200B;**[!UICONTROL Next]**。
1. 選擇要為此目的地設定的[資料匯出標籤](/help/using/features/data-export-controls.md#controls-labels)。
1. 選取&#x200B;**[!UICONTROL Save]**。
1. 在&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;區段中，選取您要傳送至此目的地的對象區段。
1. 儲存目的地。

## 符合率考量事項 {#match-rates-considerations}

Audience Manager與[!DNL Amazon Advertising]之間的整合支援歷史受眾回填。 當您建立目的地時，所有區段資格都會傳送到[!DNL Amazon]。

## 疑難排解 {#troubleshooting}

設定資料或將資料傳送到[!DNL Amazon Advertising]目的地時，您可能會遇到下述錯誤。 本節說明可能導致錯誤的原因以及如何修正錯誤。

| 錯誤訊息 | 發生次數/原因 | 解決方法 |
|---|---|---|
| `Internal server error` | 嘗試使用過時版本的Audience Manager API新增新的[!DNL Amazon]帳戶時，此錯誤訊息會顯示在Amazon UI中。 | 聯絡Adobe客戶服務。 |
| `Amazon Error: Account XXXXXXXXX was not found` | 為目的地設定的認證未獲授權存取對應的Audience Manager Ads帳戶時，此錯誤訊息會顯示在Amazon UI中。 | <ul><li>確定您使用的帳戶認證符合[必要條件](#prerequisites)。</li><li>使用相同的認證導覽至Amazon Ads UI，並檢查對應的帳戶下是否顯示正確的對象。 </li></ul> |
