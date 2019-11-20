---
description: 本文說明如何針對新整合和現有整合設定Twitter自訂對象。
seo-description: 本文說明如何針對新整合和現有整合設定Twitter自訂對象。
seo-title: 將Twitter量身訂做的觀眾設定為自助服務裝置型目的地
solution: Audience Manager
title: 將Twitter量身訂做的觀眾設定為自助服務裝置型目的地
translation-type: tm+mt
source-git-commit: 4af2d7a4e2162f8d69273cf76aecb5f1ff00e7b6

---


# 配置 [!DNL Twitter Tailored Audiences] 為基於自助設備的目標 {#configure-twitter}

本文說明如何設定與 [Twitter Tailored Audiences的整合](https://business.twitter.com/en/targeting/tailored-audiences.html)。

## 必備條件 {#prerequisites}

在設定目 [!DNL Twitter Tailored Audiences] 標之前，請務必檢閱您需要符合的下列Twitter先決條件。

1. 您的 [!DNL Twitter Ads] 帳戶必須符合廣告資格。 新帳 [!DNL Twitter Ads] 戶在建立後的前2週內無法取得廣告。
2. 您 [!DNL Twitter] 在Audience manager中授權存取的使用者帳戶必須啟用「合作伙 [伴對象管理員](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 」權限。
3. 在您的Audience manager實 [!DNL Twitter Tailored Audiences] 例中建立第一個目標時，請連絡Adobe諮詢或客戶服務，以啟用您帳戶的 [!DNL Twitter] ID同步化（資料來源ID = 1123）。 Audience manager和之間的正確同步需要此項 [!DNL Twitter]。

## 添加新目 [!DNL Twitter Tailored Audiences] 標 {#add-new-twitter-destination}

本節介紹為配置新的基於設備的目標時需要遵循的步驟 [!DNL Twitter Tailored Audiences]。 此案例假設您沒有透過Adobe顧問 [!DNL Twitter Tailored Audiences] 或客戶服務設定現有目標。

### 步驟 1. 驗證方 [!DNL Twitter Tailored Audiences] 式 {#step1-authenticate-with-twitter}

您必須先連結Audience Manager和您的帳戶，才能新增裝置型目 [!DNL Twitter Tailored Audiences] 的地。 以下是如何做到的：

1. 登入您的Audience manager帳戶，然後前往 **[!DNL Administration > Integrated Accounts]**。 如果您先前已設定與目標平台的整合，您應會在此頁面中看到它。 否則，頁面為空。
1. Click **[!DNL Add Account]**.
1. 選擇 [!DNL Twitter Tailored Audiences] 並按一下 **[!DNL Confirm]** 以重定向到驗證頁。                     ![整合平台](assets/dbd-integrated-platforms.png)
1. 一旦您通過驗證後，就會將您重新導向至Audience Manager，您應在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下 **[!DNL Confirm]**。

### 步驟 2.建立新的裝置型目標 {#step2-create-new-destination}

在連結Audience manager和您的 [!DNL Twitter Tailored Audiences]後，您可以建立新目標。 以下是如何做到的：

>[!NOTE]
>
>您無法變更現有裝置型目的地的名稱。 請務必提供有助於正確識別目標的名稱。

1. 登入您的Audience manager帳戶，前往， **[!DNL Audience Data > Destinations]**&#x200B;然後按一下 **[!DNL Create Destination]**。
1. 在該 **[!DNL Basic Information]** 部分中，輸入 **[!DNL Name]** 和 **[!DNL Description]** 新目標，然後使用以下設定：設 ![定](assets/dbd-new-basic.png)
1. Click **[!DNL Next]**.
1. 選擇 [要為此目標設定的資料導出標籤](/help/using/features/data-export-controls.md#controls-labels) 。
1. Click **[!DNL Save]**.
1. 在區 **[!DNL Segment Mappings]** 段中，選取您要傳送至此目的地的對象區段。
1. 保存目標。

<!--
## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

To improve the user experience and streamline the configuration process, we are upgrading the [!DNL Twitter Tailored Audiences] integration to a self-service model, where you can perform the configuration yourself, from the Audience Manager UI. This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>The steps described below only apply if you have an existing integration with [!DNL Twitter Tailored Audiences], configured by an Audience Manager consultant or Customer Care.
> See item number 3 in [Prerequisites](#prerequisites) before migrating your [!DNL Twitter Tailored Audiences] to the self-service model.

Follow the steps below to migrate your existing [!DNL Twitter Tailored Audiences] destination to the self-service model.

1. Log in to your Audience Manager account and go to **[!DNL Administration > Integrated Accounts]**.
2. Click **[!DNL Add Account]**.
3. Select [!DNL Twitter Tailored Audiences] and click **[!DNL Confirm]** to be redirected to the authentication page. ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated with your [!DNL Twitter] account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!DNL Confirm]**.
5. Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** and click the Twitter destination that you need to configure.
6. Click **[!UICONTROL Edit]**. In the **[!UICONTROL Basic Information]** section, click the **[!UICONTROL Integrated Account]** drop-down menu and select the [!DNL Twitter] account that you have authenticated with at Step 4.
7. **[!UICONTROL Save]** the destination.

## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

## 區段對應考量事項 {#segment-mapping-considerations}

將對象區段對應至 [!UICONTROL Twitter]時，請務必符合下列區段命名需求：

* 提供人類可讀的區段對應名稱。 我們建議您使用與Audience manager區段相同的名稱。
* 請勿在區段和區段映射中使用特殊字`,` 元( `%``:``;``@``/``=``?``$`Appring Names)。 如果您的Audience manager區段名稱包含這些字元，請先移除這些字元，再將區段對應至目 [!UICONTROL Twitter] 標。

### 範例

* 正確的區段或對應名稱：「美國和歐洲購物者」;
* 區段或對應名稱不正確：「美國、歐洲5h0pP3rs」。

>[!IMPORTANT]
>
>您無法變更已映射區段的名稱。 Audience manager使用區段名稱來正確識別整合中的區段。

## 匹配率注意事項 {#match-rates-considerations}

* 使用時， [!UICONTROL Twitter Tailored Audiences]目標頁 [!UICONTROL Segment Addressable Audience] 面的 [!UICONTROL Segment Match Rate] 和量度將不會顯示任何值。 這是正常行為，因為受眾比對以及此目的地的比對率是由Adobe而非Adobe處理 [!UICONTROL Twitter]和代管。
* 目前，Audience manager與Audience manager的整合不 [!UICONTROL Twitter Tailored Audiences] 支援歷史觀眾回填。 這表示只有區段對應至 *Twitter目的地* ，之後發生的區段資格才會即時 [!UICONTROL Twitter] 傳送至。
