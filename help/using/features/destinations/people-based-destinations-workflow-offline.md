---
description: '本頁包含如何從僅限離線的客戶資料建立受眾區段，並將其傳送至以人物為基礎的目的地的逐步指引。  '
seo-description: '本頁包含如何從僅限離線的客戶資料建立受眾區段，並將其傳送至以人物為基礎的目的地的逐步指引。  '
seo-title: 工作流程 B - 以僅限離線資料為基礎的個人化
solution: Audience Manager
title: 工作流程 B - 以僅限離線資料為基礎的個人化
feature: 以人物為基礎的目的地
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
source-git-commit: 87c3169083f0dc66490e6a8c808e16371f1d78c0
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 6%

---

# 工作流程 B - 以僅限離線資料為基礎的個人化 {#workflow-b}

>[!IMPORTANT]
>本文包含的產品檔案旨在引導您完成此功能的設定與使用。 這裡沒有任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

本頁包含如何從僅限離線的客戶資料建立受眾區段，並將其傳送至以人物為基礎的目的地的逐步指引。

## 步驟1 — 將離線特徵上線{#step-1-onboard-traits}

在此案例中，建立受眾區段的第一步是將離線客戶資料帶入Audience Manager。

>[!IMPORTANT]
>
> 繼續之前，請確定您即將上線的客戶活動已在具有相應[已上線特徵](../traits/trait-and-segment-qualification-reference.md)的Audience Manager中定義。

無論您現有的Audience Manager客戶ID([DPUUIDs](../../reference/ids-in-aam.md))是否為雜湊電子郵件，您都必須對包含[DPUUIDs](../../reference/ids-in-aam.md)的資料來源執行特徵上線。

### 範例

您想要讓下表中的客戶ID符合對應已上線特徵ID的資格。 假設您的[DPUUIDs](../../reference/ids-in-aam.md)儲存在ID為999999的資料來源中，而您的Audience Manager資料來源ID為123。

| 客戶ID(DPUUID) | 已上線的特徵ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345,23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

若要讓上述範例中的客戶ID符合相應已上線特徵的資格，您必須上傳包含下列內容的[傳入資料檔案](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md):

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

檔案名稱如下：`ftp_dpm_999999_123_TIMESTAMP.sync.gz`。
如需檔案名稱結構的詳細資訊，請參閱傳入資料檔案的[Amazon S3名稱和檔案大小要求](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)。

## 步驟2 — 配置資料源設定{#configure-data-source-settings}

視您的[DPUUID](../../reference/ids-in-aam.md)是否為小寫雜湊電子郵件地址而定，您可能需要設定將儲存雜湊電子郵件地址的資料來源。

 

**方案1:您的 [](../../reference/ids-in-aam.md) DPUUID已經變成小寫、雜湊的電子郵件地址。**

在此情況下，您需要將對應的資料來源標示為：

1. 前往&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**。
1. 找到包含[DPUUIDs](../../reference/ids-in-aam.md)的資料來源，然後按一下。
1. 確保取消選中&#x200B;**[!UICONTROL Cannot be tied to personally identifiable information]**&#x200B;選項。
1. 儲存資料來源設定。

 

**方案2:您的 [](../../reference/ids-in-aam.md) DPUUID不是小寫、雜湊電子郵件地址。**

在此情況下，您需要建立新的跨裝置資料來源，以儲存雜湊電子郵件地址。 以下是操作方法：

1. 登入您的Audience Manager帳戶，前往&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**，然後按一下&#x200B;**[!UICONTROL Add New]**。
1. 輸入新資料源的&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
1. 在&#x200B;**[!UICONTROL ID Type]**&#x200B;下拉式選單中，選取&#x200B;**[!UICONTROL Cross Device]**。
1. 在&#x200B;**[!UICONTROL Data Source Settings]**&#x200B;區段中，選取&#x200B;**[!UICONTROL Inbound]**&#x200B;和&#x200B;**[!UICONTROL Outbound]**&#x200B;選項，並啟用&#x200B;**[!UICONTROL Share associated cross-device IDs in people-based destinations]**&#x200B;選項。
1. 使用下拉式功能表來選取此資料來源的&#x200B;**[!UICONTROL Emails(SHA256, lowercased)]**&#x200B;標籤。
   >[!IMPORTANT]
   >
   >此選項只會將資料來源標示為包含與該特定演算法雜湊的資料。 Audience Manager在此步驟不會雜湊資料。 請確定您打算儲存在此資料來源的電子郵件地址已使用[!DNL SHA256]演算法雜湊。 否則，您將無法將其用於[!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 請參閱[資料入門](people-based-destinations-prerequisites.md#data-onboarding) ，了解如何將離線資料帶入以人物為基礎的目的地Audience Manager的常見問題。

請觀看以下影片以觀看如何建立[!UICONTROL People-Based Destinations]資料來源的教學課程影片。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## 步驟3 — 透過檔案式ID同步{#match-ids-emails}，將DPUUID與雜湊電子郵件地址配對

>[!IMPORTANT]
>
> 此步驟僅適用於上述的[案例2](people-based-destinations-workflow-offline.md#configure-data-source-settings)。 如果您現有的[DPUUIDs](../../reference/ids-in-aam.md)已經有雜湊的電子郵件地址，請跳至[步驟4 — 建立分段的設定檔合併規則](#create-profile-merge-rule)。

假設您想要將步驟1範例中的現有[DPUUID](../../reference/ids-in-aam.md)與下表中的雜湊電子郵件地址（右欄）相符，並將雜湊電子郵件地址儲存在您於[步驟2 — 設定資料來源設定](#configure-data-source-settings)建立的新資料來源中。

提醒您，您現在有兩個資料來源：

| 資料來源ID | 資料來源內容 |
| -------------- | -------------------------- |
| 999999 | 現有DPUUID(CRM ID) |
| 987654 | 雜湊電子郵件地址 |

| DPUUID(CRM ID) | 電子郵件地址 | 雜湊電子郵件地址 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

在我們的範例中，您的[ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)將包含下列內容：

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

[ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)必須遵循此命名結構：

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

在上述範例中，檔案名稱如下所示：
`c2c_id_999999_987654_1560431657.sync`

[在這裡下載範例檔案](assets/c2c_id_999999_987654_1560431657.sync)。

建立ID同步檔案後，需將其上傳至[!DNL Amazon S3]貯體。 若要了解如何上傳ID同步檔案，請參閱[傳送批次資料至Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)。

## 步驟4 — 建立分段的設定檔合併規則{#create-profile-merge-rule}

下一步是建立新的合併規則，協助您建立要傳送至[!DNL People-Based Destinations]的對象區段。

1. 登入您的Audience Manager帳戶，然後前往&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**。
2. 按一下 [!UICONTROL Add New Rule].
3. 輸入配置檔案合併規則&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
4. 在&#x200B;**[!UICONTROL Profile Merge Rule Setup]**&#x200B;區段中，從&#x200B;**[!UICONTROL Cross-Device Options]**&#x200B;清單中選取&#x200B;**[!UICONTROL All Cross-Device Profiles]**&#x200B;規則。
5. 在&#x200B;**[!UICONTROL Cross-Device Profile Options]**清單中，選取您的特徵已上線所針對的資料來源。
   ![合併規則設定](assets/pbd-pmr.png)

## 步驟5 — 建立受眾區段{#create-audience-segments}

若要從僅限離線的資料建立新區段，請使用[區段產生器](../segments/segment-builder.md)，並務必使用您在建立區段時於先前步驟中建立的新設定檔合併規則。

## 步驟6 — 配置基於人員的平台身份驗證{#configure-authentication}

1. 登入您的Audience Manager帳戶，然後前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您先前已設定與社交平台的整合，您應會在此頁面中看到該整合。 否則，頁面為空。
   ![以人物為基礎的整合](assets/pbd-config.png)
1. 按一下 **[!UICONTROL Add Account]**.
1. 使用&#x200B;**[!UICONTROL People-Based Platform]**下拉式功能表，選取您要設定整合的平台。
   ![以人物為基礎的平台](assets/pbd-add.png)
1. 按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;以重新導向至所選平台的驗證頁面。
1. 一旦您通過社交平台帳戶驗證，系統會將您重新導向至Audience Manager，您應該會在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!UICONTROL Confirm]**。
1. Audience Manager會在頁面頂端顯示通知，告知您帳戶是否已成功新增。 此通知也可讓您新增聯絡人電子郵件地址，以在社交平台驗證即將過期時接收通知。

>[!IMPORTANT]
>
>Audience Manager會透過驗證Token處理與社交平台的整合，該Token會在一段時間後過期。 如需如何續約過期代號的詳細資訊，請參閱驗證代號續約。

## 步驟7 — 建立以人物為基礎的目的地{#create-destination}

1. 登入您的Audience Manager帳戶，前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**，然後按一下&#x200B;**[!UICONTROL Create Destination]**。
1. 在&#x200B;**[!UICONTROL Basic Information]**&#x200B;區段中，輸入新資料源的&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**，然後使用以下設定：
   * **[!UICONTROL Category]**:整合平台；
   * **[!UICONTROL Type]**:以人為本；
   * **[!UICONTROL Platform]**:選取您要將受眾區段傳送至的以人物為基礎的平台；
   * **[!UICONTROL Account]**:選取與所選平台相關聯的所需廣告商帳戶。
      ![create-destination](assets/pbd-create-destination.png)
1. 按一下 **[!UICONTROL Next]**.
1. 選擇要為此目標設定的&#x200B;**[!UICONTROL Data Export Labels]**。
1. 在&#x200B;**[!UICONTROL Configuration]**&#x200B;區段中，選取包含雜湊資料來源的資料來源。
1. 在&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;區段中，選取您要傳送至此目的地的區段。 這會是您在[步驟5 — 建立對象區段](people-based-destinations-workflow-offline.md#create-audience-segments)中建立的區段。
1. 儲存目的地。
