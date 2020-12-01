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

本頁說明建立[!DNL Facebook Website Custom Audiences]([!DNL WCA])像素的程式，以傳送網路型[!DNL Audience Manager]觀眾區段至[!DNL Facebook]，以利透明度的線上廣告定位。

## 概述 {#overview}

[Facebook網站自訂對象(WCA)](https://www.facebook.com/business/help/449542958510885) 可讓您建立已瀏覽特定頁面或在您的網站上採取特定動作的訪客清單。[!DNL Audience Manager] 啟用使用 [!DNL WCA] 目標 [!DNL URL] 的啟動，您可透過此目標來設定自訂的像素整合，以傳送網路受眾以 [!DNL Facebook] 進行定位。

![Facebook WCA 整合](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能要求您在[URL目標](/help/using/features/destinations/create-url-destination.md)中選取[!UICONTROL Website]社交平台對象選項。 社交平台要求在傳送至其平台時，要揭露反向連結資訊。 請注意，這表示目標平台／合作夥伴將能夠在您的反向連結[!DNL URL]中看到資訊。

## 必要條件 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] 區段，準備指派給新目 [!DNL Facebook] 標。以下是如何在](/help/using/features/segments/segment-builder.md) UI中建立區段[的方法。[!DNL Audience Manager]
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID])4.1.0版或更新版本。下載最新版&#x200B;**[此處](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**。
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL])9.0版或更新版本，可從這裡 **[下載](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。或者，如果您使用[伺服器端轉送(SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)將資料匯入[!DNL Audience Manager]，則必須使用AppMeasurement 2.12版或更新版本。 使用[Analytics代碼管理器](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)下載[!DNL AppMeasurement]。

我們建議您使用[Adobe Experience Platform Launch](https://docs.adobelaunch.com/)或[Adobe動態標籤管理](https://docs.adobe.com/content/help/zh-Hant/dtm/using/dtm-home.html)，在步驟3和4中安裝或升級程式庫。

## 步驟1 —— 在[!DNL Audience Manager] {#step-1-create-facebook-destination}中建立[!UICONTROL Facebook Destination]

在[!DNL Audience Manager]中建立新的[!UICONTROL URL Destination]，並將它命名為[!DNL Facebook Website Custom Audiences]。 建立目標時，請使用以下設定。 您也可以參閱[設定URL目標](/help/using/features/destinations/create-url-destination.md)頁面。

### 基本資訊

* **[!UICONTROL Category]**: 自訂
* **[!UICONTROL Type]**: [!DNL URL]
* 選擇&#x200B;**[!UICONTROL Auto-fill Destination Mapping]**&#x200B;複選框，然後選擇&#x200B;**[!UICONTROL Segment ID]**。

### [!UICONTROL Data Export Labels]

選擇&#x200B;**[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**&#x200B;選項。

>[!NOTE]
>
> 此匯出標籤可防止從裝置圖形衍生的第三方資料和資料包含在區段中。

### 設定

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. 選取此[!UICONTROL URL Type]選項後，當觸發[!DNL Facebook WCA]像素時，[!DNL Audience Manager]不會遮蔽反向連結[!DNL URL]資訊。
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* 在&#x200B;**[!UICONTROL Base URL]**&#x200B;和&#x200B;**[!UICONTROL Secure URL]**&#x200B;欄位中，輸入[!DNL Facebook WCA]像素。
* **[!UICONTROL Delimiter]**:  `,`

基本[!DNL URL]示例：`https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

從頁面引發的像素範例。 此範例顯示符合三個[!DNL Audience Manager]區段資格的使用者，其ID為3401321、2993399、3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 參數 | 說明 |
---------|----------|
| `id` | 您的[!DNL Facebook]像素ID，當您建立觀眾像素時，可在[!DNL Facebook Ad Manager]使用者介面中找到。 |
| `ev` | Event.     這是任意值，當像素開始在網站上觸發時，該值會出現在[!DNL Facebook Ad Manager]使用者介面中。 如需詳細資訊，請參閱[步驟3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)中的[!UICONTROL Include]項目。 |
| `cd[segID]` | 另一個參數，當像素開始在網站上觸發時，會開始填入[!DNL Facebook Ad Manager]使用者介面中。 `segID` 也是武斷的。 |
| `%ALIAS%` | [!DNL Audience Manager]巨集，將動態取代為[!DNL Audience Manager] [!UICONTROL segment] ID，此ID是網站訪客適用的，以逗號分隔， |

您的[!UICONTROL URL destination]組態應如下圖所示：

![目標配置](/help/using/integration/assets/facebook-wca.png)

保存[!UICONTROL destination]。 然後，您可以繼續&#x200B;**區段映射**&#x200B;步驟。

## 步驟2 —— 段映射——將段映射到目標{#step-2-segment-mappings}

在[設定URL目標](/help/using/features/destinations/create-url-destination.md)工作流程中，將適用的區段對應至您新建立的[!UICONTROL destination]。 請注意，映射值會自動填入[!DNL Audience Manager] [!UICONTROL segment ID]。

輸入結束日期（如果適用），否則留空不顯示結束日期。

## 步驟3 —— 在[!DNL Facebook Ads Manager] {#step-3-create-audience}中建立[!UICONTROL Audience]

請參閱[!DNL Facebook]說明檔案中的[建立網站自訂對象](https://www.facebook.com/business/help/666509013483225)。 選擇下表中的[!UICONTROL Create Audience]選項：

| 項目 | 說明 |
---------|----------|
| 網站流量 | 自訂組合 |
| 包含 | <ul><li>選擇&#x200B;**[!UICONTROL Event]** >選擇&#x200B;**[!UICONTROL Adobe-Audience-Manager-Segment]**。 這是步驟1中範例像素中`ev`參數的值。 請注意，如果像素尚未觸發，**[!UICONTROL Event]**&#x200B;選項或&#x200B;**[!UICONTROL Adobe-Audience-Manager-Segment]**&#x200B;可能不會出現在[!DNL Facebook]使用者介面中。</li><li>新增參數：選擇`segID`。</li><li><p>選擇&#x200B;**contains**&#x200B;運算子。</p><p>這很重要，因為訪客可能符合多個區段的資格，所以像素參數中可能有多個[!UICONTROL segment IDs]。 使用等於(`=`)運算子可能無法讓訪客符合觀眾的資格，因此您會發現音量較低。</p></li><li>新增值：輸入[!DNL Audience Manager]區段ID。</li></ul> |
| 新增條件 | 可選設定。 |
| 在最後一個 | 可選設定。 |
| 對象名稱 | 我們建議您使用相同的[!DNL Audience Manager]區段名稱來維持一致性，除非您要新增其他條件至此對象。 |

## 步驟4 —— 將[!UICONTROL Audience]指派給[!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}中的[!UICONTROL Campaign]

建立[!DNL Custom Audience]後，將它指派給廣告促銷活動。 建立新的促銷活動或編輯現有的促銷活動，您會發現新建立的對象會列在[!DNL Facebook]使用者介面中。 如果[!DNL Audience Manager]將像素點數納入區段，您的廣告促銷活動將會定位在瀏覽器上瀏覽您的網站時，曾看到像素點數的使用者。

## 摘要 {#summary}

現在您已將[!DNL Audience Manager]區段指派給[!DNL Facebook WCA]目標，[!DNL Audience Manager]會選擇性地將[!DNL Facebook WCA]像素觸發給指定區段的使用者，並在像素中使用相應的區段ID來填入[!DNL Facebook Audience]。 這會使[!DNL Facebook Audience]的值逐漸增加，標籤對您網站上的適用對象引發的次數越多。

>[!NOTE]
>
> 如果使用者從[!DNL Audience Manager]區段中掉下來，目前沒有辦法讓[!DNL Audience Manager]通知[!DNL Facebook]將使用者從[!DNL Custom Audience]移除。

