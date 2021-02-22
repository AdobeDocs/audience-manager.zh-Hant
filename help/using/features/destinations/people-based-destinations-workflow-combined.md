---
description: '本頁包含如何結合離線CRM資料和您在Audience Manager中已擁有的行為資料以建立新受眾細分的逐步指引，然後將這些受眾細分傳送至以人為本的目標。  '
seo-description: '本頁包含如何結合離線CRM資料和您在Audience Manager中已擁有的行為資料以建立新受眾細分的逐步指引，然後將這些受眾細分傳送至以人為本的目標。   '
seo-title: 工作流程 A - 以所有線上活動和離線資料為基礎的個人化
solution: Audience Manager
title: 工作流程 A - 以所有線上活動和離線資料為基礎的個人化
feature: 以人物為基礎的目的地
translation-type: tm+mt
source-git-commit: 6e3a06da8149c91a9192b5b3ee582e46fbb1790c
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 7%

---


# 工作流程 A - 以所有線上活動和離線資料為基礎的個人化 {#workflow-a}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

本頁包含如何結合離線[!DNL CRM]資料與您在Audience Manager中已擁有的行為資料以建立新受眾區段的逐步指引，然後將這些受眾區段傳送至[!DNL People-Based Destinations]。

## 步驟1 —— 配置資料源設定{#configure-data-source-settings}

視您的[DPUUIDs](../../reference/ids-in-aam.md)是否為小寫雜湊電子郵件地址而定，您可能需要設定將儲存雜湊電子郵件地址的資料來源。

 

**方案1:您的 [](../../reference/ids-in-aam.md) DPUUID已是小寫、雜湊的電子郵件地址。**

在這種情況下，您需要將對應的資料源標籤為：

1. 前往[!UICONTROL Audience Data] -> [!UICONTROL Data Sources]。
1. 尋找包含[DPUUIDs](../../reference/ids-in-aam.md)的資料來源，然後按一下。
1. 在&#x200B;**[!UICONTROL ID Type]**&#x200B;下拉菜單中，選擇&#x200B;**[!UICONTROL Cross Device]**。
1. 請確定未選中[!UICONTROL Cannot be tied to personally identifiable information]選項。
1. 在&#x200B;**[!UICONTROL Data Source Settings]**&#x200B;部分，選擇&#x200B;**[!UICONTROL Inbound]**&#x200B;和&#x200B;**[!UICONTROL Outbound]**&#x200B;選項，並啟用&#x200B;**[!UICONTROL Share associated cross-device IDs in people-based destinations]**&#x200B;選項。
1. 使用下拉式選單來選取此資料來源的&#x200B;**[!UICONTROL Emails(SHA256, lowercased)]**&#x200B;標籤。
   >[!IMPORTANT]
   >
   >此選項僅將資料來源標示為包含使用特定演算法雜湊的資料。 Audience Manager不會在此步驟中雜湊資料。 請確定您打算儲存在此資料來源中的電子郵件地址已使用[!DNL SHA256]演算法雜湊。 否則，您將無法將它用於[!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. 儲存資料來源設定。

 

**方案2:您的 [](../../reference/ids-in-aam.md) DPUUID不是小寫、雜湊的電子郵件地址。**

在這種情況下，您需要建立新的跨裝置資料來源，以儲存雜湊的電子郵件地址。 以下是如何做到的：

1. 登入您的Audience Manager帳戶並前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**，然後按一下&#x200B;**[!UICONTROL Add New]**。
1. 為新資料源輸入[!UICONTROL Name]和[!UICONTROL Description]。
1. 在&#x200B;**[!UICONTROL ID Type]**&#x200B;下拉菜單中，選擇&#x200B;**[!UICONTROL Cross Device]**。
1. 在&#x200B;**[!UICONTROL Data Source Settings]**&#x200B;部分，選擇&#x200B;**[!UICONTROL Inbound]**&#x200B;和&#x200B;**[!UICONTROL Outbound]**&#x200B;選項，並啟用&#x200B;**[!UICONTROL Share associated cross-device IDs in people-based destinations]**&#x200B;選項。
1. 使用下拉式選單來選取此資料來源的&#x200B;**[!UICONTROL Emails(SHA256, lowercased)]**&#x200B;標籤。
   >[!IMPORTANT]
   >
   >此選項僅將資料來源標示為包含使用特定演算法雜湊的資料。 Audience Manager不會在此步驟中雜湊資料。 請確定您打算儲存在此資料來源中的電子郵件地址已使用[!DNL SHA256]演算法雜湊。 否則，您將無法將它用於[!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. 儲存資料來源設定。

觀看以下視訊，以取得如何建立[!UICONTROL People-Based Destinations]資料來源的教學課程影片。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> 如需如何將離線資料匯入Audience Manager以進行人員型目標的常見問題，請參閱[資料入門](people-based-destinations-prerequisites.md#data-onboarding)。

## 步驟2 —— 透過檔案式ID同步化將DPUUID與雜湊的電子郵件地址比對{#match-ids-emails}

>[!IMPORTANT]
>
> 此步驟僅適用於上述的[Scenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings)。 如果您現有的[DPUUIDs](../../reference/ids-in-aam.md)已雜湊電子郵件地址，請跳至[步驟3 —— 建立區段的描述檔合併規則](people-based-destinations-workflow-combined.md#create-merge-rule)。

假設您想要將現有的[DPUUIDs](../../reference/ids-in-aam.md)與下表中的雜湊電子郵件地址（右欄）相符，並將雜湊電子郵件地址儲存在您在[步驟1 —— 設定資料來源設定](people-based-destinations-workflow-combined.md#configure-data-source-settings)所建立的新資料來源中。

| DPUUID(CRM ID) | 電子郵件地址 | 雜湊電子郵件地址 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083419957253870443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111170764602676593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

您最多可以將10個雜湊電子郵件地址連結至單一[DPUUID](../../reference/ids-in-aam.md)。 為此，請在同步檔案內使用`<TAB>`分隔散列電子郵件地址。

在我們的範例中，您現在有兩個資料來源。

| 資料來源ID | 資料來源內容 |
| -------------- | -------------------------- |
| 郵編：999999 | 現有DPUUID(CRM ID) |
| 郵編：987654 | 雜湊的電子郵件地址 |

 

您的[ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)將包含以下內容：

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

建立ID同步檔案後，您必須將它上傳至[!DNL Amazon S3]儲存貯體。 若要瞭解如何上傳ID同步檔案，請參閱[傳送批次資料至Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)。

## 步驟3 —— 建立區段的描述檔合併規則{#create-merge-rule}

下一步是建立新的合併規則，協助您建立對象區段以傳送至以人員為基礎的目的地。

>[!IMPORTANT]
>
> 如果您已使用[!UICONTROL Current Authenticated Profiles]或[!UICONTROL Last Authenticated Profiles]選項定義規則，則可跳至[步驟4 —— 建立對象區段](people-based-destinations-workflow-combined.md#create-audience-segments)。

1. 登入您的Audience Manager帳戶並前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**。
1. 按一下 **[!UICONTROL Add New Rule]**.
1. 輸入配置檔案合併規則&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
1. 在&#x200B;**[!UICONTROL Profile Merge Rule Setup]**&#x200B;部分，選擇&#x200B;**[!UICONTROL Current Authenticated Profiles]**&#x200B;或&#x200B;**[!UICONTROL Last Authenticated Profiles]**&#x200B;選項。
1. 在&#x200B;**[!UICONTROL Cross-Device Profile Options]**&#x200B;清單中，選取您要執行區段的資料來源。 這些應是包含您現有[DPUUIDs](../../reference/ids-in-aam.md)的資料來源。

## 步驟4 —— 建立對象區段{#create-audience-segments}

若要建立新的觀眾區隔，請使用[區隔產生器](../segments/segment-builder.md)。 如果您有要傳送至[!DNL People-Based Destinations]的現有對象區段，請跳至[步驟5 —— 設定以人員為基礎的平台驗證](people-based-destinations-workflow-combined.md#configure-authentication)。

## 步驟5 —— 配置基於人的平台身份驗證{#configure-authentication}

1. 登入您的Audience Manager帳戶並前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您先前已設定與社交平台的整合，您應該會在此頁面中看到它。 否則，頁面為空。
   ![以人為本的整合](assets/pbd-config.png)
1. 按一下 **[!UICONTROL Add Account]**.
1. 使用&#x200B;**[!UICONTROL People-Based Platform]**下拉式功能表，選取您要設定整合的平台。
   ![以人為本的平台](assets/pbd-add.png)
1. 按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;以重新導向至所選平台的驗證頁面。
1. 一旦您已驗證您的社交平台帳戶，就會將您重新導向至Audience Manager，您應該會在其中看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!UICONTROL Confirm]**。
1. Audience Manager會在頁面頂端顯示通知，讓您知道帳戶是否已成功新增。 此通知也可讓您新增連絡人電子郵件地址，以在社交平台驗證即將到期時接收通知。

>[!IMPORTANT]
>
>觀眾管理員透過驗證Token處理與社交平台的整合，驗證Token會在特定時間後過期。 如需如何續約過期代號的詳細資訊，請參閱驗證代號續約。

## 步驟6 —— 建立基於人的目標{#create-destination}

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
1. 在&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;區段中，選取您要傳送至此目的地的區段。 這將是您在[步驟4 —— 建立對象區段](people-based-destinations-workflow-combined.md#create-audience-segments)中建立的區段。
1. 保存目標。
