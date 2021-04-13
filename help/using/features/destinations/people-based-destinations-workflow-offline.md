---
description: '本頁包含逐步指引，說明如何從僅離線的客戶資料建立受眾細分，並將其傳送至以人為本的目標。  '
seo-description: '本頁包含逐步指引，說明如何從僅離線的客戶資料建立受眾細分，並將其傳送至以人為本的目標。  '
seo-title: 工作流程 B - 以僅限離線資料為基礎的個人化
solution: Audience Manager
title: 工作流程 B - 以僅限離線資料為基礎的個人化
feature: 以人為本的目的地
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 6%

---

# 工作流程 B - 以僅限離線資料為基礎的個人化 {#workflow-b}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

本頁包含逐步指引，說明如何從僅離線的客戶資料建立受眾細分，並將其傳送至以人為本的目標。

## 步驟1 —— 板載離線特徵{#step-1-onboard-traits}

在此案例中建立受眾細分的第一步是將離線客戶資料帶入Audience Manager。

>[!IMPORTANT]
>
> 在繼續之前，請確定您即將上線的客戶活動已定義在具有相應[已登錄特徵](../traits/trait-and-segment-qualification-reference.md)的Audience Manager中。

無論您現有的Audience Manager客戶ID([DPUUIDs](../../reference/ids-in-aam.md))是否是雜湊電子郵件，您都必須對包含[DPUUIDs](../../reference/ids-in-aam.md)的資料來源執行特徵上線。

### 範例

您想要從下表中為對應的已登入特徵ID限定客戶ID。 假設您的[DPUUIDs](../../reference/ids-in-aam.md)儲存在ID為999999的資料來源中，而您的Audience Manager合作夥伴ID為123。

| 客戶ID(DPUUID) | 已登入特徵ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345、23456 |
| 67412682083419957253870443620307584 | 郵編：45678 |
| 89159024796760343733111170764602676593 | 11223、93342、27341 |

<br />

若要將上述範例中的客戶ID限定為對應的已登入特徵，您必須上傳包含下列內容的[傳入資料檔案](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md):

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

檔案名如下所示：`ftp_dpm_999999_123_TIMESTAMP.sync.gz`。
有關檔案名結構的詳細資訊，請參閱[AmazonS3 Name and File Size Requirements for Inbound Data Files](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)。

## 步驟2 —— 配置資料源設定{#configure-data-source-settings}

視您的[DPUUIDs](../../reference/ids-in-aam.md)是否為小寫雜湊電子郵件地址而定，您可能需要設定將儲存雜湊電子郵件地址的資料來源。

 

**方案1:您的 [](../../reference/ids-in-aam.md) DPUUID已是小寫、雜湊的電子郵件地址。**

在這種情況下，您需要將對應的資料源標籤為：

1. 前往&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**。
1. 尋找包含[DPUUIDs](../../reference/ids-in-aam.md)的資料來源，然後按一下。
1. 請確定未選中&#x200B;**[!UICONTROL Cannot be tied to personally identifiable information]**&#x200B;選項。
1. 儲存資料來源設定。

 

**方案2:您的 [](../../reference/ids-in-aam.md) DPUUID不是小寫、雜湊的電子郵件地址。**

在這種情況下，您需要建立新的跨裝置資料來源，以儲存雜湊的電子郵件地址。 以下是如何做到的：

1. 登入您的Audience Manager帳戶並前往&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**，然後按一下&#x200B;**[!UICONTROL Add New]**。
1. 為新資料源輸入&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
1. 在&#x200B;**[!UICONTROL ID Type]**&#x200B;下拉菜單中，選擇&#x200B;**[!UICONTROL Cross Device]**。
1. 在&#x200B;**[!UICONTROL Data Source Settings]**&#x200B;部分，選擇&#x200B;**[!UICONTROL Inbound]**&#x200B;和&#x200B;**[!UICONTROL Outbound]**&#x200B;選項，並啟用&#x200B;**[!UICONTROL Share associated cross-device IDs in people-based destinations]**&#x200B;選項。
1. 使用下拉式選單來選取此資料來源的&#x200B;**[!UICONTROL Emails(SHA256, lowercased)]**&#x200B;標籤。
   >[!IMPORTANT]
   >
   >此選項僅將資料來源標示為包含使用特定演算法雜湊的資料。 Audience Manager不會在此步驟中對資料進行雜湊處理。 請確定您打算儲存在此資料來源中的電子郵件地址已使用[!DNL SHA256]演算法雜湊。 否則，您將無法將它用於[!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 如需如何將離線資料匯入Audience Manager人員型目的地的常見問題，請參閱[資料入門](people-based-destinations-prerequisites.md#data-onboarding)。

觀看以下視訊，以取得如何建立[!UICONTROL People-Based Destinations]資料來源的教學課程影片。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## 步驟3 —— 透過檔案式ID同步化將DPUUID與雜湊的電子郵件地址比對{#match-ids-emails}

>[!IMPORTANT]
>
> 此步驟僅適用於上述的[Scenario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings)。 如果您現有的[DPUUIDs](../../reference/ids-in-aam.md)已雜湊電子郵件地址，請跳至[步驟4 —— 建立區段的描述檔合併規則](#create-profile-merge-rule)。

假設您想要將步驟1範例中的現有[DPUUID](../../reference/ids-in-aam.md)與下表中的雜湊電子郵件地址（右欄）比對，並將雜湊電子郵件地址儲存在您在[步驟2 —— 設定資料來源設定](#configure-data-source-settings)所建立的新資料來源中。

提醒您，您現在有兩個資料來源：

| 資料來源ID | 資料來源內容 |
| -------------- | -------------------------- |
| 郵編：999999 | 現有DPUUID(CRM ID) |
| 郵編：987654 | 雜湊的電子郵件地址 |

| DPUUID(CRM ID) | 電子郵件地址 | 雜湊電子郵件地址 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083419957253870443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111170764602676593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

在我們的示例中，您的[ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)將包含以下內容：

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

[ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)必須遵循以下命名結構：

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

在上述範例中，檔案名稱會如下所示：
`c2c_id_999999_987654_1560431657.sync`

[在這裡下載範例檔案](assets/c2c_id_999999_987654_1560431657.sync)。

建立ID同步檔案後，您必須將它上傳至[!DNL Amazon S3]儲存貯體。 要瞭解如何上傳ID同步檔案，請參閱[將批次資料發送到Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)。

## 步驟4 —— 建立區段的描述檔合併規則{#create-profile-merge-rule}

下一步是建立新的合併規則，協助您建立要傳送至[!DNL People-Based Destinations]的對象區段。

1. 登入您的Audience Manager帳戶並前往&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**。
2. 按一下 [!UICONTROL Add New Rule].
3. 輸入配置檔案合併規則&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
4. 在&#x200B;**[!UICONTROL Profile Merge Rule Setup]**&#x200B;部分，從&#x200B;**[!UICONTROL Cross-Device Options]**&#x200B;清單中選擇&#x200B;**[!UICONTROL All Cross-Device Profiles]**&#x200B;規則。
5. 在&#x200B;**[!UICONTROL Cross-Device Profile Options]**清單中，選取您的特徵所針對的資料來源。
   ![merge-rule-setup](assets/pbd-pmr.png)

## 步驟5 —— 建立對象區段{#create-audience-segments}

若要從僅離線資料建立新區段，請使用「區段產生器」[，並確定您在建立區段時使用在上一步驟中建立的新描述檔合併規則。](../segments/segment-builder.md)

## 步驟6 —— 配置基於人的平台身份驗證{#configure-authentication}

1. 登入您的Audience Manager帳戶，並前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您先前已設定與社交平台的整合，您應該會在此頁面中看到它。 否則，頁面為空。
   ![以人為本的整合](assets/pbd-config.png)
1. 按一下 **[!UICONTROL Add Account]**.
1. 使用&#x200B;**[!UICONTROL People-Based Platform]**下拉式功能表，選取您要設定整合的平台。
   ![以人為本的平台](assets/pbd-add.png)
1. 按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;以重新導向至所選平台的驗證頁面。
1. 一旦您已驗證您的社交平台帳戶，就會將您重新導向至Audience Manager，您應該在該處看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!UICONTROL Confirm]**。
1. Audience Manager會在頁面頂端顯示通知，讓您知道帳戶是否已成功新增。 此通知也可讓您新增連絡人電子郵件地址，以在社交平台驗證即將到期時接收通知。

>[!IMPORTANT]
>
>Audience Manager會透過驗證Token處理與社交平台的整合，這些Token會在特定時間後過期。 如需如何續約過期代號的詳細資訊，請參閱驗證代號續約。

## 步驟7 —— 建立基於人的目標{#create-destination}

1. 登入您的Audience Manager帳戶，前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**，然後按一下&#x200B;**[!UICONTROL Create Destination]**。
1. 在&#x200B;**[!UICONTROL Basic Information]**&#x200B;區段中，為新資料源輸入&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]** ，並使用以下設定：
   * **[!UICONTROL Category]**:整合平台；
   * **[!UICONTROL Type]**:以人為本；
   * **[!UICONTROL Platform]**:選取您要傳送受眾細分至的以人為本的平台；
   * **[!UICONTROL Account]**:選取與所選平台相關聯的所需廣告商帳戶。
      ![create-destination](assets/pbd-create-destination.png)
1. 按一下 **[!UICONTROL Next]**.
1. 選擇要為此目標設定的&#x200B;**[!UICONTROL Data Export Labels]**。
1. 在&#x200B;**[!UICONTROL Configuration]**&#x200B;區段中，選取包含雜湊資料來源的資料來源。
1. 在&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;區段中，選取您要傳送至此目的地的區段。 這將是您在[步驟5 —— 建立對象區段](people-based-destinations-workflow-offline.md#create-audience-segments)中建立的區段。
1. 保存目標。
