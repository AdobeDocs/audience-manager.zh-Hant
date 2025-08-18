---
description: 本文說明如何設定Twitter自訂對象的新整合和現有整合。
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: 將Twitter自訂對象設定為自助服務以裝置為基礎的目的地
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# 將[!DNL Twitter Custom Audiences]設定為自助式以裝置為基礎的目的地 {#configure-twitter}

本文說明如何設定與[Twitter自訂對象](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html)的整合。

## 先決條件 {#prerequisites}

設定[!DNL Twitter Custom Audiences]目的地之前，請確定您符合下列必要條件。

* 您的[!DNL Twitter Ads]帳戶必須符合廣告資格。 新[!DNL Twitter Ads]帳戶在建立後的前2週內不符合廣告資格。
* 您在Audience Manager中授權存取的[!DNL Twitter]使用者帳戶必須啟用[合作夥伴對象管理員](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels)許可權。
* 在您的Audience Manager執行個體中建立第一個[!DNL Twitter Custom Audiences]目的地時，請聯絡Adobe Consulting或客戶服務，為您的帳戶啟用[!DNL Twitter] ID同步(資料Source ID = 1123)。 這是Audience Manager與[!DNL Twitter]之間正確同步所需。

## 新增新的[!DNL Twitter Custom Audiences]目的地 {#add-new-twitter-destination}

本節說明為[!DNL Twitter Custom Audiences]設定以裝置為基礎的新目的地時，必須遵循的步驟。 此情境假設您沒有透過您的Adobe顧問或客戶服務設定現有的[!DNL Twitter Custom Audiences]目的地。

### 步驟 1.使用[!DNL Twitter Custom Audiences]進行驗證 {#step1-authenticate-with-twitter}

在新增以裝置為基礎的目的地之前，您需要連結Audience Manager和您的[!DNL Twitter Custom Audiences]帳戶。 以下是其操作方式：

1. 登入您的Audience Manager帳戶並移至&#x200B;**[!DNL Administration > Integrated Accounts]**。 如果您先前設定好與目的地平台的整合，您應會看到此頁面所列的專案。 否則，頁面會是空的。
1. 按一下 **[!DNL Add Account]**。
1. 選取[!DNL Twitter Custom Audiences]並按一下&#x200B;**[!DNL Confirm]**&#x200B;以重新導向至驗證頁面。

   ![整合平台](assets/dbd-integrated-platforms.png)

1. 完成驗證後，系統會將您重新導向至Audience Manager，您應會在該處看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!DNL Confirm]**。

### 步驟 2.建立以裝置為基礎的新目的地 {#step2-create-new-destination}

連結Audience Manager和[!DNL Twitter Custom Audiences]後，您就可以建立新的目的地。 以下是其操作方式：

>[!NOTE]
>
>您無法變更現有的以裝置為基礎的目的地名稱。 請務必提供有助於您正確識別目的地的名稱。

1. 登入您的Audience Manager帳戶，前往&#x200B;**[!DNL Audience Data > Destinations]**，然後按一下&#x200B;**[!DNL Create Destination]**。
1. 在&#x200B;**[!DNL Basic Information]**&#x200B;區段中，輸入您新目的地的&#x200B;**[!DNL Name]**&#x200B;和&#x200B;**[!DNL Description]**，並使用下列設定： ![設定](assets/dbd-new-basic.png)
1. 按一下 **[!DNL Next]**。
1. 選擇要為此目的地設定的[資料匯出標籤](/help/using/features/data-export-controls.md#controls-labels)。
1. 按一下 **[!DNL Save]**。
1. 在&#x200B;**[!DNL Segment Mappings]**&#x200B;區段中，選取您要傳送至此目的地的對象區段。
1. 儲存目的地。

## 區段對應考量事項 {#segment-mapping-considerations}

將對象區段對應至[!UICONTROL Twitter]時，請確定符合下列區段命名需求：

* 提供人類可讀的區段對應名稱。 建議您使用與Audience Manager區段相同的名稱。
* 請勿在區段和區段對應名稱中使用特殊字元(`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`)。 如果您的Audience Manager區段名稱包含這些字元，請先移除這些字元，然後再將區段對應至[!UICONTROL Twitter]目的地。

### 範例

* 正確的區段或對應名稱：「美國和歐洲購物者」；
* 不正確的區段或對應名稱：「US， European 5h0pP3rs」。

>[!IMPORTANT]
>
>您無法變更已對應區段的名稱。 Audience Manager會使用區段名稱來正確識別整合中的區段。

## 符合率考量事項 {#match-rates-considerations}

* Audience Manager與[!UICONTROL Twitter Custom Audiences]之間的整合支援歷史受眾回填。 當您建立目的地時，所有區段資格都會傳送到[!UICONTROL Twitter]。

## 疑難排解 {#troubleshooting}

設定資料或將資料傳送到Twitter自訂對象目的地時，您可能會遇到下列錯誤。 本節說明可能導致錯誤的原因以及如何修正錯誤。

| 錯誤訊息 | 發生次數/原因 | 解決方法 |
|---|---|---|
| `Internal server error` | 嘗試使用過時的Twitter API版本新增新的[!DNL Twitter]帳戶時，此錯誤訊息會顯示在Audience Manager UI中。 | 聯絡Adobe客戶服務。 |
| `Twitter Error: This request is not properly authenticated` | 嘗試將不支援的區段名稱對應至目的地時，Audience Manager UI中會顯示此錯誤訊息。 | 檢閱對應的區段名稱，確認不含不支援的字元。 如需不支援的字元清單，請參閱[區段對應考量事項](#segment-mapping-considerations)。 |
| `Twitter Error: Account XXXXXXXXX was not found` | 為目的地設定的認證未獲授權存取對應的Twitter Ads帳戶時，此錯誤訊息會顯示在Audience Manager UI中。 | <ul><li>確定您使用的帳戶認證符合[必要條件](#prerequisites)。</li><li>使用相同的認證導覽至Twitter Ads UI，然後檢查對應的`XXXXXXXXX`帳戶下是否顯示正確的對象。 </li></ul> |