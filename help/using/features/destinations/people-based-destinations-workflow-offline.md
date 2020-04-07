---
description: '本頁包含逐步指引，說明如何從僅離線的客戶資料建立受眾細分，並將其傳送至以人為本的目標。  '
seo-description: '本頁包含逐步指引，說明如何從僅離線的客戶資料建立受眾細分，並將其傳送至以人為本的目標。  '
seo-title: 工作流程B —— 基於僅離線資料的個人化
solution: Audience Manager
title: 工作流程B —— 基於僅離線資料的個人化
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# 工作流程B —— 基於僅離線資料的個人化 {#workflow-b}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

本頁包含逐步指引，說明如何從僅離線的客戶資料建立受眾細分，並將其傳送至以人為本的目標。

## 步驟1 —— 板載離線特徵 {#step-1-onboard-traits}

在此案例中建立受眾細分的第一步，就是將您的離線客戶資料匯入Audience Manager。

>[!IMPORTANT]
>
> 在繼續之前，請確定您即將上線的客戶活動已在Audience Manager中定義，並具有對應的已 [上線特徵](../traits/trait-and-segment-qualification-reference.md)。

無論您現有的Audience Manager客戶ID([DPUUID](../../reference/ids-in-aam.md))是否是雜湊電子郵件，您都必須對包含您的 [DPUUID的資料來源執行特徵登入](../../reference/ids-in-aam.md)。

### 範例

您想要從下表中為對應的已登入特徵ID限定客戶ID。 我們假設您的 [DPUUID](../../reference/ids-in-aam.md) 儲存在ID為99999的資料來源中，而您的Audience Manager合作夥伴ID為123。

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

## 步驟2 —— 設定資料來源設定 {#configure-data-source-settings}

視您的 [DPUUID是小寫](../../reference/ids-in-aam.md) 、雜湊電子郵件地址而定，您可能需要設定將儲存雜湊電子郵件地址的資料來源。

 

**方案1:您的[DPUUID](../../reference/ids-in-aam.md)已是小寫、雜湊的電子郵件地址。**

在這種情況下，您需要將對應的資料源標籤為：

1. 轉到 **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**。
1. 尋找包含您的DPUUID的資 [料來源](../../reference/ids-in-aam.md)，然後按一下。
1. 請確定選項未 **[!UICONTROL Cannot be tied to personally identifiable information]** 勾選。
1. 儲存資料來源設定。

 

**方案2:您的[DPUUID](../../reference/ids-in-aam.md)不是小寫、雜湊的電子郵件地址。**

在這種情況下，您需要建立新的跨裝置資料來源，以儲存雜湊的電子郵件地址。 以下是如何做到的：

1. 登入您的Audience Manager帳戶並前往 **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**，然後按一下 **[!UICONTROL Add New]**。
1. 為新數 **[!UICONTROL Name]** 據源 **[!UICONTROL Description]** 輸入和。
1. 在下拉 **[!UICONTROL ID Type]** 式功能表中，選取 **[!UICONTROL Cross Device]**。
1. 在該節 **[!UICONTROL Data Source Settings]** 中，同時選擇和 **[!UICONTROL Inbound]** 選 **[!UICONTROL Outbound]** 項，並啟用選 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 項。
1. 使用下拉式選單來選取此 **[!UICONTROL Emails(SHA256, lowercased)]** 資料來源的標籤。
   >[!IMPORTANT]
   >
   >此選項僅將資料來源標示為包含使用特定演算法雜湊的資料。 Audience Manager不會在此步驟中雜湊資料。 請確定您打算儲存在此資料來源中的電子郵件地址已使用演算法雜湊 [!DNL SHA256] 過。 否則，您將無法使用它 [!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 如需 [](people-based-destinations-prerequisites.md#data-onboarding) 如何將離線資料匯入Audience Manager（以人為本的目的地）的常見問題，請參閱資料入門。

觀看以下影片，以取得如何建立資料來源的教學影片 [!UICONTROL People-Based Destinations]。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

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

建立ID同步檔案後，您必須將它上傳至儲 [!DNL Amazon S3] 存貯體。 如要瞭解如何上傳ID同步檔案，請參 [閱傳送批次資料至Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)。

## 步驟4 —— 建立分段的描述檔合併規則 {#create-profile-merge-rule}

下一步是建立新的合併規則，協助您建立要傳送給您的對象區段 [!DNL People-Based Destinations]。

1. 登入您的Audience Manager帳戶，然後前往 **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**。
2. 按一下 [!UICONTROL Add New Rule].
3. 輸入配置檔案合併規 **[!UICONTROL Name]** 則和 **[!UICONTROL Description]**。
4. 在區段 **[!UICONTROL Profile Merge Rule Setup]** 中，從清單 **[!UICONTROL All Cross-Device Profiles]** 中選取規 **[!UICONTROL Cross-Device Options]** 則。
5. 在清單 **[!UICONTROL Cross-Device Profile Options]** 中，選取您的特徵所針對的資料來源。
   ![merge-rule-setup](assets/pbd-pmr.png)

## 步驟5 —— 建立觀眾區段 {#create-audience-segments}

若要從僅離線資料建立新區段，請使用「區段產生器 [](../segments/segment-builder.md) 」，並確定您在建立區段時，使用在上一步驟中建立的新描述檔合併規則。

## 步驟6 —— 配置基於人的平台身份驗證 {#configure-authentication}

1. 登入您的Audience Manager帳戶，然後前往 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您先前已設定與社交平台的整合，您應該會在此頁面中看到它。 否則，頁面為空。
   ![以人為本的整合](assets/pbd-config.png)
1. 按一下 **[!UICONTROL Add Account]**.
1. 使用下 **[!UICONTROL People-Based Platform]** 拉式選單來選取您要設定整合的平台。
   ![以人為本的平台](assets/pbd-add.png)
1. 按一 **[!UICONTROL Confirm]** 下以重新導向至所選平台的驗證頁面。
1. 一旦您已驗證您的社交平台帳戶，就會將您重新導向至Audience Manager，您應該會在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下 **[!UICONTROL Confirm]**。
1. Audience Manager會在頁面頂端顯示通知，讓您知道帳戶是否已成功新增。 此通知也可讓您新增連絡人電子郵件地址，以在社交平台驗證即將到期時接收通知。

>[!IMPORTANT]
>
>Audience Manager會透過驗證Token處理與社交平台的整合，驗證Token會在特定時間後過期。 如需如何續約過期代號的詳細資訊，請參閱驗證代號續約。

## 步驟7 —— 建立以人為本的目的地 {#create-destination}

1. 登入您的Audience Manager帳戶，前往 **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**，然後按一下 **[!UICONTROL Create Destination]**。
1. 在該 **[!UICONTROL Basic Information]** 部分中，輸入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** 新資料源，並使用以下設定：
   * **[!UICONTROL Category]**:整合平台；
   * **[!UICONTROL Type]**:以人為本；
   * **[!UICONTROL Platform]**:選取您要傳送受眾細分至的以人為本的平台；
   * **[!UICONTROL Account]**:選取與所選平台相關聯的所需廣告商帳戶。
      ![create-destination](assets/pbd-create-destination.png)
1. 按一下 **[!UICONTROL Next]**.
1. 選擇 **[!UICONTROL Data Export Labels]** 要為此目標設定的。
1. 在區 **[!UICONTROL Configuration]** 段中，選取包含雜湊資料來源的資料來源。
1. 在區 **[!UICONTROL Segment Mappings]** 段中，選取您要傳送至此目的地的區段。 這將是您在步驟5 —— 建立 [觀眾區段中建立的區段](people-based-destinations-workflow-offline.md#create-audience-segments)。
1. 保存目標。
