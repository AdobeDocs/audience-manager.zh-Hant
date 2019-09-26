---
description: '本頁包含如何結合離線CRM資料和您在Audience manager中已擁有的行為資料以建立新受眾細分的逐步指引，然後將這些受眾細分傳送至以人為本的目標。  '
seo-description: '本頁包含如何結合離線CRM資料和您在Audience manager中已擁有的行為資料以建立新受眾細分的逐步指引，然後將這些受眾細分傳送至以人為本的目標。   '
seo-title: 工作流程A —— 基於所有線上活動和離線資料的個人化
solution: Audience Manager
title: 工作流程A —— 基於所有線上活動和離線資料的個人化
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# 工作流程A —— 基於所有線上活動和離線資料的個人化 {#workflow-a}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

本頁包含如何結合離線資料與您在Audience manager中已擁有的行為資料以建立新受眾細分的逐步指引，然後將這些受眾細分傳送至 [!DNL CRM][!DNL People-Based Destinations]。

## 步驟1 —— 設定資料來源設定 {#configure-data-source-settings}

視您的 [DPUUID是小寫](../../reference/ids-in-aam.md) 、雜湊電子郵件地址而定，您可能需要設定將儲存雜湊電子郵件地址的資料來源。

 

**方案1:您的[DPUUID](../../reference/ids-in-aam.md)已是小寫、雜湊的電子郵件地址。**

在這種情況下，您需要將對應的資料源標籤為：

1. 轉到 [!UICONTROL Audience Data] -&gt; [!UICONTROL Data Sources]。
1. 尋找包含您的DPUUID的資 [料來源](../../reference/ids-in-aam.md)，然後按一下。
1. 在下拉 **[!UICONTROL ID Type]** 式功能表中，選取 **[!UICONTROL Cross Device]**。
1. 請確定選項未 [!UICONTROL Cannot be tied to personally identifiable information] 勾選。
1. 在該節 **[!UICONTROL Data Source Settings]** 中，同時選擇和 **[!UICONTROL Inbound]** 選 **[!UICONTROL Outbound]** 項，並啟用選 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 項。
1. 使用下拉式選單來選取此 **[!UICONTROL Emails(SHA256, lowercased)]** 資料來源的標籤。
   >[!IMPORTANT]
   >
   >此選項僅將資料來源標示為包含使用特定演算法雜湊的資料。 Audience manager不會在此步驟中雜湊資料。 請確定您打算儲存在此資料來源中的電子郵件地址已使用演算法雜湊 [!DNL SHA256] 過。 否則，您將無法使用它 [!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. 儲存資料來源設定。

 

**方案2:您的[DPUUID](../../reference/ids-in-aam.md)不是小寫、雜湊的電子郵件地址。**

在這種情況下，您需要建立新的跨裝置資料來源，以儲存雜湊的電子郵件地址。 以下是如何做到的：

1. 登入您的Audience manager帳戶並前往 **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**，然後按一下 **[!UICONTROL Add New]**。
1. Enter a [!UICONTROL Name] and [!UICONTROL Description] for your new data source.
1. 在下拉 **[!UICONTROL ID Type]** 式功能表中，選取 **[!UICONTROL Cross Device]**。
1. In the  section, select both the  and  options, and enable the  option.**[!UICONTROL Data Source Settings]****[!UICONTROL Inbound]****[!UICONTROL Outbound]****[!UICONTROL Share associated cross-device IDs in people-based destinations]**
1. Use the drop-down menu to select the  label for this data source.**[!UICONTROL Emails(SHA256, lowercased)]**
   >[!IMPORTANT]
   >
   >This option only labels the data source as containing data hashed with that specific algorithm. Audience Manager does not hash the data at this step. Make sure the email addresses that you plan on storing in this data source are already hashed with the  algorithm. [!DNL SHA256]Otherwise, you won't be able to use it for .[!DNL People-Based Destinations]

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Save the data source settings.

>[!NOTE]
>
> See Data Onboarding for frequently asked questions about how you should bring your offline data into Audience Manager for People-Based Destinations.[](people-based-destinations-prerequisites.md#data-onboarding)

## Step 2 - Match DPUUIDs to Hashed Email Addresses via File-Based ID Synchronization {#match-ids-emails}

>[!IMPORTANT]
>
> This step only applies to [Scenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) described above. If your existing DPUUIDs are already hashed email addresses, skip to Step 3 - Create a Profile Merge Rule for Segmentation.[](../../reference/ids-in-aam.md)[](people-based-destinations-workflow-combined.md#create-merge-rule)

Let's say you want to match your existing DPUUIDs to the hashed email addresses from the table below (right column), and store the hashed email addresses in the new data source that you created at Step 1 - Configure Data Source Settings.[](../../reference/ids-in-aam.md)[](people-based-destinations-workflow-combined.md#configure-data-source-settings)

| DPUUID(CRM ID) | 電子郵件地址 | Hashed email address |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

您最多可以將10個雜湊電子郵件地址連結至單一 [DPUUID](../../reference/ids-in-aam.md)。 若要這麼做，請在同步檔案中以逗號分隔雜湊的電子郵件地址。

在我們的範例中，您現在有兩個資料來源。

| 資料來源ID | 資料來源內容 |
| -------------- | -------------------------- |
| 999999 | 現有DPUUID(CRM ID) |
| 987654 | 雜湊的電子郵件地址 |

 

您的 [ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ，會包含下列內容：

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

## 步驟3 —— 建立分段的描述檔合併規則 {#create-merge-rule}

下一步是建立新的合併規則，協助您建立對象區段以傳送至以人員為基礎的目的地。

>[!IMPORTANT]
>
> 如果您已使用或選項定義規 [!UICONTROL Current Authenticated Profiles] 則， [!UICONTROL Last Authenticated Profiles] 可跳至步驟4 - [建立對象區段](people-based-destinations-workflow-combined.md#create-audience-segments)。

1. 登入您的Audience manager帳戶，然後前往 **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Profile Merge Rules]**。
1. Click **[!UICONTROL Add New Rule]**.
1. 輸入配置檔案合併規 **[!UICONTROL Name]** 則和 **[!UICONTROL Description]**。
1. 在節 **[!UICONTROL Profile Merge Rule Setup]** 中，選擇 **[!UICONTROL Current Authenticated Profiles]** 或選 **[!UICONTROL Last Authenticated Profiles]** 項。
1. 在清 **[!UICONTROL Cross-Device Profile Options]** 單中，選取您要執行區段的資料來源。 這些應是包含您現有DPUUID的資 [料來源](../../reference/ids-in-aam.md)。

## 步驟4 —— 建立觀眾區段 {#create-audience-segments}

若要建立新的讀者區段，請使用「區 [段產生器](../segments/segment-builder.md)」。 如果您有要傳送給的現有對象區段，請跳至 [!DNL People-Based Destinations]步驟5 [-設定以人員為基礎的平台驗證](people-based-destinations-workflow-combined.md#configure-authentication)。

## 步驟5 —— 配置基於人的平台身份驗證 {#configure-authentication}

1. 登入您的Audience manager帳戶，然後前往 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。 如果您先前已設定與社交平台的整合，您應該會在此頁面中看到它。 否則，頁面為空。
   ![以人為本的整合](assets/pbd-config.png)
1. Click **[!UICONTROL Add Account]**.
1. 使用下 **[!UICONTROL People-Based Platform]** 拉式選單來選取您要設定整合的平台。
   ![以人為本的平台](assets/pbd-add.png)
1. Click  to be redirected to the authentication page of the selected platform.**[!UICONTROL Confirm]**
1. Once you've authenticated to your social platform account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click .**[!UICONTROL Confirm]**
1. Audience Manager displays a notification at the top of the page to let you know whether the account was successfully added. The notification also allows you to add a contact email address to receive notifications when the social platform authentication is about to expire.

>[!IMPORTANT]
>
>A udience Manager handles the integration with social platforms through authentication tokens that expire after a certain amount of time. See Authentication Token Renewal for details on how to renew the expired tokens.

## Step 6 - Create a People-Based Destination {#create-destination}

1. Log in to your Audience Manager account, go to  &gt; , and click .**[!UICONTROL Audience Data]****[!UICONTROL Destinations]****[!UICONTROL Create Destination]**
1. 在該 **[!UICONTROL Basic Information]** 部分中，輸入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** 新資料源，並使用以下設定：
   * **[!UICONTROL Category]**:整合平台；
   * **[!UICONTROL Type]**: People-Based;
   * **[!UICONTROL Platform]**: select the people-based platform that you want to send audience segments to;
   * **[!UICONTROL Account]**: select the desired advertiser account associated with the selected platform.
      ![create-destination](assets/pbd-create-destination.png)
1. Click **[!UICONTROL Next]**.
1. Choose the  that you want to set for this destination.**[!UICONTROL Data Export Labels]**
1. 在區 **[!UICONTROL Configuration]** 段中，選取包含雜湊資料來源的資料來源。
1. In the  section, select the segments that you want to send to this destination. **[!UICONTROL Segment Mappings]** This would be the segments that you created at Step 4 - Create Audience Segments.[](people-based-destinations-workflow-combined.md#create-audience-segments)
1. 保存目標。
