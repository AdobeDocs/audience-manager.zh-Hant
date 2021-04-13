---
description: 本文說明如何針對新整合和現有整合設定Twitter自訂對象。
seo-description: 本文說明如何針對新整合和現有整合設定Twitter自訂對象。
seo-title: 將為 Twitter 量身打造的受眾設定為自助服務以裝置為基礎的目的地
solution: Audience Manager
title: 將為 Twitter 量身打造的受眾設定為自助服務以裝置為基礎的目的地
feature: 以人為本的目的地
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# 將[!DNL Twitter Tailored Audiences]配置為基於自助設備的目標{#configure-twitter}

本文說明如何設定與[Twitter Tailored Audiences](https://business.twitter.com/en/targeting/tailored-audiences.html)的整合。

## 必要條件 {#prerequisites}

在設定[!DNL Twitter Tailored Audiences]目標之前，請務必檢閱您需要符合的下列Twitter必要條件。

1. 您的[!DNL Twitter Ads]帳戶必須符合廣告資格。 新[!DNL Twitter Ads]帳戶在建立後的前2週內不符合廣告資格。
2. 您授權在Audience Manager中存取的[!DNL Twitter]使用者帳戶必須啟用[合作夥伴對象管理員](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels)權限。
3. 在您的Audience Manager實例中建立第一個[!DNL Twitter Tailored Audiences]目標時，請聯繫Adobe咨詢或客戶服務，為您的帳戶啟用[!DNL Twitter] ID同步（資料源ID = 1123）。 這是Audience Manager與[!DNL Twitter]之間正確同步所必需的。

## 新增[!DNL Twitter Tailored Audiences]目標{#add-new-twitter-destination}

本節介紹為[!DNL Twitter Tailored Audiences]配置新的基於設備的目標時需要遵循的步驟。 此方案假設您沒有透過您的Adobe顧問或客戶服務來設定現有的[!DNL Twitter Tailored Audiences]目標。

### 步驟 1. 驗證[!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

在添加基於設備的目標之前，您需要連結Audience Manager和[!DNL Twitter Tailored Audiences]帳戶。 以下是如何做到的：

1. 登入您的Audience Manager帳戶並前往&#x200B;**[!DNL Administration > Integrated Accounts]**。 如果您先前已設定與目標平台的整合，您應會在此頁面中看到它。 否則，頁面為空。
1. 按一下 **[!DNL Add Account]**.
1. 選擇[!DNL Twitter Tailored Audiences]並按一下&#x200B;**[!DNL Confirm]**&#x200B;以重定向到驗證頁。                     ![整合平台](assets/dbd-integrated-platforms.png)
1. 一旦您通過驗證後，系統會將您重新導向至Audience Manager，您應該在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!DNL Confirm]**。

### 步驟 2.建立新的基於設備的目標{#step2-create-new-destination}

在連結Audience Manager和[!DNL Twitter Tailored Audiences]後，可以建立新目標。 以下是如何做到的：

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
* 請勿在區段和區段對應名稱中使用特殊字元(`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`)。 如果您的Audience Manager區段名稱包含這些字元，請先移除這些字元，再將區段對應至[!UICONTROL Twitter]目標。

### 範例

* 正確的區段或對應名稱：「美國和歐洲購物者」;
* 區段或對應名稱不正確：「美國、歐洲5h0pP3rs」。

>[!IMPORTANT]
>
>您無法變更已映射區段的名稱。 Audience Manager會使用區段名稱來正確識別整合中的區段。

## 匹配率注意事項{#match-rates-considerations}

* Audience Manager與[!UICONTROL Twitter Tailored Audiences]之間的整合支援歷史讀者回填。 當您建立目標時，所有區段資格都會傳送至[!UICONTROL Twitter]。
