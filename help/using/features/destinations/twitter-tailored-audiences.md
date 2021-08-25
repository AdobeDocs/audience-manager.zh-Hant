---
description: 本文說明如何針對新整合和現有整合設定Twitter自訂對象。
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: 將Twitter自訂對象設定為自助服務以裝置為基礎的目的地
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 670d2f1990d7370ab8930776df9ae5af71dd3d9e
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 1%

---

# 將[!DNL Twitter Custom Audiences]配置為基於自助服務設備的目標 {#configure-twitter}

本文說明如何設定與[Twitter自訂對象](https://business.twitter.com/en/targeting/tailored-audiences.html)的整合。

## 必要條件 {#prerequisites}

設定[!DNL Twitter Custom Audiences]目的地前，請務必檢閱您需要符合的下列Twitter必要條件。

1. 您的[!DNL Twitter Ads]帳戶必須符合廣告資格。 新[!DNL Twitter Ads]帳戶在建立後的前2週內不符合廣告資格。
2. 您授權在Audience Manager中存取的[!DNL Twitter]使用者帳戶必須已啟用[合作夥伴audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels)權限。
3. 在您的Audience Manager例項中建立第一個[!DNL Twitter Custom Audiences]目的地時，請聯絡Adobe諮詢或客戶服務，為您的帳戶啟用[!DNL Twitter] ID同步（資料來源ID = 1123）。 這是在Audience Manager和[!DNL Twitter]之間正確同步所必需的。

## 添加新的[!DNL Twitter Custom Audiences]目標 {#add-new-twitter-destination}

本節介紹為[!DNL Twitter Custom Audiences]配置新的基於設備的目標時需要遵循的步驟。 此案例假設您沒有透過您的Adobe顧問或客戶服務設定任何現有的[!DNL Twitter Custom Audiences]目的地。

### 步驟 1. 使用[!DNL Twitter Custom Audiences]進行驗證 {#step1-authenticate-with-twitter}

您必須先連結Audience Manager和[!DNL Twitter Custom Audiences]帳戶，才能新增以裝置為基礎的目的地。 以下是操作方法：

1. 登入您的Audience Manager帳戶，然後前往&#x200B;**[!DNL Administration > Integrated Accounts]**。 如果您先前已設定與目的地平台的整合，您應會在本頁面中看到該整合列出。 否則，頁面為空。
1. 按一下 **[!DNL Add Account]**.
1. 選擇[!DNL Twitter Custom Audiences]並按一下&#x200B;**[!DNL Confirm]**&#x200B;以重定向到身份驗證頁。                     ![整合平台](assets/dbd-integrated-platforms.png)
1. 驗證後，系統會將您重新導向至Audience Manager，您應該會在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!DNL Confirm]**。

### 步驟 2.建立新的以裝置為基礎的目的地 {#step2-create-new-destination}

在連結Audience Manager和[!DNL Twitter Custom Audiences]後，您可以建立新目的地。 以下是操作方法：

>[!NOTE]
>
>您無法更改現有基於設備的目標的名稱。 請務必提供可協助您正確識別目的地的名稱。

1. 登入您的Audience Manager帳戶，前往&#x200B;**[!DNL Audience Data > Destinations]**，然後按一下&#x200B;**[!DNL Create Destination]**。
1. 在&#x200B;**[!DNL Basic Information]**&#x200B;區段中，輸入新目的地的&#x200B;**[!DNL Name]**&#x200B;和&#x200B;**[!DNL Description]**，然後使用下列設定：![setup](assets/dbd-new-basic.png)
1. 按一下 **[!DNL Next]**.
1. 選擇要為此目標設定的[資料導出標籤](/help/using/features/data-export-controls.md#controls-labels)。
1. 按一下 **[!DNL Save]**.
1. 在&#x200B;**[!DNL Segment Mappings]**&#x200B;區段中，選取您要傳送至此目的地的對象區段。
1. 儲存目的地。

## 區段對應考量事項 {#segment-mapping-considerations}

將受眾區段對應至[!UICONTROL Twitter]時，請務必符合下列區段命名需求：

* 提供人類看得懂的區段對應名稱。 建議您使用與用於Audience Manager區段相同的名稱。
* 在區段和區段對應名稱中，請勿使用特殊字元(`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`)。 如果您的Audience Manager區段名稱包含這些字元，請先將其移除，再將區段對應至[!UICONTROL Twitter]目的地。

### 範例

* 正確的區段或對應名稱：「美國和歐洲購物者」；
* 區段或對應名稱不正確：「美國、歐洲5h0pP3rs」。

>[!IMPORTANT]
>
>您無法變更已映射區段的名稱。 Audience Manager使用區段名稱來正確識別整合中的區段。

## 匹配率考量事項 {#match-rates-considerations}

* Audience Manager與[!UICONTROL Twitter Custom Audiences]之間的整合支援歷史受眾回填。 建立目的地時，所有區段資格都會傳送至[!UICONTROL Twitter]。
