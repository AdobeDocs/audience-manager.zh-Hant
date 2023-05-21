---
description: 本頁包括有關如何從僅離線的客戶資料構建受眾段並將它們發送到基於人員的目標的逐步指導。
seo-description: This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.
seo-title: Workflow B - Personalization Based on Offline-Only Data
solution: Audience Manager
title: 工作流程 B - 以僅限離線資料為基礎的個人化
feature: People-based Destinations
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
source-git-commit: 87c3169083f0dc66490e6a8c808e16371f1d78c0
workflow-type: tm+mt
source-wordcount: '1143'
ht-degree: 6%

---

# 工作流程 B - 以僅限離線資料為基礎的個人化 {#workflow-b}

>[!IMPORTANT]
>本文包含旨在指導您完成此功能的設定和使用的產品文檔。 這裡沒有法律建議。 請咨詢您自己的法律顧問以獲得法律指導。

本頁包括有關如何從僅離線的客戶資料構建受眾段並將它們發送到基於人員的目標的逐步指導。

## 步驟1 — 板載離線特性 {#step-1-onboard-traits}

在此方案中建立受眾段的第一步是將離線客戶資料引入Audience Manager。

>[!IMPORTANT]
>
> 在繼續之前，請確保您即將加入的客戶活動已與相應的Audience Manager一起定義 [已上鈎的性狀](../traits/trait-and-segment-qualification-reference.md)。

無論您現有的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))是散列電子郵件，您必須對包含您的 [DPUUID](../../reference/ids-in-aam.md)。

### 範例

您希望從下表中為相應的掛接特性ID限定客戶ID。 讓我們考慮一下 [DPUUID](../../reference/ids-in-aam.md) 儲存在ID為999999的資料源中，而Audience Manager資料源ID為123。

| 客戶ID(DPUUID) | 掛接特性ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

要驗證上例中客戶ID是否具有相應的已掛載特徵，必須上載 [入站資料檔案](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) 內容如下：

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

檔案名如下所示： `ftp_dpm_999999_123_TIMESTAMP.sync.gz`。
請參閱 [Amazon入站資料檔案的S3名稱和檔案大小要求](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 的子菜單。

## 步驟2 — 配置資料源設定 {#configure-data-source-settings}

取決於 [DPUUID](../../reference/ids-in-aam.md) 是小寫的散列電子郵件地址，您可能需要配置將儲存散列電子郵件地址的資料源。

 

**方案1:你 [DPUUID](../../reference/ids-in-aam.md) 已經是小寫的散列電子郵件地址。**

在這種情況下，您需要將相應的資料源標籤為：

1. 轉到 **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**。
1. 查找包含您的 [DPUUID](../../reference/ids-in-aam.md)，然後按一下。
1. 確保選項 **[!UICONTROL Cannot be tied to personally identifiable information]** 複選框。
1. 保存資料源設定。

 

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

## 步驟3 — 通過基於檔案的ID同步將DPUUID與散列電子郵件地址匹配 {#match-ids-emails}

>[!IMPORTANT]
>
> 此步驟僅適用於 [方案2](people-based-destinations-workflow-offline.md#configure-data-source-settings) 如上所述。 如果您現有 [DPUUID](../../reference/ids-in-aam.md) 已經有散列的電子郵件地址，跳至 [步驟4 — 建立用於分段的配置檔案合併規則](#create-profile-merge-rule)。

假設你想與你現有的 [DPUUID](../../reference/ids-in-aam.md) 從步驟1的示例到下表（右列）中散列的電子郵件地址，並將散列的電子郵件地址儲存在您在建立的新資料源中 [步驟2 — 配置資料源設定](#configure-data-source-settings)。

作為提醒，您現在有兩個資料源：

| 資料源ID | 資料源內容 |
| -------------- | -------------------------- |
| 999999 | 現有DPUUID(CRM ID) |
| 987654 | 散列電子郵件地址 |

| DPUUID(CRM ID) | 電子郵件地址 | 散列電子郵件地址 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

以我們為例， [ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 將包含以下內容：

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

的 [ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 必須遵循此命名結構：

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

在上面的示例中，檔案名如下所示：
`c2c_id_999999_987654_1560431657.sync`

[在此處下載示例檔案](assets/c2c_id_999999_987654_1560431657.sync)。

建立ID同步檔案後，需要將其上載到 [!DNL Amazon S3] 桶。 要瞭解如何上載ID同步檔案，請參見 [將批資料發送到Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)。

## 步驟4 — 建立用於分段的配置檔案合併規則 {#create-profile-merge-rule}

下一步是建立新的合併規則，該規則將幫助您建立要發送到您的 [!DNL People-Based Destinations]。

1. 登錄到您的Audience Manager帳戶，然後轉到 **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**。
2. 按一下 [!UICONTROL Add New Rule].
3. 輸入配置檔案合併規則 **[!UICONTROL Name]** 和 **[!UICONTROL Description]**。
4. 在 **[!UICONTROL Profile Merge Rule Setup]** 的 **[!UICONTROL All Cross-Device Profiles]** 規則 **[!UICONTROL Cross-Device Options]** 清單框。
5. 在 **[!UICONTROL Cross-Device Profile Options]** 清單中，選擇您的特徵所針對的資料源。
   ![合併規則設定](assets/pbd-pmr.png)

## 步驟5 — 建立受眾段 {#create-audience-segments}

要從僅離線資料建立新段，請使用 [段生成器](../segments/segment-builder.md) 並確保在建立段時使用在上一步中建立的新配置檔案合併規則。

## 步驟6 — 配置基於人員的平台身份驗證 {#configure-authentication}

1. 登錄到您的Audience Manager帳戶，然後轉到 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您以前配置了與社交平台的整合，則應在此頁中列出。 否則，頁面為空。
   ![基於人的整合](assets/pbd-config.png)
1. 按一下 **[!UICONTROL Add Account]**.
1. 使用 **[!UICONTROL People-Based Platform]** 下拉菜單，以選擇要配置整合的平台。
   ![基於人的平台](assets/pbd-add.png)
1. 按一下 **[!UICONTROL Confirm]** 重定向到所選平台的驗證頁面。
1. 一旦您已經通過社交平台帳戶的身份驗證，您將被重定向到Audience Manager，您應該在該區域查看相關的廣告商帳戶。 選擇要使用的廣告商帳戶，然後按一下 **[!UICONTROL Confirm]**。
1. Audience Manager在頁面頂部顯示通知，以便您知道是否已成功添加帳戶。 此通知還允許您添加聯繫人電子郵件地址以在社交平台身份驗證即將過期時接收通知。

>[!IMPORTANT]
>
>Audience Manager通過驗證令牌處理與社交平台的整合，該令牌在一定時間後過期。 有關如何續訂過期令牌的詳細資訊，請參閱驗證令牌續訂。

## 步驟7 — 建立基於人員的目標 {#create-destination}

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
1. 在 **[!UICONTROL Segment Mappings]** 部分，選擇要發送到此目標的段。 這將是您在 [步驟5 — 建立受眾段](people-based-destinations-workflow-offline.md#create-audience-segments)。
1. 保存目標。
