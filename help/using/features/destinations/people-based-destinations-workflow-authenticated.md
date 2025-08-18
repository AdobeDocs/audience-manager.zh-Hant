---
description: 此頁面包含分步指南，說明如何將離線CRM資料與已驗證身分使用者的即時行為資料結合，以建立對象區段，然後將這些對象區段傳送至「以人物為基礎的目的地」。
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with real-time behavioral data for authenticated users to create audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow C - Personalization Based on Authenticated Activity Combined with Offline Data
solution: Audience Manager
title: 工作流程C — 以結合離線資料的驗證活動為基礎的Personalization
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 1%

---

# 工作流程C — 以結合離線資料的驗證活動為基礎的Personalization {#workflow-c}

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 此處未包含任何法律建議。 請諮詢您自己的法律顧問，以取得法律指引。

此頁面包含如何結合離線[!DNL CRM]資料與已驗證使用者的即時行為資料，以建立對象區段，然後將這些對象區段傳送至[!DNL People-Based Destinations]的逐步指引。

## 步驟1 — 設定資料Source設定 {#configure-data-source-settings}

視您的[DPUUID](../../reference/ids-in-aam.md)是否為小寫、雜湊電子郵件地址而定，您可能需要設定將儲存雜湊電子郵件地址的資料來源。

 

**案例1：您的[DPUUID](../../reference/ids-in-aam.md)已經是小寫、雜湊電子郵件地址。**

在此情況下，請跳至[步驟5 — 設定以人物為基礎的平台驗證](#configure-authentication)。

 

**案例2：您的[DPUUID](../../reference/ids-in-aam.md)不是小寫、雜湊電子郵件地址。**

在這種情況下，您需要建立新的跨裝置資料來源，以儲存雜湊電子郵件地址。 以下是其操作方式：

1. 登入您的Audience Manager帳戶並移至&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**，然後按一下&#x200B;**[!UICONTROL Add New]**。
1. 輸入您新資料來源的&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
1. 在&#x200B;**[!UICONTROL ID Type]**&#x200B;下拉式功能表中，選取&#x200B;**[!UICONTROL Cross Device]**。
1. 在&#x200B;**[!UICONTROL Data Source Settings]**&#x200B;區段中，同時選取&#x200B;**[!UICONTROL Inbound]**&#x200B;和&#x200B;**[!UICONTROL Outbound]**&#x200B;選項，並啟用&#x200B;**[!UICONTROL Share associated cross-device IDs in people-based destinations]**&#x200B;選項。
1. 使用下拉式功能表為此資料來源選取&#x200B;**[!UICONTROL Emails(SHA256, lowercased)]**&#x200B;標籤。
   >[!IMPORTANT]
   >
   >此選項僅會將資料來源標示為包含使用該特定演演算法雜湊的資料。 Audience Manager不會在此步驟將資料雜湊。 確定您計畫儲存在此資料來源中的電子郵件地址已使用[!DNL SHA256]演演算法雜湊。 否則，您將無法將其用於[!DNL People-Based Destinations]。

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 請參閱[資料上線](people-based-destinations-prerequisites.md#data-onboarding)，以取得有關如何將離線資料帶入Audience Manager以人物為基礎的目的地的常見問題。

觀看以下影片以瞭解如何為[!UICONTROL People-Based Destinations]建立資料來源的影片教學課程。

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## 步驟2 — 透過即時HTTP呼叫，使用宣告ID來比對DPUUID與雜湊電子郵件地址 {#match-email-addresses}

若要讓已驗證的使用者符合規則型特徵的資格，您必須透過[宣告的ID](../declared-ids.md)傳送特徵資格。

### 範例

假設您已建立下列兩個資料來源。

| 資料來源ID | 資料來源內容 |
| -------------- | -------------------------- |
| 999999 | 現有DPUUID (CRM ID) |
| 987654 | 雜湊電子郵件地址 |

 

然後，您想要限定下列CRM ID符合表格中的特徵。

| DPUUID (CRM ID) | 電子郵件地址 | 雜湊電子郵件地址 | 特性 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | 位置=美國 |

 

您宣告的ID應遵循下列語法：

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

在上述範例中，宣告ID呼叫看起來應該像這樣：

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## 步驟3 — 建立區段的設定檔合併規則 {#create-profile-merge-rule-segmentation}

下一個步驟是建立新的合併規則，協助您建立要傳送至[!DNL People-Based Destinations]的對象區段。

>[!IMPORTANT]
>
>如果您已有使用&#x200B;**[!UICONTROL Current Authenticated Profiles]**&#x200B;或&#x200B;**[!UICONTROL Last Authenticated Profiles]**&#x200B;選項定義的規則，您可以跳至[步驟4 — 建立對象區段](#create-audience-segments)。

1. 登入您的Audience Manager帳戶並移至&#x200B;**[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**。
2. 按一下 **[!UICONTROL Add New Rule]**。
3. 輸入設定檔合併規則&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**。
4. 在&#x200B;**[!UICONTROL Profile Merge Rule Setup]**&#x200B;區段中，從&#x200B;**[!UICONTROL Current Authenticated Profiles]**&#x200B;清單中選取&#x200B;**[!UICONTROL Last Authenticated Profiles]**&#x200B;或&#x200B;**[!UICONTROL Cross-Device Options]**&#x200B;規則。
5. 在&#x200B;**[!UICONTROL Cross-Device Profile Options]**清單中，選取您要執行分段的資料來源。 這些應該是包含現有DPUUID的資料來源。
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## 步驟4 — 建立對象區段 {#create-audience-segments}

若要建立新區段，請使用[區段產生器](../segments/segment-builder.md)。 如果您有想要傳送至[!DNL People-Based Destinations]的現有對象區段，請跳至[步驟5 — 設定以人物為基礎的平台驗證](#configure-authentication)。

## 步驟5 — 設定以人物為基礎的平台驗證 {#configure-authentication}

1. 登入您的Audience Manager帳戶並移至&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**。 如果您先前設定好與社交平台的整合，您應會看到此頁面所列的專案。 否則，頁面會是空的。
   ![以人物為基礎的整合](assets/pbd-config.png)
2. 按一下 **[!UICONTROL Add Account]**。
3. 使用&#x200B;**[!UICONTROL People-Based Platform]**下拉式功能表選取您要設定整合的平台。
   ![以人員為基礎的平台](assets/pbd-add.png)
4. 按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;以重新導向至所選平台的驗證頁面。
5. 在驗證您的Social Platform帳戶後，您會重新導向至Audience Manager，在那裡您應該會看到相關的廣告商帳戶。 選取您要使用的廣告商帳戶，然後按一下&#x200B;**[!UICONTROL Confirm]**。
6. Audience Manager會在頁面頂端顯示通知，讓您知道帳戶是否已成功新增。 通知也可讓您新增連絡人電子郵件地址，以在社交平台驗證即將到期時接收通知。

>[!IMPORTANT]
>
>Audience Manager會透過驗證權杖（將於特定時間後過期）來處理與社交平台的整合。 如需如何更新過期權杖的詳細資訊，請參閱驗證權杖續約。

## 步驟6 — 建立以人物為基礎的目的地 {#create-destination}

1. 登入您的Audience Manager帳戶，前往&#x200B;**[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**，然後按一下&#x200B;**[!UICONTROL Create Destination]**。
1. 在&#x200B;**[!UICONTROL Basic Information]**&#x200B;區段中，輸入新資料來源的&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**，並使用下列設定：
   * **[!UICONTROL Category]**：整合平台；
   * **[!UICONTROL Type]**：以人物為基礎；
   * **[!UICONTROL Platform]**：選取您要傳送受眾區段的目標以人物為基礎的平台；
   * **[!UICONTROL Account]**：選取與所選平台相關聯的所需廣告商帳戶。
     ![create-destination](assets/pbd-create-destination.png)
1. 按一下 **[!UICONTROL Next]**。
1. 選擇要為此目的地設定的&#x200B;**[!UICONTROL Data Export Labels]**。
1. 在&#x200B;**[!UICONTROL Configuration]**&#x200B;區段中，選取包含雜湊資料來源的資料來源。
1. 在&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;區段中，選取您要傳送至此目的地的區段。 這是您在[步驟4 — 建立對象區段](#create-audience-segments)所建立的區段。
1. 儲存目的地。
