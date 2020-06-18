---
description: 本文說明如何針對新整合和現有整合設定Twitter自訂對象。
seo-description: 本文說明如何針對新整合和現有整合設定Twitter自訂對象。
seo-title: 將為 Twitter 量身打造的受眾設定為自助服務以裝置為基礎的目的地
solution: Audience Manager
title: 將為 Twitter 量身打造的受眾設定為自助服務以裝置為基礎的目的地
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 4%

---


# 配置 [!DNL Twitter Tailored Audiences] 為基於自助設備的目標 {#configure-twitter}

本文說明如何設定與 [Twitter Tailored Audiences的整合](https://business.twitter.com/en/targeting/tailored-audiences.html)。

## 必要條件 {#prerequisites}

在設定目 [!DNL Twitter Tailored Audiences] 標之前，請務必檢閱下列您必須符合的Twitter必要條件。

1. 您的 [!DNL Twitter Ads] 帳戶必須符合廣告資格。 新帳 [!DNL Twitter Ads] 戶在建立後的前2週內無法取得廣告。
2. 您 [!DNL Twitter] 在Audience Manager中授權存取的使用者帳戶必須啟用「合作伙 [伴對象管理員](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 」權限。
3. 在您的Audience Manager實 [!DNL Twitter Tailored Audiences] 例中建立第一個目標時，請連絡Adobe諮詢或客戶服務，以啟用您帳戶的 [!DNL Twitter] ID同步化（資料來源ID = 1123）。 Audience Manager和之間的正確同步需要此項 [!DNL Twitter]。

## 添加新目 [!DNL Twitter Tailored Audiences] 標 {#add-new-twitter-destination}

本節介紹為配置新的基於設備的目標時需要遵循的步驟 [!DNL Twitter Tailored Audiences]。 此案例假設您沒有透過Adobe顧問 [!DNL Twitter Tailored Audiences] 或客戶服務設定現有目標。

### 步驟 1. 驗證 [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

您必須先連結Audience Manager和您的帳戶，才能新增裝置型目 [!DNL Twitter Tailored Audiences] 的地。 以下是如何做到的：

1. 登入您的Audience Manager帳戶，然後前往 **[!DNL Administration > Integrated Accounts]**。 如果您先前已設定與目標平台的整合，您應會在此頁面中看到它。 否則，頁面為空。
1. 按一下 **[!DNL Add Account]**.
1. 選擇 [!DNL Twitter Tailored Audiences] 並按一下 **[!DNL Confirm]** 以重定向到驗證頁。                     ![整合平台](assets/dbd-integrated-platforms.png)
1. 一旦您通過驗證後，就會將您重新導向至Audience Manager，您應在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下 **[!DNL Confirm]**。

### 步驟 2.建立新的裝置型目標 {#step2-create-new-destination}

在連結Audience Manager和您的 [!DNL Twitter Tailored Audiences]後，您可以建立新目標。 以下是如何做到的：

>[!NOTE]
>
>您無法變更現有裝置型目的地的名稱。 請務必提供有助於正確識別目標的名稱。

1. 登入您的Audience Manager帳戶，前往， **[!DNL Audience Data > Destinations]**&#x200B;然後按一下 **[!DNL Create Destination]**。
1. 在該 **[!DNL Basic Information]** 部分中，輸入 **[!DNL Name]** 和 **[!DNL Description]** 新目標，然後使用以下設定： ![設定](assets/dbd-new-basic.png)
1. 按一下 **[!DNL Next]**.
1. 選擇 [要為此目標設定的資料導出標籤](/help/using/features/data-export-controls.md#controls-labels) 。
1. 按一下 **[!DNL Save]**.
1. 在區 **[!DNL Segment Mappings]** 段中，選取您要傳送至此目的地的對象區段。
1. 保存目標。

## 區段對應考量事項 {#segment-mapping-considerations}

將對象區段對應至 [!UICONTROL Twitter]時，請務必符合下列區段命名需求：

* 提供人類可讀的區段對應名稱。 我們建議您使用與Audience Manager區段相同的名稱。
* 請勿在區段和區段映射中使用特殊字`,` 元( `%``:``;``@``/``=``?``$`Appring Names)。 如果您的Audience Manager區段名稱包含這些字元，請先移除這些字元，再將區段對應至目 [!UICONTROL Twitter] 標。

### 範例

* 正確的區段或對應名稱： 「美國和歐洲購物者」;
* 區段或對應名稱不正確： 「美國、歐洲5h0pP3rs」。

>[!IMPORTANT]
>
>您無法變更已映射區段的名稱。 Audience Manager使用區段名稱來正確識別整合中的區段。

## 匹配率注意事項 {#match-rates-considerations}

* 使用時， [!UICONTROL Twitter Tailored Audiences]目標頁 [!UICONTROL Segment Addressable Audience] 面的 [!UICONTROL Segment Match Rate] 和量度將不會顯示任何值。 這是正常行為，因為受眾比對以及此目的地的比對率是由Adobe而非Adobe處理 [!UICONTROL Twitter]和代管。
* Audience Manager與支援歷史觀眾回填 [!UICONTROL Twitter Tailored Audiences] 的整合。 建立目標時，會傳送所 [!UICONTROL Twitter] 有區段資格給。
