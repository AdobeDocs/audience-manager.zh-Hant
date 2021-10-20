---
description: 本頁說明建立Facebook網站自訂對象(WCA)像素的程式，以將網頁型Audience Manager對象區段傳送至Facebook，以提高透明度進行線上廣告鎖定目標。
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Facebook WCA 整合
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 3%

---

# [!DNL Facebook WCA] 整合 {#facebook-wca-integration}

此頁面說明建立 [!DNL Facebook Website Custom Audiences] ([!DNL WCA])像素，以傳送以Web為基礎 [!DNL Audience Manager] 對象區段 [!DNL Facebook]，改善透明度的線上廣告鎖定目標。

## 概述 {#overview}

[Facebook網站自訂對象(WCA)](https://www.facebook.com/business/help/449542958510885) 可讓您建立瀏覽過特定頁面或在網站上採取特定動作的人員清單。 [!DNL Audience Manager] 啟用 [!DNL WCA] 使用 [!DNL URL] 目的地，您可以透過此目的地設定自訂像素式整合，以傳送網頁受眾至 [!DNL Facebook] 進行定位。

![Facebook WCA 整合](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能需要您選取 [!UICONTROL Website] 社交平台對象選項，位於 [URL目的地](/help/using/features/destinations/create-url-destination.md). 社交平台要求在傳送至其平台時，要揭露反向連結資訊。 請注意，這表示目的地平台/合作夥伴將能夠在您的反向連結中看到資訊 [!DNL URL].

## 必要條件 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] 區段，已準備好指派給新 [!DNL Facebook] 目的地。 這裡 [如何建立區段](/help/using/features/segments/segment-builder.md) 在 [!DNL Audience Manager] UI。
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID])4.1.0版或更新版本。 下載最新版本 **[此處](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL])9.0版或更新版本，可從下列網址下載： **[此處](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. 或者，如果您使用 [伺服器端轉送(SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) 若要將資料匯入 [!DNL Audience Manager]，您必須使用AppMeasurement 2.12版或更新版本。 下載 [!DNL AppMeasurement] 使用 [Analytics代碼管理器](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

建議您使用安裝程式庫，或升級步驟3和步驟4中的程式庫 [Adobe Experience Platform標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## 步驟1 — 建立 [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

建立新 [!UICONTROL URL Destination] in [!DNL Audience Manager] 然後給它命名 [!DNL Facebook Website Custom Audiences]. 建立目的地時，請使用下方的設定。 您也可以參閱 [設定URL目的地](/help/using/features/destinations/create-url-destination.md) 頁面。

### 基本資訊

* **[!UICONTROL Category]**: 自訂
* **[!UICONTROL Type]**: [!DNL URL]
* 選取 **[!UICONTROL Auto-fill Destination Mapping]** 核取方塊，然後選取 **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

選取選項 **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> 此匯出標籤可防止從裝置圖表衍生的第三方資料和資料納入區段中。

### 設定

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. 選擇此 [!UICONTROL URL Type] 選項， [!DNL Audience Manager] 不會遮蔽反向連結 [!DNL URL] 觸發時的資訊 [!DNL Facebook WCA] 像素。
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* 在 **[!UICONTROL Base URL]** 和 **[!UICONTROL Secure URL]** 欄位，輸入 [!DNL Facebook WCA] 像素。
* **[!UICONTROL Delimiter]**: `,`

基 [!DNL URL] 範例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

從頁面引發的範例像素。 此範例顯示符合三個使用者的資格 [!DNL Audience Manager] 區段，使用ID3401321、2993399、3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 參數 | 說明 |
|---------|----------|
| `id` | 您的 [!DNL Facebook] 像素ID，您可在 [!DNL Facebook Ad Manager] 使用者介面。 |
| `ev` | Event.     這是任意值，會顯示在 [!DNL Facebook Ad Manager] 像素開始在網站上引發時的使用者介面。 請參閱 [!UICONTROL Include] 項目 [步驟3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)，以了解詳細資訊。 |
| `cd[segID]` | 其他參數將開始在 [!DNL Facebook Ad Manager] 像素開始在網站上引發時的使用者介面。 `segID` 也是武斷的。 |
| `%ALIAS%` | 安 [!DNL Audience Manager] 宏，將動態替換為 [!DNL Audience Manager] [!UICONTROL segment] 網站訪客符合的ID，以逗號分隔， |

您的 [!UICONTROL URL destination] 設定應如下圖所示：

![目標配置](/help/using/integration/assets/facebook-wca.png)

儲存 [!UICONTROL destination]. 接著，您可以繼續 **區段對應** 步驟。

## 步驟2 — 區段對應 — 將區段對應至目的地 {#step-2-segment-mappings}

在 [設定URL目的地](/help/using/features/destinations/create-url-destination.md) 工作流程，將適用的區段對應至您新建立的 [!UICONTROL destination]. 請注意，對應值會自動填入 [!DNL Audience Manager] [!UICONTROL segment ID].

輸入終止日期（如果適用），否則留空不輸入終止日期。

## 步驟3 — 建立 [!UICONTROL Audience] with [!DNL Facebook Ads Manager] {#step-3-create-audience}

請參閱 [建立網站自訂對象](https://www.facebook.com/business/help/666509013483225) 在 [!DNL Facebook] 說明檔案。 選取 [!UICONTROL Create Audience] 下表中的選項：

| 項目 | 說明 |
|---------|----------|
| 網站流量 | 自訂組合 |
| 包含 | <ul><li>選擇 **[!UICONTROL Event]** >選取 **[!UICONTROL Adobe-Audience-Manager-Segment]**. 這是 `ev` 參數。 請注意，如果像素尚未引發，則 **[!UICONTROL Event]** 選項或 **[!UICONTROL Adobe-Audience-Manager-Segment]** 不會顯示在 [!DNL Facebook] 使用者介面。</li><li>新增參數：選擇 `segID`.</li><li><p>選取 **包含** 運算元。</p><p>考慮到訪客可能符合多個區段的資格，這很重要 [!UICONTROL segment IDs] 在像素參數中。 使用等於(`=`)運算子可能不符合訪客對象的資格，而您會看到較低的量。</p></li><li>新增值：輸入 [!DNL Audience Manager] 區段ID。</li></ul> |
| 新增條件 | 可選設定。 |
| 最後 | 可選設定。 |
| 對象名稱 | 建議您使用相同 [!DNL Audience Manager] 一致性的區段名稱，除非您要新增其他條件至此對象。 |

## 步驟4 — 指派 [!UICONTROL Audience] 到 [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

建立 [!DNL Custom Audience]，將其指派至廣告促銷活動。 建立新促銷活動或編輯現有的促銷活動，您會發現新建立的對象列在 [!DNL Facebook] 使用者介面。 您的廣告促銷活動將目標定位在瀏覽您的網站時，已在瀏覽器上看到像素引發的使用者(如果 [!DNL Audience Manager] 在區段中納入。

## 摘要 {#summary}

既然您已將 [!DNL Audience Manager] 區段至 [!DNL Facebook WCA] 目的地， [!DNL Audience Manager] 會有選擇地發射 [!DNL Facebook WCA] 像素中填入像素中各自的區段ID給指定區段的使用者 [!DNL Facebook Audience]. 這會導致 [!DNL Facebook Audience] 對您網站上的適用對象觸發標籤的次數越多。

>[!NOTE]
>
> 如果使用者從 [!DNL Audience Manager] 區段，目前無法 [!DNL Audience Manager] 通知 [!DNL Facebook] 從 [!DNL Custom Audience].
