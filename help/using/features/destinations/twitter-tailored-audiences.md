---
description: 本文介紹如何為新整合和現有整合配置Twitter定制受眾。
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: 將Twitter自定義受眾配置為基於設備的自助服務目標
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 1%

---

# 配置 [!DNL Twitter Custom Audiences] 作為基於自助設備的目標 {#configure-twitter}

本文介紹如何配置與 [Twitter定制觀眾](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html)。

## 必要條件 {#prerequisites}

在配置之前 [!DNL Twitter Custom Audiences] 目標，確保滿足以下先決條件。

* 您 [!DNL Twitter Ads] 帳戶必須符合廣告資格。 新建 [!DNL Twitter Ads] 帳戶在建立後的頭2週內無資格獲得廣告。
* 您 [!DNL Twitter] 在Audience Manager中授權訪問的用戶帳戶必須具有 [合作夥伴受眾經理](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 權限已啟用。
* 建立第一個 [!DNL Twitter Custom Audiences] 目標，請聯繫Adobe咨詢或客戶服務以啟用Audience Manager實例 [!DNL Twitter] 帳戶的ID同步（資料源ID = 1123）。 這是在Audience Manager和 [!DNL Twitter]。

## 添加新 [!DNL Twitter Custom Audiences] 目標 {#add-new-twitter-destination}

本節介紹在為配置新的基於設備的目標時需要遵循的步驟 [!DNL Twitter Custom Audiences]。 此方案假定您沒有現有 [!DNL Twitter Custom Audiences] 通過您的Adobe顧問或客戶服務配置的目標。

### 步驟 1. 驗證 [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

在添加基於設備的目標之前，您需要將Audience Manager與 [!DNL Twitter Custom Audiences] 帳戶。 下面是如何做到的：

1. 登錄到您的Audience Manager帳戶，然後轉到 **[!DNL Administration > Integrated Accounts]**。 如果您以前配置了與目標平台的整合，則應在此頁中列出該整合。 否則，頁面為空。
1. 按一下 **[!DNL Add Account]**.
1. 選擇 [!DNL Twitter Custom Audiences] 按一下 **[!DNL Confirm]** 重定向到驗證頁。

   ![整合平台](assets/dbd-integrated-platforms.png)

1. 一旦您經過身份驗證，您將重定向到Audience Manager，您應該在該區域查看相關的廣告商帳戶。 選擇要使用的廣告商帳戶，然後按一下 **[!DNL Confirm]**。

### 步驟 2.建立新的基於設備的目標 {#step2-create-new-destination}

在你把Audience Manager和 [!DNL Twitter Custom Audiences]，可以建立新目標。 下面是如何做到的：

>[!NOTE]
>
>不能更改現有基於設備的目標的名稱。 確保提供有助於正確標識目標的名稱。

1. 登錄到Audience Manager帳戶，轉到 **[!DNL Audience Data > Destinations]**，然後按一下 **[!DNL Create Destination]**。
1. 在 **[!DNL Basic Information]** 部分，輸入 **[!DNL Name]** 和 **[!DNL Description]** 用於新目標，並使用以下設定： ![設定](assets/dbd-new-basic.png)
1. 按一下 **[!DNL Next]**.
1. 選擇 [資料導出標籤](/help/using/features/data-export-controls.md#controls-labels) 要為此目標設定。
1. 按一下 **[!DNL Save]**.
1. 在 **[!DNL Segment Mappings]** 部分，選擇要發送到此目標的受眾段。
1. 保存目標。

## 段映射注意事項 {#segment-mapping-considerations}

將受眾段映射到 [!UICONTROL Twitter]，確保滿足以下段命名要求：

* 提供人可讀段映射名稱。 我們建議使用您用於Audience Manager段的相同名稱。
* 不使用特殊字元(`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`)。 如果您的Audience Manager段名稱包含這些字元，請在將段映射到 [!UICONTROL Twitter] 目標。

### 範例

* 正確的段或映射名稱：「美國和歐洲購物者」；
* 段或映射名稱不正確：「美國、歐洲5h0pP3rs」。

>[!IMPORTANT]
>
>無法更改已映射段的名稱。 Audience Manager使用段名稱正確標識整合中的段。

## 匹配比率注意事項 {#match-rates-considerations}

* Audience Manager與 [!UICONTROL Twitter Custom Audiences] 支援歷史受眾回填。 所有段資格都發送到 [!UICONTROL Twitter] 建立目標。

## 疑難排解 {#troubleshooting}

配置資料或將資料發送到Twitter自定義訪問群體目標時，可能會遇到以下描述的錯誤。 本節說明可能導致錯誤的原因以及如何修復錯誤。

| 錯誤消息 | 事件/原因 | 解決方法 |
|---|---|---|
| `Internal server error` | 嘗試添加新的Audience Manager時，此錯誤消息將顯示在UI中 [!DNL Twitter] 使用過時版本的TwitterAPI。 | 連絡 Adobe 客戶服務. |
| `Twitter Error: This request is not properly authenticated` | 當嘗試將具有不受支援段名稱的段映射到目標時，此錯誤消息會顯示在Audience ManagerUI中。 | 查看映射的段名稱，並確保它們不包含不受支援的字元。 請參閱 [段映射注意事項](#segment-mapping-considerations) 的子菜單。 |
| `Twitter Error: Account XXXXXXXXX was not found` | 當為目標配置的憑據未授權訪問相應的Twitter廣告帳戶時，Audience ManagerUI中將顯示此錯誤消息。 | <ul><li>確保您使用的帳戶憑據符合 [先決條件](#prerequisites)。</li><li>使用相同憑據導航到Twitter廣告用戶介面，並檢查是否在相應的用戶下顯示了正確的受眾 `XXXXXXXXX` 帳戶。 </li></ul> |