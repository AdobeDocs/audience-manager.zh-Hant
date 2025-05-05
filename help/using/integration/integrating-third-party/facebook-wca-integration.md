---
description: 本頁說明建立Facebook網站自訂對象(WCA)畫素的程式，其目的是將網頁型Audience Manager對象區段傳送至Facebook，以提升透明度的線上廣告目標定位。
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: facebook WCA整合
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 6dc931b88666515cf51ab89ce1a54bbcf9995679
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 1%

---

# [!DNL Facebook WCA]整合 {#facebook-wca-integration}

此頁面說明建立[!DNL Facebook Website Custom Audiences] ([!DNL WCA])畫素的程式，目的是將Web型[!DNL Audience Manager]對象區段傳送至[!DNL Facebook]，以用於線上廣告目標定位，並改善透明度。

>[!IMPORTANT]
>
>這不是Audience Manager與Facebook之間的產品化整合。

## 概述 {#overview}

[Facebook網站自訂對象(WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494)可讓您建立曾經造訪過特定頁面或在您的網站上採取特定動作的人清單。 [!DNL Audience Manager]可使用[!DNL URL]目的地在[!DNL WCA]中啟用啟用，您可以設定自訂畫素式整合，將網頁式對象傳送至[!DNL Facebook]以進行目標定位。

![Facebook WCA 整合](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能需要您在[URL目的地](/help/using/features/destinations/create-url-destination.md)中選取適用於社交平台的[!UICONTROL Website]對象選項。 社交平台要求反向連結資訊在傳送至其平台時須取消遮罩。 請注意，這表示目的地平台/合作夥伴將能夠在您的反向連結[!DNL URL]中檢視資訊。

## 必備條件 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager]個區段，已準備好指派給您的新[!DNL Facebook]目的地。 以下是[如何在[!DNL Audience Manager] UI中建立區段](/help/using/features/segments/segment-builder.md)。
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) 4.1.0或更新版本。 在此下載最新版本&#x200B;**[&#128279;](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**。
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) 9.0或更新版本，可從&#x200B;**[這裡](https://github.com/Adobe-Marketing-Cloud/dil/releases)**&#x200B;下載。 或者，如果您使用[伺服器端轉送(SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=zh-Hant)將資料匯入[!DNL Audience Manager]，則必須使用AppMeasurement版本2.12或更新版本。 使用[Analytics代碼管理員](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=zh-Hant)下載[!DNL AppMeasurement]。

建議您使用[Adobe Experience Platform標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hant)來安裝或升級步驟3與步驟4中的程式庫。

## 步驟1 — 在[!DNL Audience Manager]中建立[!UICONTROL Facebook Destination] {#step-1-create-facebook-destination}

在[!DNL Audience Manager]中建立新的[!UICONTROL URL Destination]並將其命名為[!DNL Facebook Website Custom Audiences]。 建立目的地時，請使用下列設定。 您也可以參閱[設定URL目的地](/help/using/features/destinations/create-url-destination.md)頁面。

### 基本資訊

* **[!UICONTROL Category]**：自訂
* **[!UICONTROL Type]**： [!DNL URL]
* 選取&#x200B;**[!UICONTROL Auto-fill Destination Mapping]**&#x200B;核取方塊，然後選取&#x200B;**[!UICONTROL Segment ID]**。

### [!UICONTROL Data Export Labels]

選取選項&#x200B;**[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**。

>[!NOTE]
>
> 此匯出標籤可防止區段中包含從裝置圖表衍生的第三方資料和資料。

### 設定

* **[!UICONTROL URL type]**：選取&#x200B;**[!UICONTROL Website audience for social platforms]**。 選取此[!UICONTROL URL Type]選項後，[!DNL Audience Manager]在引發[!DNL Facebook WCA]畫素時不會遮蔽反向連結[!DNL URL]資訊。
* **[!UICONTROL Serialize]**：選取&#x200B;**[!UICONTROL Enable]**。
* 在&#x200B;**[!UICONTROL Base URL]**&#x200B;和&#x200B;**[!UICONTROL Secure URL]**&#x200B;欄位中，輸入[!DNL Facebook WCA]畫素。
* **[!UICONTROL Delimiter]**： `,`

基底[!DNL URL]範例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

從頁面引發的畫素範例。 此範例顯示符合三個[!DNL Audience Manager]區段資格的使用者，其ID為3401321、2993399、3263410：

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 參數 | 說明 |
|---------|----------|
| `id` | 建立對象畫素時，您可以在[!DNL Facebook Ad Manager]使用者介面中找到您的[!DNL Facebook]畫素ID。 |
| `ev` | 事件。 這是任意值，一旦畫素開始在網站上引發，就會顯示在[!DNL Facebook Ad Manager]使用者介面中。 如需詳細資訊，請參閱[步驟3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)中的[!UICONTROL Include]專案。 |
| `cd[segID]` | 另一個引數，當畫素開始在網站上引發時，就會開始填入[!DNL Facebook Ad Manager]使用者介面中。 `segID`也是任意的。 |
| `%ALIAS%` | [!DNL Audience Manager]巨集，將會以網站訪客合格的[!DNL Audience Manager] [!UICONTROL segment] ID動態取代，並以逗號分隔， |

您的[!UICONTROL URL destination]設定應該如下圖所示：

![目的地組態](/help/using/integration/assets/facebook-wca.png)

儲存[!UICONTROL destination]。 接著，您可以繼續進行&#x200B;**區段對應**&#x200B;步驟。

## 步驟2 — 區段對應 — 將區段對應至目的地 {#step-2-segment-mappings}

在[設定URL目的地](/help/using/features/destinations/create-url-destination.md)工作流程中，將適用的區段對應至您新建立的[!UICONTROL destination]。 請注意，對應值已使用[!DNL Audience Manager] [!UICONTROL segment ID]自動填入。

輸入結束日期（若適用），否則將留空表示無結束日期。

## 步驟3 — 在[!DNL Facebook Ads Manager]中建立[!UICONTROL Audience] {#step-3-create-audience}

請參閱[!DNL Facebook]說明檔案中的建立網站自訂對象[&#128279;](https://www.facebook.com/business/help/666509013483225)。 選取下表中的[!UICONTROL Create Audience]選項：

| 項目 | 說明 |
|---------|----------|
| 網站流量 | 自訂組合 |
| 包含 | <ul><li>選取&#x200B;**[!UICONTROL Event]** >選取&#x200B;**[!UICONTROL Adobe-Audience-Manager-Segment]**。 這是步驟1中範例畫素中`ev`引數的值。 請注意，如果畫素尚未引發，**[!UICONTROL Event]**&#x200B;選項或&#x200B;**[!UICONTROL Adobe-Audience-Manager-Segment]**&#x200B;可能不會顯示在[!DNL Facebook]使用者介面中。</li><li>新增引數：選取`segID`。</li><li><p>選取&#x200B;**包含**&#x200B;運運算元。</p><p>這點很重要，因為訪客可能有資格使用多個區段，畫素引數中可能會有多個[!UICONTROL segment IDs]。 使用等於(`=`)運運算元可能無法讓您的訪客符合受眾資格，而且您會看到較小的數量。</p></li><li>新增值：輸入[!DNL Audience Manager]區段識別碼。</li></ul> |
| 新增條件 | 選擇性設定。 |
| 過去 | 選擇性設定。 |
| 對象名稱 | 除非您新增其他條件至此對象，否則建議您使用相同的[!DNL Audience Manager]區段名稱來維持一致性。 |

## 步驟4 — 將[!UICONTROL Audience]指派給[!DNL Facebook Ads Manager]中的[!UICONTROL Campaign] {#step-4-assign-audience-to-campaign}

建立[!DNL Custom Audience]後，將其指派至廣告行銷活動。 建立新的行銷活動或編輯現有的行銷活動，您會發現新建立的對象列在[!DNL Facebook]使用者介面中。 如果[!DNL Audience Manager]將使用者納入區段中，您的廣告行銷活動會鎖定在造訪您的網站時瀏覽器上看見畫素觸發的使用者。

## 摘要 {#summary}

現在您已將[!DNL Audience Manager]區段指派至[!DNL Facebook WCA]目的地，[!DNL Audience Manager]會選擇性地將[!DNL Facebook WCA]畫素引發給在畫素中具有個別區段ID的指定區段使用者，以填入[!DNL Facebook Audience]。 這會導致[!DNL Facebook Audience]逐漸增加，您網站上對適用對象引發的標籤就會越多。

>[!NOTE]
>
> 如果使用者退出[!DNL Audience Manager]區段，目前沒有方法可讓[!DNL Audience Manager]通知[!DNL Facebook]從[!DNL Custom Audience]移除使用者。
>
