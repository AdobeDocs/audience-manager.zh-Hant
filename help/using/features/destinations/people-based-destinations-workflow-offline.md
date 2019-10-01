---
description: '本頁包含逐步指引，說明如何從僅離線的客戶資料建立受眾細分，並將其傳送至以人為本的目標。  '
seo-description: '本頁包含逐步指引，說明如何從僅離線的客戶資料建立受眾細分，並將其傳送至以人為本的目標。  '
seo-title: Workflow B - Personalization Based on Offline-Only Data
solution: Audience Manager
title: 工作流程B —— 基於僅離線資料的個人化
translation-type: tm+mt
source-git-commit: fb5d9eff3573048d3e8a570b342a97bce3cd8da0

---


# Workflow B - Personalization Based on Offline-Only Data {#workflow-b}

>[!IMPORTANT]
>This article contains product documentation meant to guide you through the setup and usage of this feature. Nothing contained herein is legal advice. Please consult your own legal counsel for legal guidance.

This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.

## Step 1 - Onboard Offline Traits {#step-1-onboard-traits}

在此案例中建立受眾細分的第一步，就是將您的離線客戶資料匯入Audience Manager。

>[!IMPORTANT]
>
> Before continuing, make sure that the customer activity that you are about to onboard is already defined in Audience Manager with corresponding [onboarded traits](../traits/trait-qualification-reference.md).

Regardless of whether your existing Audience Manager customer IDs (DPUUIDs) are hashed emails or not, you must perform the trait onboarding against the data source that contains your DPUUIDs.[](../../reference/ids-in-aam.md)[](../../reference/ids-in-aam.md)

### 範例

您想要從下表中為對應的已登入特徵ID限定客戶ID。 Let's consider that your DPUUIDs are stored in a data source with the ID 999999, and your Audience Manager Partner ID is 123.[](../../reference/ids-in-aam.md)

| 客戶ID(DPUUID) | 已登入特徵ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />
若要將上述範例中的客戶ID限定為對應的已登入特徵，您必須上傳包含下列內容的[傳入資料檔案](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md):

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

檔案名如下所示： `ftp_dpm_999999_123_TIMESTAMP.sync.gz`。
如需 [檔案名稱結構的詳細資訊，請參閱Amazon S3傳入資料檔案的名稱和檔案大小需求](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 。

## Step 2 - Configure Data Source Settings {#configure-data-source-settings}

視您的 [DPUUID是小寫](../../reference/ids-in-aam.md) 、雜湊電子郵件地址而定，您可能需要設定將儲存雜湊電子郵件地址的資料來源。

 

**方案1:您的[DPUUID](../../reference/ids-in-aam.md)已是小寫、雜湊的電子郵件地址。**

在這種情況下，您需要將對應的資料源標籤為：

1. 轉到 **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**。
1. 尋找包含您的DPUUID的資 [料來源](../../reference/ids-in-aam.md)，然後按一下。
1. 請確定選項未 **[!UICONTROL Cannot be tied to personally identifiable information]** 勾選。
1. 儲存資料來源設定。

 

**方案2:您的[DPUUID](../../reference/ids-in-aam.md)不是小寫、雜湊的電子郵件地址。**

在這種情況下，您需要建立新的跨裝置資料來源，以儲存雜湊的電子郵件地址。 以下是如何做到的：

1. 登入您的Audience manager帳戶並前往 **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**，然後按一下 **[!UICONTROL Add New]**。
1. 為新數 **[!UICONTROL Name]** 據源 **[!UICONTROL Description]** 輸入和。
1. 在下拉 **[!UICONTROL ID Type]** 式功能表中，選取 **[!UICONTROL Cross Device]**。
1. 在該節 **[!UICONTROL Data Source Settings]** 中，同時選擇和 **[!UICONTROL Inbound]** 選 **[!UICONTROL Outbound]** 項，並啟用選 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 項。
1. 使用下拉式選單來選取此 **[!UICONTROL Emails(SHA256, lowercased)]** 資料來源的標籤。
   >[!IMPORTANT]
   >
   >This option only labels the data source as containing data hashed with that specific algorithm. Audience Manager does not hash the data at this step. Make sure the email addresses that you plan on storing in this data source are already hashed with the  algorithm. [!DNL SHA256]否則，您將無法使用它 [!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > See Data Onboarding for frequently asked questions about how you should bring your offline data into Audience Manager for People-Based Destinations.[](people-based-destinations-prerequisites.md#data-onboarding)

## Step 3 - Match DPUUIDs to Hashed Email Addresses via File-Based ID Synchronization {#match-ids-emails}

>[!IMPORTANT]
>
> 此步驟僅適用於上 [述的方案](people-based-destinations-workflow-offline.md#configure-data-source-settings) 2。 If your existing DPUUIDs are already hashed email addresses, skip to Step 4 - Create a Profile Merge Rule for Segmentation.[](../../reference/ids-in-aam.md)[](#create-profile-merge-rule)

假設您想要將步驟1範例中的現有 [DPUUID](../../reference/ids-in-aam.md) ，與下表（右欄）中雜湊的電子郵件地址相符，並將雜湊的電子郵件地址儲存在您在步驟2 —— 設定資料來源設定中建立的新資料來源中 [](#configure-data-source-settings)。

提醒您，您現在有兩個資料來源：

| 資料來源ID | 資料來源內容 |
| -------------- | -------------------------- |
| 999999 | 現有DPUUID(CRM ID) |
| 987654 | 雜湊的電子郵件地址 |

| DPUUID(CRM ID) | 電子郵件地址 | 雜湊電子郵件地址 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

在我們的範例中，您的 [ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ，會包含下列內容：

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

[ID同步檔案必須遵循](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 下列命名結構：

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

在上述範例中，檔案名稱會如下所示：
`c2c_id_999999_987654_1560431657.sync`

[在這裡下載範例檔案](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)。

建立ID同步檔案後，您必須將它上傳至儲 [!DNL Amazon S3] 存貯體。 如要瞭解如何上傳ID同步檔案，請參 [閱傳送批次資料至Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)。

## Step 4 - Create a Profile Merge Rule for Segmentation {#create-profile-merge-rule}

The next step is creating a new merge rule that will help you create the audience segments to send to your .[!DNL People-Based Destinations]

1. Log in to your Audience Manager account and go to  -&gt; .**[!UICONTROL Audience Data]****[!UICONTROL Profile Merge Rules]**
2. 按一下 [!UICONTROL Add New Rule].
3. 輸入配置檔案合併規 **[!UICONTROL Name]** 則和 **[!UICONTROL Description]**。
4. 在區段 **[!UICONTROL Profile Merge Rule Setup]** 中，從清單 **[!UICONTROL All Cross-Device Profiles]** 中選取規 **[!UICONTROL Cross-Device Options]** 則。
5. 在清單 **[!UICONTROL Cross-Device Profile Options]** 中，選取您的特徵所針對的資料來源。
   ![merge-rule-setup](assets/pbd-pmr.png)

## 步驟5 —— 建立觀眾區段 {#create-audience-segments}

若要從僅離線資料建立新區段，請使用「區段產生器 [](../segments/segment-builder.md) 」，並確定您在建立區段時，使用在上一步驟中建立的新描述檔合併規則。

## 步驟6 —— 配置基於人的平台身份驗證 {#configure-authentication}

1. Log in to your Audience Manager account and go to  &gt; . **[!UICONTROL Administration]****[!UICONTROL Integrated Accounts]**如果您先前已設定與社交平台的整合，您應該會在此頁面中看到它。 否則，頁面為空。
   ![以人為本的整合](assets/pbd-config.png)
1. Click **[!UICONTROL Add Account]**.
1. 使用下 **[!UICONTROL People-Based Platform]** 拉式選單來選取您要設定整合的平台。
   ![以人為本的平台](assets/pbd-add.png)
1. 按一 **[!UICONTROL Confirm]** 下以重新導向至所選平台的驗證頁面。
1. 一旦您已驗證您的社交平台帳戶，就會將您重新導向至Audience Manager，您應該會在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下 **[!UICONTROL Confirm]**。
1. Audience manager會在頁面頂端顯示通知，讓您知道帳戶是否已成功新增。 The notification also allows you to add a contact email address to receive notifications when the social platform authentication is about to expire.

>[!IMPORTANT]
>
>A udience Manager handles the integration with social platforms through authentication tokens that expire after a certain amount of time. 如需如何續約過期代號的詳細資訊，請參閱驗證代號續約。

## 步驟7 —— 建立以人為本的目的地 {#create-destination}

1. Log in to your Audience Manager account, go to  &gt; , and click .**[!UICONTROL Audience Data]****[!UICONTROL Destinations]****[!UICONTROL Create Destination]**
1. 在該 **[!UICONTROL Basic Information]** 部分中，輸入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** 新資料源，並使用以下設定：
   * **[!UICONTROL Category]**:整合平台；
   * **[!UICONTROL Type]**:以人為本；
   * **[!UICONTROL Platform]**:選取您要傳送受眾細分至的以人為本的平台；
   * **[!UICONTROL Account]**:選取與所選平台相關聯的所需廣告商帳戶。
      ![create-destination](assets/pbd-create-destination.png)
1. Click **[!UICONTROL Next]**.
1. Choose the  that you want to set for this destination.**[!UICONTROL Data Export Labels]**
1. 在區 **[!UICONTROL Configuration]** 段中，選取包含雜湊資料來源的資料來源。
1. 在區 **[!UICONTROL Segment Mappings]** 段中，選取您要傳送至此目的地的區段。 這將是您在步驟5 —— 建立 [觀眾區段中建立的區段](people-based-destinations-workflow-offline.md#create-audience-segments)。
1. 保存目標。
