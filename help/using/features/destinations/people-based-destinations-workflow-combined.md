---
description: '本頁面包含逐步指引，說明如何將離線CRM資料與您在Audience Manager中現有的行為資料結合，以建立新受眾區段，然後將這些受眾區段傳送至「基於人員的目標」。  '
seo-description: '本頁面包含逐步指引，說明如何將離線CRM資料與您在Audience Manager中現有的行為資料結合，以建立新受眾區段，然後將這些受眾區段傳送至「基於人員的目標」。   '
seo-title: 工作流程A-根據所有線上活動結合離線資料的個人化
solution: Audience Manager
title: 工作流程A-根據所有線上活動結合離線資料的個人化
translation-type: tm+mt
source-git-commit: f3f47db944d9f771cbd55058f6652188cda0e147

---


# 工作流程A-根據所有線上活動結合離線資料的個人化 {#workflow-a}

此頁面包含逐步指引，說明如何將離線 [!DNL CRM] 資料與您在Audience Manager中現有的行為資料結合 [!DNL People-Based Destinations]，以建立新受眾區段，然後傳送這些觀眾區段。

## 步驟-設定資料來源設定 {#configure-data-source-settings}

根據 [您的DPuUID](../../reference/ids-in-aam.md) 為小寫、雜湊電子郵件地址，您可能需要設定儲存雜湊電子郵件地址的資料來源。

**方案1：您[的dpuuid](../../reference/ids-in-aam.md)是小寫的電子郵件地址。**

在這種情況下，您需要為對應的資料來源加上標籤：

1. 前往 [!UICONTROL Audience Data] -&gt; [!UICONTROL Data Sources]。
1. 尋找包含您 [的DPUUID](../../reference/ids-in-aam.md)的資料來源，然後按一下它。
1. 請確定選項 [!UICONTROL Cannot be tied to personally identifiable information] 未勾選。
1. 儲存資料來源設定。

**方案2：您[的dpuUID](../../reference/ids-in-aam.md)不是小寫、雜湊電子郵件地址。**

在這種情況下，您需要建立新的跨裝置資料來源，以儲存雜湊電子郵件地址。以下是如何做到這一點：

1. 登入您的Audience Manager帳戶並前往 **[!UICONTROL Audience Data]** &gt;， **[!UICONTROL Data Sources]**&#x200B;然後按一下 **[!UICONTROL Add New]**。
1. 輸入您 [!UICONTROL Name][!UICONTROL Description] 的新資料來源。
1. 在 **[!UICONTROL ID Type]** 下拉式選單中，選取 **[!UICONTROL Cross Device]**。
1. **[!UICONTROL Data Source Settings]** 在區段中，選取和 **[!UICONTROL Inbound]****[!UICONTROL Outbound]** 選項，然後啓用 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 選項。
1. 使用下拉式選單選擇此資料來源的 **[!UICONTROL Emails(SHA256, lowercased)]** 標籤。
   >[!IMPORTANT]
   >
   >此選項只會將資料來源標示為包含特定演算法雜湊的資料。Audience Manager不會在此步驟雜湊資料。確定您打算儲存在此資料來源中的電子郵件地址已雜湊化 [!DNL SHA256] 。否則，您將無法使用 [!DNL People-Based Destinations]它。

   ![pdd-dataource-settings](assets/pbd-ds-config.png)

>[!NOTE]
>
> 如需有關如何將離線資料放入Audience Manager for People Manager的常見問題，請參閱 [「資料登錄](people-based-destinations-prerequisites.md#data-onboarding) 」。

## 步驟-透過檔案ID同步，將DpuUID比對至雜湊電子郵件地址 {#match-ids-emails}

>[!IMPORTANT]
>
> 此步驟僅適用於上述 [情況2](people-based-destinations-workflow-combined.md#configure-data-source-settings) 。如果您現有 [的DPuUID](../../reference/ids-in-aam.md) 是已雜湊的電子郵件地址，請略過至 [步驟-建立區段合併規則用於分段](people-based-destinations-workflow-combined.md#create-merge-rule)。

假設您要將現有 [的DPuUID](../../reference/ids-in-aam.md) 與下列表格的雜湊電子郵件地址配對(右欄)，並將雜湊電子郵件地址儲存在您在 [步驟建立的新資料來源中-設定資料來源設定](people-based-destinations-workflow-combined.md#configure-data-source-settings)。

| DPUUID(CRM ID) | 電子郵件地址 | 雜湊電子郵件地址 |
| --- | --- | --- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

您最多可以連結10個雜湊電子郵件地址至單一 [DPUUID](../../reference/ids-in-aam.md)。若要這麼做，請在同步檔案中將雜湊的電子郵件地址分隔為逗號。

在我們的範例中，您現在有兩個資料來源。

| 資料來源ID | 資料來源內容 |
| --- | --- |
| 999999 | 現有的DPuUID(CRM ID) |
| 987654 | 雜湊電子郵件地址 |

[您的ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 會有下列內容：

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

[ID同步檔案](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 必須遵循此命名結構：

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

在上述範例中，檔案名稱如下：`c2c_id_999999_987654_1560431657.sync`


[請在此處下載範例檔案](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)。

## 步驟-建立區段的描述檔合併規則 {#create-merge-rule}

下一個步驟是建立新的合併規則，幫助您建立對象區段，以傳送給您的人員目的地。

>[!IMPORTANT]
>
> 如果您已使用 [!UICONTROL Current Authenticated Profiles] 或 [!UICONTROL Last Authenticated Profiles] 選項定義規則，則可略過至 [步驟-建立對象區段](people-based-destinations-workflow-combined.md#create-audience-segments)。

1. 登入您的Audience Manager帳戶，然後前往 **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Profile Merge Rules]**。
1. Click **[!UICONTROL Add New Rule]**.
1. 輸入描述檔合併規則 **[!UICONTROL Name]** 。**[!UICONTROL Description]**
1. 在 **[!UICONTROL Profile Merge Rule Setup]** 區段中選取或 **[!UICONTROL Current Authenticated Profiles]****[!UICONTROL Last Authenticated Profiles]** 選項。
1. 在 **[!UICONTROL Cross-Device Profile Options]** 清單中，選取您要執行分段的資料來源。這些應是包含您現有 [的DPuUID](../../reference/ids-in-aam.md)的資料來源。

## 步驟-建立觀眾區段 {#create-audience-segments}

若要建立新的觀眾區段，請使用 [區段產生器](../segments/segment-builder.md)。如果您要傳送現有對象區段 [!DNL People-Based Destinations]，請略過至 [步驟-設定人員型平台驗證](people-based-destinations-workflow-combined.md#configure-authentication)。

## 步驟-設定人員架構的平台驗證 {#configure-authentication}

1. 登入您的Audience Manager帳戶，然後前往 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**。如果您先前已設定與社交平台的整合，則應在此頁面中查看它。否則，頁面是空的。
   ![人員型整合](assets/pbd-config.png)
1. Click **[!UICONTROL Add Account]**.
1. 使用 **[!UICONTROL People-Based Platform]** 下拉式選單選擇您要設定整合的平台。
   ![人員型平台](assets/pbd-add.png)
1. 按一下以 **[!UICONTROL Confirm]** 重新導向至所選平台的驗證頁面。
1. 在您驗證您的社交平台帳戶後，將會重新導向至Audience Manager，您應該會看到相關聯的廣告商帳戶。選取您要使用並按一下 **[!UICONTROL Confirm]**&#x200B;的廣告商帳戶。
1. Audience Manager會在頁面頂端顯示通知，讓您知道帳戶是否成功新增。此通知也可讓您新增連絡人電子郵件地址，以便在社交平台驗證即將過期時接收通知。

>[!IMPORTANT]
>
>使用者經理透過在特定時間長度後過期的驗證Token，處理與社交平台之間的整合。如需如何續約過期Token的詳細資訊，請參閱驗證Token續約。

## 步驟-建立以人員為基礎的目的地 {#create-destination}

1. 登入您的Audience Manager帳戶，前往 **[!UICONTROL Audience Data]** &gt;， **[!UICONTROL Destinations]**&#x200B;然後按一下 **[!UICONTROL Create Destination]**。
1. **[!UICONTROL Basic Information]** 在區段中，輸入新 **[!UICONTROL Name]** 資料來源並 **[!UICONTROL Description]** 使用下列設定：
   * **[!UICONTROL Category]**：整合平台；
   * **[!UICONTROL Type]**：以人為本；
   * **[!UICONTROL Platform]**：選取您要傳送對象區段的人員型平台；
   * **[!UICONTROL Account]**：選取所選平台相關聯的廣告商帳戶。
      ![建立目的地](assets/pbd-create-destination.png)
1. Click **[!UICONTROL Next]**.
1. 選擇您 **[!UICONTROL Data Export Labels]** 要為此目的地設定的項目。
1. 在 **[!UICONTROL Configuration]** 區段中，選取包含雜湊資料來源的資料來源。
1. 在 **[!UICONTROL Segment Mappings]** 區段中，選取要傳送至此目的地的區段。這將是您在 [步驟建立的區段-建立對象區段](people-based-destinations-workflow-combined.md#create-audience-segments)。
1. 儲存目的地。
