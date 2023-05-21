---
description: 本頁包括有關如何將離線CRM資料與即時行為資料相結合的逐步指導，以便經過身份驗證的用戶建立受眾段，然後將這些受眾段發送到基於人員的目標。
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with real-time behavioral data for authenticated users to create audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow C - Personalization Based on Authenticated Activity Combined with Offline Data
solution: Audience Manager
title: 工作流 C - 以結合離線資料的驗證活動為基礎的個人化
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 5%

---

# 工作流 C - 以結合離線資料的驗證活動為基礎的個人化 {#workflow-c}

>[!IMPORTANT]
>本文包含旨在指導您完成此功能的設定和使用的產品文檔。 這裡沒有法律建議。 請咨詢您自己的法律顧問以獲得法律指導。

本頁包括有關如何離線組合的逐步指導 [!DNL CRM] 資料，其中包含用於經過驗證的用戶的即時行為資料，以建立受眾段，然後將這些受眾段發送到 [!DNL People-Based Destinations]。

## 步驟1 — 配置資料源設定 {#configure-data-source-settings}

取決於 [DPUUID](../../reference/ids-in-aam.md) 是小寫的散列電子郵件地址，您可能需要配置將儲存散列電子郵件地址的資料源。

 

**方案1:你 [DPUUID](../../reference/ids-in-aam.md) 已經是小寫的散列電子郵件地址。**

在本例中，跳至 [步驟5 — 配置基於人員的平台身份驗證](#configure-authentication)。

 

**方案2:你 [DPUUID](../../reference/ids-in-aam.md) 不是小寫的散列電子郵件地址。**

在這種情況下，您需要建立一個新的跨設備資料源來儲存散列的電子郵件地址。 下面是如何做到的：

1. 登錄到您的Audience Manager帳戶，然後轉到 **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**，然後按一下 **[!UICONTROL Add New]**。
1. 輸入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** 新資料源。
1. 在 **[!UICONTROL ID Type]** 下拉菜單，選擇 **[!UICONTROL Cross Device]**。
1. 在 **[!UICONTROL Data Source Settings]** 的 **[!UICONTROL Inbound]** 和 **[!UICONTROL Outbound]** 選項，並啟用 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 的雙曲餘切值。
1. 使用下拉菜單選擇 **[!UICONTROL Emails(SHA256, lowercased)]** 標籤。
   >[!IMPORTANT]
   >
   >此選項僅將資料源標籤為包含使用該特定算法散列的資料。 Audience Manager在此步驟中不對資料進行散列。 確保您計畫儲存在此資料源中的電子郵件地址已與 [!DNL SHA256] 算法。 否則，您將無法使用 [!DNL People-Based Destinations]。

   ![pbd資料源設定](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 請參閱 [資料載入](people-based-destinations-prerequisites.md#data-onboarding) 有關如何將離線資料Audience Manager到基於人員的目標的常見問題。

觀看下面的視頻，瞭解如何建立資料源的視頻教程 [!UICONTROL People-Based Destinations]。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## 步驟2 — 使用聲明的ID通過即時HTTP調用將DPUUID與散列的電子郵件地址匹配 {#match-email-addresses}

要對經過驗證的用戶進行基於規則的特徵資格鑑定，您需要通過 [聲明的ID](../declared-ids.md)。

### 範例

假設您已建立以下兩個資料源。

| 資料源ID | 資料源內容 |
| -------------- | -------------------------- |
| 999999 | 現有DPUUID(CRM ID) |
| 987654 | 散列電子郵件地址 |

 

然後，您希望針對表中的特性限定下面的CRM ID。

| DPUUID(CRM ID) | 電子郵件地址 | 散列電子郵件地址 | 特徵 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | 位置=美國 |

 

您聲明的ID應遵循以下語法：

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

在上例中，聲明的ID調用應如下所示：

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## 步驟3 — 建立用於分段的配置檔案合併規則 {#create-profile-merge-rule-segmentation}

下一步是建立新的合併規則，該規則將幫助您建立要發送到您的 [!DNL People-Based Destinations]。

>[!IMPORTANT]
>
>如果已使用 **[!UICONTROL Current Authenticated Profiles]** 或 **[!UICONTROL Last Authenticated Profiles]** 選項，您可以跳過 [步驟4 — 建立受眾段](#create-audience-segments)。

1. 登錄到您的Audience Manager帳戶，然後轉到 **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**。
2. 按一下 **[!UICONTROL Add New Rule]**.
3. 輸入配置檔案合併規則 **[!UICONTROL Name]** 和 **[!UICONTROL Description]**。
4. 在 **[!UICONTROL Profile Merge Rule Setup]** 的 **[!UICONTROL Current Authenticated Profiles]** 或 **[!UICONTROL Last Authenticated Profiles]** 規則 **[!UICONTROL Cross-Device Options]** 清單框。
5. 在 **[!UICONTROL Cross-Device Profile Options]** 清單中，選擇要在上運行分段的資料源。 這些應是包含現有DPUUID的資料源。
   ![合併規則設定](assets/pbd-pmr-combined.png)

## 步驟4 — 建立受眾段 {#create-audience-segments}

要建立新段，請使用 [段生成器](../segments/segment-builder.md)。 如果您有要發送到的現有受眾段 [!DNL People-Based Destinations]，跳至 [步驟5 — 配置基於人員的平台身份驗證](#configure-authentication)。

## 步驟5 — 配置基於人員的平台身份驗證 {#configure-authentication}

1. 登錄到您的Audience Manager帳戶，然後轉到 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您以前配置了與社交平台的整合，則應在此頁中列出。 否則，頁面為空。
   ![基於人的整合](assets/pbd-config.png)
2. 按一下 **[!UICONTROL Add Account]**.
3. 使用 **[!UICONTROL People-Based Platform]** 下拉菜單，以選擇要配置整合的平台。
   ![基於人的平台](assets/pbd-add.png)
4. 按一下 **[!UICONTROL Confirm]** 重定向到所選平台的驗證頁面。
5. 一旦您已經通過社交平台帳戶的身份驗證，您將被重定向到Audience Manager，您應該在該區域查看相關的廣告商帳戶。 選擇要使用的廣告商帳戶，然後按一下 **[!UICONTROL Confirm]**。
6. Audience Manager在頁面頂部顯示通知，以便您知道是否已成功添加帳戶。 此通知還允許您添加聯繫人電子郵件地址以在社交平台身份驗證即將過期時接收通知。

>[!IMPORTANT]
>
>Audience Manager通過驗證令牌處理與社交平台的整合，該令牌在一定時間後過期。 有關如何續訂過期令牌的詳細資訊，請參閱驗證令牌續訂。

## 步驟6 — 建立基於人員的目標 {#create-destination}

1. 登錄到Audience Manager帳戶，轉到 **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**，然後按一下 **[!UICONTROL Create Destination]**。
1. 在 **[!UICONTROL Basic Information]** 部分，輸入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** 為新資料源，並使用以下設定：
   * **[!UICONTROL Category]**:整合平台；
   * **[!UICONTROL Type]**:以人為本；
   * **[!UICONTROL Platform]**:選擇要向其發送受眾段的基於人的平台；
   * **[!UICONTROL Account]**:選擇與所選平台關聯的所需廣告商帳戶。
      ![建立目標](assets/pbd-create-destination.png)
1. 按一下 **[!UICONTROL Next]**.
1. 選擇 **[!UICONTROL Data Export Labels]** 要為此目標設定。
1. 在 **[!UICONTROL Configuration]** 部分，選擇包含散列資料源的資料源。
1. 在 **[!UICONTROL Segment Mappings]** 部分，選擇要發送到此目標的段。 這將是您在 [步驟4 — 建立受眾段](#create-audience-segments)。
1. 保存目標。
