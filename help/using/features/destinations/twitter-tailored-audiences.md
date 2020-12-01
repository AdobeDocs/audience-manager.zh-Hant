---
description: 本文說明如何針對新整合和現有整合設定Twitter自訂對象。
seo-description: 本文說明如何針對新整合和現有整合設定Twitter自訂對象。
seo-title: 將為 Twitter 量身打造的受眾設定為自助服務以裝置為基礎的目的地
solution: Audience Manager
title: 將為 Twitter 量身打造的受眾設定為自助服務以裝置為基礎的目的地
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: 8ff76decc1cbd7f7babd619dd1ce9fe047541337
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 4%

---


# 將[!DNL Twitter Tailored Audiences]配置為基於自助設備的目標{#configure-twitter}

本文說明如何設定與[Twitter Tailored Audiences](https://business.twitter.com/en/targeting/tailored-audiences.html)的整合。

## 必要條件 {#prerequisites}

在設定[!DNL Twitter Tailored Audiences]目標之前，請務必檢閱您需要符合的下列Twitter必要條件。

1. 您的[!DNL Twitter Ads]帳戶必須符合廣告資格。 新[!DNL Twitter Ads]帳戶在建立後的前2週內不符合廣告資格。
2. 您在Audience Manager中授權存取的[!DNL Twitter]使用者帳戶必須啟用[合作夥伴對象管理員](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels)權限。
3. 在您的Audience Manager例項中建立第一個[!DNL Twitter Tailored Audiences]目標時，請聯絡Adobe諮詢或客戶服務，以啟用您帳戶的[!DNL Twitter] ID同步化（資料來源ID = 1123）。 Audience Manager和[!DNL Twitter]之間的正確同步需要此項。

## 新增[!DNL Twitter Tailored Audiences]目標{#add-new-twitter-destination}

本節介紹為[!DNL Twitter Tailored Audiences]配置新的基於設備的目標時需要遵循的步驟。 此案例假設您沒有透過Adobe顧問或客戶服務設定現有的[!DNL Twitter Tailored Audiences]目標。

### 步驟 1. 驗證[!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

您必須先連結Audience Manager和您的[!DNL Twitter Tailored Audiences]帳戶，才能新增裝置型目標。 以下是如何做到的：

1. 登入您的Audience Manager帳戶並前往&#x200B;**[!DNL Administration > Integrated Accounts]**。 如果您先前已設定與目標平台的整合，您應會在此頁面中看到它。 否則，頁面為空。
1. 按一下 **[!DNL Add Account]**.
1. 選擇[!DNL Twitter Tailored Audiences]並按一下&#x200B;**[!DNL Confirm]**&#x200B;以重定向到驗證頁。                     ![整合平台](assets/dbd-integrated-platforms.png)
1. 一旦您通過驗證後，就會將您重新導向至Audience Manager，您應在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!DNL Confirm]**。

### 步驟 2.建立新的基於設備的目標{#step2-create-new-destination}

在連結Audience Manager和[!DNL Twitter Tailored Audiences]後，您就可以建立新的目的地。 以下是如何做到的：

>[!NOTE]
>
>您無法變更現有裝置型目的地的名稱。 請務必提供有助於正確識別目標的名稱。

1. 登入您的Audience Manager帳戶，前往&#x200B;**[!DNL Audience Data > Destinations]**，然後按一下&#x200B;**[!DNL Create Destination]**。
1. 在&#x200B;**[!DNL Basic Information]**&#x200B;區段中，輸入新目標的&#x200B;**[!DNL Name]**&#x200B;和&#x200B;**[!DNL Description]**，然後使用以下設定：![setup](assets/dbd-new-basic.png)
1. 按一下 **[!DNL Next]**.
1. 選擇要為此目標設定的[資料導出標籤](/help/using/features/data-export-controls.md#controls-labels)。
1. 按一下 **[!DNL Save]**.
1. 在&#x200B;**[!DNL Segment Mappings]**&#x200B;區段中，選取您要傳送至此目的地的對象區段。
1. 保存目標。

## 區段對應考量事項{#segment-mapping-considerations}

將對象區段對應至[!UICONTROL Twitter]時，請確定符合下列區段命名需求：

* 提供人類可讀的區段對應名稱。 我們建議您使用與Audience Manager區段相同的名稱。
* 請勿在區段和區段對應名稱中使用特殊字元(`,` `%` `:` `;` `@` `/` `=` `?` `$`)。 如果您的Audience Manager區段名稱包含這些字元，請先移除這些字元，再將區段對應至[!UICONTROL Twitter]目標。

### 範例

* 正確的區段或對應名稱：「美國和歐洲購物者」;
* 區段或對應名稱不正確：「美國、歐洲5h0pP3rs」。

>[!IMPORTANT]
>
>您無法變更已映射區段的名稱。 Audience Manager使用區段名稱來正確識別整合中的區段。

## 匹配率注意事項{#match-rates-considerations}

* Audience Manager與[!UICONTROL Twitter Tailored Audiences]的整合支援歷史觀眾回填。 當您建立目標時，所有區段資格都會傳送至[!UICONTROL Twitter]。
