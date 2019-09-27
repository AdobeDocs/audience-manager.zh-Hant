---
description: 本文說明如何針對新整合和現有整合設定Twitter自訂對象。
seo-description: 本文說明如何針對新整合和現有整合設定Twitter自訂對象。
seo-title: 將Twitter量身訂做的觀眾設定為自助服務裝置型目的地
solution: Audience Manager
title: 將Twitter量身訂做的觀眾設定為自助服務裝置型目的地
translation-type: tm+mt
source-git-commit: c6318921b49603015b4670a361ec85ffa29abb30

---


# 配置 [!DNL Twitter Tailored Audiences] 為基於自助設備的目標 {#configure-twitter}

本文說明如何針對新的和現 [有的整合設定Twitter Tailored](https://business.twitter.com/en/targeting/tailored-audiences.html) Audiences。

## 必備條件 {#prerequisites}

在設定目 [!DNL Twitter Tailored Audiences] 標之前，請務必檢閱您需要符合的下列Twitter先決條件。

1. 您的 [!DNL Twitter Ads] 帳戶必須符合廣告資格。 新帳 [!DNL Twitter Ads] 戶在建立後的前2週內無法取得廣告。
1. 您在Audience manager中授權存取的Twitter使用者帳戶必須啟用「合作伙 [伴對象管理員](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 」權限。
1. 如果您要將 [現有的Twitter整合更新為自助服務管理](#update-existing-twitter-integrations)，您的Twitter使用者帳戶必須啟用廣告 [管理員](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 權限。
1. 在您的Audience manager實 [!DNL Twitter Tailored Audiences] 例中建立第一個目標時，請連絡Adobe諮詢或客戶服務，以啟用您帳戶的 [!DNL Twitter] ID同步化（資料來源ID = 1123）。 This is required for the correct synchronization between Audience Manager and .[!DNL Twitter]

## Add a New [!DNL Twitter Tailored Audiences] Destination {#add-new-twitter-destination}

This section describes the steps you need to follow when configuring a new device-based destination for [!DNL Twitter Tailored Audiences]. 此案例假設您沒有透過Adobe顧問 [!DNL Twitter Tailored Audiences] 或客戶服務設定現有目標。

### 步驟 1. 驗證方 [!DNL Twitter Tailored Audiences] 式 {#step1-authenticate-with-twitter}

您必須先連結Audience Manager和您的帳戶，才能新增裝置型目 [!DNL Twitter Tailored Audiences] 的地。 Here's how to do this:

1. Log in to your Audience Manager account and go to **[!DNL Administration > Integrated Accounts]**. If you have a previously configured integration with a destination platform, you should see it listed in this page. 否則，頁面為空。
2. Click **[!DNL Add Account]**.
3. 選擇 [!DNL Twitter Tailored Audiences] 並按一下 **[!DNL Confirm]** 以重定向到驗證頁。                     ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click .**[!DNL Confirm]**

### 步驟 2.建立新的裝置型目標 {#step2-create-new-destination}

After you have linked Audience Manager and your , you can create the new destination. [!DNL Twitter Tailored Audiences]Here's how to do this:

>[!NOTE]
>
>You cannot change the name of an existing device-based destination. Make sure to provide a name that will help you identify the destination correctly.

1. Log in to your Audience Manager account, go to , and click .**[!DNL Audience Data > Destinations]****[!DNL Create Destination]**
2. In the **[!DNL Basic Information]** section, enter a **[!DNL Name]** and **[!DNL Description]** for your new destination, and use the settings below: ![setup](assets/dbd-new-basic.png)
3. Click **[!DNL Next]**.
4. 選擇 [要為此目標設定的資料導出標籤](/help/using/features/data-export-controls.md#controls-labels) 。
5. Click **[!DNL Save]**.
6. 在區 **[!DNL Segment Mappings]** 段中，選取您要傳送至此目的地的對象區段。
7. 保存目標。

## 將現有的Twitter整合更新為自助服務管理 {#update-existing-twitter-integrations}

為改善使用者體驗並簡化設定程式，我們將整合升級為自助服務模型，您可從Audience Manager UI自行執行設定。 [!DNL Twitter Tailored Audiences] 本節說明更新現有Twitter整合時需要採取的步驟。

>[!IMPORTANT]
>
>以下所述步驟僅適用於您已與Audience manager顧問或客戶服務 [!DNL Twitter Tailored Audiences]所設定的現有整合時。 您目的地的自助服務模型完整升級程式最長需要5個工作日。 同時，您的目的地仍然有效，而Audience manager會持續傳送受眾至。
> 在移轉至自助服務模 [型之前](#prerequisites) ，請參 [!DNL Twitter Tailored Audiences] 閱先決條件中的項目編號3。

請遵循下列步驟，將您的現 [!DNL Twitter Tailored Audiences] 有目的地移轉至自助服務模型。

1. 登入您的Audience manager帳戶，然後前往 **[!DNL Administration > Integrated Accounts]**。
1. Click **[!DNL Add Account]**.
1. 選擇 [!DNL Twitter Tailored Audiences] 並按一下 **[!DNL Confirm]** 以重定向到驗證頁。 ![整合平台](assets/dbd-integrated-platforms.png)
1. 在您的帳戶進行驗證後，您會 [!DNL Twitter] 被重新導向至Audience Manager，您應該會在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下 **[!DNL Confirm]**。
1. 前往 **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** 並按一下您需要設定的Twitter目的地。
1. Click **[!UICONTROL Edit]**. 在區 **[!UICONTROL Basic Information]** 段中，按一 **[!UICONTROL Integrated Account]** 下下拉式功能表，並選取您在步驟4 [!DNL Twitter] 中已驗證的帳戶。
1. **[!UICONTROL Save]** 目的地。

## 驗證向自助服務管理的遷移 {#migration-validation}

將現有整合完 [!DNL Twitter] 整移轉至自助服務管理最多需要7天。 移轉完成後，Audience manager會在UI中顯示通知。

您也會在帳戶中看到一組新的對象，其 [!DNL Twitter] 名稱會加上[[!DNL Adobe DMP Audience]]的前置詞。 請允許最多7天的時間，讓觀眾人數完全回填。 Once the migration is complete, you should use these new audiences instead of the old ones.

## Segment Mapping Considerations {#segment-mapping-considerations}

When mapping audience segments to Twitter, make sure to meet the following segment naming requirements:

* Provide human-readable segment mapping names. 我們建議您使用與Audience manager區段相同的名稱。
* 請勿在區段和區段對應名稱中使用逗號。

### 範例

* 正確的區段或對應名稱：「美國和歐洲購物者」;
* 區段或對應名稱不正確：「美國、歐洲5h0pP3rs」。

>[!IMPORTANT]
>
>您無法變更已映射區段的名稱。 Audience manager使用區段名稱來正確識別整合中的區段。

## Match Rates Considerations {#match-rates-considerations}

When using , the  and  metrics from the destination page will not display any values. [!UICONTROL Twitter Tailored Audiences][!UICONTROL Segment Addressable Audience][!UICONTROL Segment Match Rate]This is normal behavior, since audience matching along with the match rates for this destination are handled and hosted by , not Adobe.[!UICONTROL Twitter]
