---
description: '本頁包含如何結合離線CRM資料與即時行為資料的逐步指引，讓經過驗證的使用者建立受眾區段，然後將這些受眾區段傳送至以人員為基礎的目的地。 '
seo-description: '本頁包含如何結合離線CRM資料與即時行為資料的逐步指引，讓經過驗證的使用者建立受眾區段，然後將這些受眾區段傳送至以人員為基礎的目的地。  '
seo-title: 工作流 C - 以結合離線資料的驗證活動為基礎的個人化
solution: Audience Manager
title: 工作流 C - 以結合離線資料的驗證活動為基礎的個人化
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 5%

---

# 工作流 C - 以結合離線資料的驗證活動為基礎的個人化 {#workflow-c}

>[!IMPORTANT]
>本文包含旨在引導您完成此功能設定與使用的產品檔案。 本協定中沒有任何法律建議。 請洽詢您自己的法律顧問以取得法律指導。

本頁包含如何結合離線[!DNL CRM]資料與即時行為資料的逐步指引，讓已驗證的使用者建立受眾區段，然後將這些受眾區段傳送至[!DNL People-Based Destinations]。

## 步驟1 —— 配置資料源設定{#configure-data-source-settings}

視您的[DPUUIDs](../../reference/ids-in-aam.md)是否為小寫雜湊電子郵件地址而定，您可能需要設定將儲存雜湊電子郵件地址的資料來源。

 

**方案1:您的 [](../../reference/ids-in-aam.md) DPUUID已是小寫、雜湊的電子郵件地址。**

在本例中，請跳至[步驟5 —— 配置基於人員的平台驗證](#configure-authentication)。

 

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

## 步驟2 —— 使用宣告的ID，透過即時HTTP呼叫將DPUUID與雜湊的電子郵件地址比對{#match-email-addresses}

若要讓已驗證的使用者符合規則型特徵的資格，您必須透過[宣告的ID](../declared-ids.md)傳送特徵資格。

### 範例

假設您已建立下列兩個資料來源。

| 資料來源ID | 資料來源內容 |
| -------------- | -------------------------- |
| 郵編：999999 | 現有DPUUID(CRM ID) |
| 郵編：987654 | 雜湊的電子郵件地址 |

 

然後，您會想要將下方的CRM ID限定為表格中的特徵。

| DPUUID(CRM ID) | 電子郵件地址 | 雜湊電子郵件地址 | 特徵 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | 位置=美國 |

 

您宣告的ID應遵循下列語法：

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

在上述範例中，宣告的ID呼叫應如下所示：

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## 步驟3 —— 建立區段的描述檔合併規則{#create-profile-merge-rule-segmentation}

下一步是建立新的合併規則，協助您建立要傳送至[!DNL People-Based Destinations]的對象區段。

>[!IMPORTANT]
>
>如果您已使用&#x200B;**[!UICONTROL Current Authenticated Profiles]**&#x200B;或&#x200B;**[!UICONTROL Last Authenticated Profiles]**&#x200B;選項定義規則，則可跳至[步驟4 —— 建立對象區段](#create-audience-segments)。

1. 登入您的Audience Manager帳戶並前往&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**。
2. 按一下 **[!UICONTROL Add New Rule]**.
3. 輸入配置檔案合併規則&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
4. 在&#x200B;**[!UICONTROL Profile Merge Rule Setup]**&#x200B;部分，從&#x200B;**[!UICONTROL Cross-Device Options]**&#x200B;清單中選擇&#x200B;**[!UICONTROL Current Authenticated Profiles]**&#x200B;或&#x200B;**[!UICONTROL Last Authenticated Profiles]**&#x200B;規則。
5. 在&#x200B;**[!UICONTROL Cross-Device Profile Options]**清單中，選取您要執行區段的資料來源。 這些應是包含您現有DPUUID的資料來源。
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## 步驟4 —— 建立對象區段{#create-audience-segments}

若要建立新區段，請使用[區段產生器](../segments/segment-builder.md)。 如果您有要傳送至[!DNL People-Based Destinations]的現有對象區段，請跳至[步驟5 —— 設定以人員為基礎的平台驗證](#configure-authentication)。

## 步驟5 —— 配置基於人的平台身份驗證{#configure-authentication}

1. 登入您的Audience Manager帳戶，並前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您先前已設定與社交平台的整合，您應該會在此頁面中看到它。 否則，頁面為空。
   ![以人為本的整合](assets/pbd-config.png)
2. 按一下 **[!UICONTROL Add Account]**.
3. 使用&#x200B;**[!UICONTROL People-Based Platform]**下拉式功能表，選取您要設定整合的平台。
   ![以人為本的平台](assets/pbd-add.png)
4. 按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;以重新導向至所選平台的驗證頁面。
5. 一旦您已驗證您的社交平台帳戶，就會將您重新導向至Audience Manager，您應該在該處看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!UICONTROL Confirm]**。
6. Audience Manager會在頁面頂端顯示通知，讓您知道帳戶是否已成功新增。 此通知也可讓您新增連絡人電子郵件地址，以在社交平台驗證即將到期時接收通知。

>[!IMPORTANT]
>
>Audience Manager會透過驗證Token處理與社交平台的整合，這些Token會在特定時間後過期。 如需如何續約過期代號的詳細資訊，請參閱驗證代號續約。

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
1. 在&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;區段中，選取您要傳送至此目的地的區段。 這將是您在[步驟4 —— 建立對象區段](#create-audience-segments)中建立的區段。
1. 保存目標。
