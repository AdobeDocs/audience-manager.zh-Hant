---
description: '本頁包含逐步指引，說明如何從僅離線的客戶資料建立受眾細分，並將其傳送至以人為本的目標。  '
seo-description: '本頁包含逐步指引，說明如何從僅離線的客戶資料建立受眾細分，並將其傳送至以人為本的目標。  '
seo-title: 工作流程B —— 基於僅離線資料的個人化
solution: Audience Manager
title: 工作流程B —— 基於僅離線資料的個人化
translation-type: tm+mt
source-git-commit: ad9c077f538759e195a83d47e0ef36ccffa25c7e

---


# 工作流程B —— 基於僅離線資料的個人化 {#workflow-b}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

本頁包含逐步指引，說明如何從僅離線的客戶資料建立受眾細分，並將其傳送至以人為本的目標。

## 步驟1 —— 板載離線特徵 {#step-1-onboard-traits}

在此案例中建立受眾細分的第一步，就是將您的離線客戶資料匯入Audience Manager。

>[!IMPORTANT]
>
> 在繼續之前，請確定您即將上線的客戶活動已在Audience manager中定義，並具有對應的已 [上線特徵](../traits/trait-qualification-reference.md)。

無論您現有的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))是否是雜湊電子郵件，您都必須對包含您的 [DPUUID的資料來源執行特徵登入](../../reference/ids-in-aam.md)。

### 範例

You want to qualify the customer IDs from the table below for the corresponding onboarded trait IDs. 我們假設您的 [DPUUID](../../reference/ids-in-aam.md) 儲存在ID為99999的資料來源中，而您的Audience Manager合作夥伴ID為123。

| Customer ID (DPUUID) | Onboarded Trait ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />
To qualify the customer IDs in the example above for the corresponding onboarded traits, you must upload an [inbound data file](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) with the following contents:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

The file name would look like this: .
`ftp_dpm_999999_123_TIMESTAMP.sync.gz`See Amazon S3 Name and File Size Requirements for Inbound Data Files for detailed information on the file name structure.[](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

## 步驟2 —— 設定資料來源設定 {#configure-data-source-settings}

Depending on whether your DPUUIDs are lowercase, hashed email addresses, you might need to configure the data source that will store the hashed email addresses.[](../../reference/ids-in-aam.md)

 

**Scenario 1: your DPUUIDs are already lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)**

In this case, you need to need to label the corresponding data source as such:

1. Go to  -&gt; .**[!UICONTROL Audience Data]****[!UICONTROL Data Sources]**
1. Find the data source that contains your DPUUIDs, and click it.[](../../reference/ids-in-aam.md)
1. 請確定選項未 **[!UICONTROL Cannot be tied to personally identifiable information]** 勾選。
1. 儲存資料來源設定。

 

**Scenario 2: your DPUUIDs are not lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)**

In this case, you need to create a new cross-device data source that will store your hashed email addresses. 以下是如何做到的：

1. 登入您的Audience manager帳戶並前往 **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**，然後按一下 **[!UICONTROL Add New]**。
1. 為新數 **[!UICONTROL Name]** 據源 **[!UICONTROL Description]** 輸入和。
1. 在下拉 **[!UICONTROL ID Type]** 式功能表中，選取 **[!UICONTROL Cross Device]**。
1. 在該節 **[!UICONTROL Data Source Settings]** 中，同時選擇和 **[!UICONTROL Inbound]** 選 **[!UICONTROL Outbound]** 項，並啟用選 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 項。
1. 使用下拉式選單來選取此 **[!UICONTROL Emails(SHA256, lowercased)]** 資料來源的標籤。
   >[!IMPORTANT]
   >
   >此選項僅將資料來源標示為包含使用特定演算法雜湊的資料。 Audience manager不會在此步驟中雜湊資料。 請確定您打算儲存在此資料來源中的電子郵件地址已使用演算法雜湊 [!DNL SHA256] 過。 否則，您將無法使用它 [!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 如需 [](people-based-destinations-prerequisites.md#data-onboarding) 如何將離線資料匯入Audience Manager（以人為本的目的地）的常見問題，請參閱資料入門。

## 步驟3 —— 透過檔案式ID同步化，將DPUUID與雜湊的電子郵件地址相符 {#match-ids-emails}

>[!IMPORTANT]
>
> 此步驟僅適用於上 [述的方案](people-based-destinations-workflow-offline.md#configure-data-source-settings) 2。 如果您的現 [有DPUUID](../../reference/ids-in-aam.md) 已雜湊電子郵件地址，請跳至 [步驟4 —— 建立區段的描述檔合併規則](#create-profile-merge-rule)。

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

Once you've created your ID synchronization file, you need to upload it to an  bucket. [!DNL Amazon S3]To learn how to upload ID synchronization files, see Send Batch Data to Audience Manager.[](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)

## Step 4 - Create a Profile Merge Rule for Segmentation {#create-profile-merge-rule}

The next step is creating a new merge rule that will help you create the audience segments to send to your .[!DNL People-Based Destinations]

1. Log in to your Audience Manager account and go to  -&gt; .**[!UICONTROL Audience Data]****[!UICONTROL Profile Merge Rules]**
2. 按一下 [!UICONTROL Add New Rule].
3. Enter a profile merge rule  and .**[!UICONTROL Name]****[!UICONTROL Description]**
4. In the  section, select the  rule from the  list.**[!UICONTROL Profile Merge Rule Setup]****[!UICONTROL All Cross-Device Profiles]****[!UICONTROL Cross-Device Options]**
5. In the  list, select the data source that your traits are onboarded against.**[!UICONTROL Cross-Device Profile Options]**
   ![merge-rule-setup](assets/pbd-pmr.png)

## Step 5 - Create Audience Segments {#create-audience-segments}

To create new segments from offline-only data, use the Segment Builder and make sure you use the new profile merge rule that you created in the previous step when creating the segment.[](../segments/segment-builder.md)

## Step 6 - Configure People-Based Platform Authentication {#configure-authentication}

1. 登入您的Audience manager帳戶，然後前往 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。 如果您先前已設定與社交平台的整合，您應該會在此頁面中看到它。 Otherwise, the page is empty.
   ![以人為本的整合](assets/pbd-config.png)
1. Click **[!UICONTROL Add Account]**.
1. 使用下 **[!UICONTROL People-Based Platform]** 拉式選單來選取您要設定整合的平台。
   ![以人為本的平台](assets/pbd-add.png)
1. 按一 **[!UICONTROL Confirm]** 下以重新導向至所選平台的驗證頁面。
1. 一旦您已驗證您的社交平台帳戶，就會將您重新導向至Audience Manager，您應該會在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下 **[!UICONTROL Confirm]**。
1. Audience manager會在頁面頂端顯示通知，讓您知道帳戶是否已成功新增。 此通知也可讓您新增連絡人電子郵件地址，以在社交平台驗證即將到期時接收通知。

>[!IMPORTANT]
>
>Audience manager會透過驗證Token處理與社交平台的整合，驗證Token會在特定時間後過期。 如需如何續約過期代號的詳細資訊，請參閱驗證代號續約。

## 步驟7 —— 建立以人為本的目的地 {#create-destination}

1. 登入您的Audience manager帳戶，前往 **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]**，然後按一下 **[!UICONTROL Create Destination]**。
1. 在該 **[!UICONTROL Basic Information]** 部分中，輸入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** 新資料源，並使用以下設定：
   * **[!UICONTROL Category]**:整合平台；
   * **[!UICONTROL Type]**:以人為本；
   * **[!UICONTROL Platform]**:選取您要傳送受眾細分至的以人為本的平台；
   * **[!UICONTROL Account]**:選取與所選平台相關聯的所需廣告商帳戶。
      ![create-destination](assets/pbd-create-destination.png)
1. Click **[!UICONTROL Next]**.
1. 選擇 **[!UICONTROL Data Export Labels]** 要為此目標設定的。
1. 在區 **[!UICONTROL Configuration]** 段中，選取包含雜湊資料來源的資料來源。
1. 在區 **[!UICONTROL Segment Mappings]** 段中，選取您要傳送至此目的地的區段。 這將是您在步驟5 —— 建立 [觀眾區段中建立的區段](people-based-destinations-workflow-offline.md#create-audience-segments)。
1. 保存目標。
