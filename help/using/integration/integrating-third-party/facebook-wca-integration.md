---
description: 本頁說明建立Facebook網站自訂對象(WCA)像素的程式，其目的是將網路型Audience Manager對象區段傳送至Facebook，以利透明度提升的線上廣告定位。
seo-description: 本頁說明建立Facebook網站自訂對象(WCA)像素的程式，其目的是將網路型Audience Manager對象區段傳送至Facebook，以利透明度提升的線上廣告定位。
seo-title: Facebook WCA 整合
solution: Audience Manager
title: Facebook WCA 整合
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 6%

---


# [!DNL Facebook WCA] 整合 {#facebook-wca-integration}

本頁說明建立( [!DNL Facebook Website Custom Audiences] )像素的程式，以傳送網路讀者區段至[!DNL WCA]，以利透明度 [!DNL Audience Manager][!DNL Facebook]的線上廣告定位。

## 概述 {#overview}

[Facebook網站自訂對象(WCA)](https://www.facebook.com/business/help/449542958510885) (Facebook Website Custom Audiences,WCA)可讓您建立已瀏覽特定頁面或在您的網站上採取特定動作的訪客清單。 [!DNL Audience Manager] 啟用使用目 [!DNL WCA] 標的 [!DNL URL] 啟動功能，您可透過此功能設定自訂的像素整合，將網路受眾傳送至目標 [!DNL Facebook] 對象。

![Facebook WCA 整合](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 這項功能需要您在 [!UICONTROL Website] URL [目的地中選取社交平台](/help/using/features/destinations/create-url-destination.md)對象選項。 社交平台要求在傳送至其平台時，要揭露反向連結資訊。 請注意，這表示目標平台／合作夥伴將能夠在您的反向連結中看到資訊 [!DNL URL]。

## 必要條件 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] 區段，準備指派給新目 [!DNL Facebook] 標。 以下是 [如何在UI中建立區段](/help/using/features/segments/segment-builder.md)[!DNL Audience Manager] 的方法。
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID])4.1.0版或更新版本。 Download the latest version **[here](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL])9.0版或更新版本，可從這裡 **[下載](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。 或者，如果您使[用伺服器端轉送(SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)，將資料匯入[!DNL Audience Manager]，則必須使用AppMeasurement 2.12版或更新版本。 Download[!DNL AppMeasurement]using the[Analytics Code Manager](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/admin-tools/code-manager-admin.translate.html).

我們建議您使用 [Adobe Experience Platform Launch或](https://docs.adobelaunch.com/) Adobe Dynamic Tag Management [，在步驟3和4中安裝或升級程式庫](https://docs.adobe.com/content/help/zh-Hant/dtm/using/dtm-home.html)。

## 步驟1 —— 在中創 [!UICONTROL Facebook Destination] 建 [!DNL Audience Manager] {#step-1-create-facebook-destination}

在中創 [!UICONTROL URL Destination] 建 [!DNL Audience Manager] 新名稱 [!DNL Facebook Website Custom Audiences]。 建立目標時，請使用以下設定。 您也可以參閱「設 [定URL目標」頁面](/help/using/features/destinations/create-url-destination.md) 。

### 基本資訊

* **[!UICONTROL Category]**: 自訂
* **[!UICONTROL Type]**: [!DNL URL]
* 選中該 **[!UICONTROL Auto-fill Destination Mapping]** 複選框，然後選擇 **[!UICONTROL Segment ID]**。

### [!UICONTROL Data Export Labels]

選擇選項 **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**。

>[!NOTE]
>
> 此匯出標籤可防止從裝置圖形衍生的第三方資料和資料包含在區段中。

### 設定

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. 選取此選 [!UICONTROL URL Type] 項時， [!DNL Audience Manager] 不會在引發像素時遮 [!DNL URL] 蔽反向連結 [!DNL Facebook WCA] 資訊。
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* 在和字 **[!UICONTROL Base URL]** 段中 **[!UICONTROL Secure URL]** ，輸入像 [!DNL Facebook WCA] 素。
* **[!UICONTROL Delimiter]**: `,`

基本 [!DNL URL] 範例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

從頁面引發的像素範例。 此範例顯示符合三個區 [!DNL Audience Manager] 段資格的使用者，ID為3401321、2993399、3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 參數 | 說明 |
---------|----------|
| `id` | 您的 [!DNL Facebook] 像素ID，當您建立觀眾像素時，可 [!DNL Facebook Ad Manager] 在使用者介面中找到它。 |
| `ev` | Event.     這是任意值，當像素開始在網站上 [!DNL Facebook Ad Manager] 觸發時，就會出現在使用者介面中。 如需詳 [!UICONTROL Include] 細資訊， [請參閱](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)「步驟3」中的項目。 |
| `cd[segID]` | 另一個參數，當像素開始在網站上觸發 [!DNL Facebook Ad Manager] 時，就會開始填入使用者介面。 `segID` 也是武斷的。 |
| `%ALIAS%` | 巨 [!DNL Audience Manager] 集，將動態取代為網站訪客符合的 [!DNL Audience Manager][!UICONTROL segment] ID，以逗號分隔。 |

您的 [!UICONTROL URL destination] 設定應如下圖所示：

![目標配置](/help/using/integration/assets/facebook-wca.png)

儲存 [!UICONTROL destination]。 然後，您可以繼續「區段 **對應」步驟** 。

## 步驟2 —— 區段對應——將區段對應至目標 {#step-2-segment-mappings}

在「設 [定URL目標」工作流程中](/help/using/features/destinations/create-url-destination.md) ，將適用的區段對應至您新建立的區段 [!UICONTROL destination]。 請注意，對應值會自動填入 [!DNL Audience Manager][!UICONTROL segment ID]。

輸入結束日期（如果適用），否則留空不顯示結束日期。

## 步驟3 —— 在內 [!UICONTROL Audience] 部 [!DNL Facebook Ads Manager] {#step-3-create-audience}

請參 [閱說明檔案中的建立網站](https://www.facebook.com/business/help/666509013483225) 「自訂 [!DNL Facebook] 對象」。 選擇下 [!UICONTROL Create Audience] 表中的選項：

| 項目 | 說明 |
---------|----------|
| 網站流量 | 自訂組合 |
| 包含 | <ul><li>選擇 **[!UICONTROL Event]** >選擇 **[!UICONTROL Adobe-Audience-Manager-Segment]**。 這是步驟1中 `ev` 範例像素中的參數值。 請注意，如果像素尚未觸發，則 **[!UICONTROL Event]** 選項或 **[!UICONTROL Adobe-Audience-Manager-Segment]** 可能不會出現在使 [!DNL Facebook] 用者介面中。</li><li>新增參數： 選擇 `segID`。</li><li><p>選擇包 **含運算** 子。</p><p>這很重要，因為訪客可能符合多個區段的資格，所以像素參數中 [!UICONTROL segment IDs] 可能有多個。 使用等號(`=`)運算子可能無法讓訪客符合觀眾的資格，而且您會觀察到較低的量。</p></li><li>新增值： 輸入區 [!DNL Audience Manager] 段ID。</li></ul> |
| 新增條件 | 可選設定。 |
| 在最後一個 | 可選設定。 |
| 對象名稱 | 我們建議您使用相同的 [!DNL Audience Manager] 區段名稱來維持一致性，除非您要新增其他條件至此對象。 |

## 步驟4 —— 將 [!UICONTROL Audience] 指派給 [!UICONTROL Campaign] [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

建立後， [!DNL Custom Audience]將其指派至廣告促銷活動。 建立新的促銷活動或編輯現有的促銷活動，您會發現新建立的對象會列在使用者介 [!DNL Facebook] 面中。 您的廣告促銷活動將定位在瀏覽您的網站時，瀏覽器上曾看到像素觸發的使用者(如果將 [!DNL Audience Manager] 他們納入區段)。

## 摘要 {#summary}

現在您已將區段指 [!DNL Audience Manager] 派至目的地 [!DNL Facebook WCA] , [!DNL Audience Manager] 將會以像素中各自的區段ID，選擇性地 [!DNL Facebook WCA] 將像素觸發給指定區段的使用者以填入 [!DNL Facebook Audience]。 如此會逐漸增加標籤 [!DNL Facebook Audience] 對您網站上適用對象的引發量。

>[!NOTE]
>
> 如果使用者脫離區 [!DNL Audience Manager] 段，目前無法通知 [!DNL Audience Manager] 將 [!DNL Facebook] 使用者從中移除 [!DNL Custom Audience]。

