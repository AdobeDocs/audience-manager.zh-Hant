---
description: 本頁說明了建立Facebook網站自定義受眾(WCA)像素的過程，目的是向Facebook發送基於Web的Audience Manager受眾段，以提高透明度進行線上廣告定位。
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Facebook WCA 整合
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 8780083474d68717fe3bd4dc632d96da89929122
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Facebook WCA] 整合 {#facebook-wca-integration}

此頁說明了建立 [!DNL Facebook Website Custom Audiences] ([!DNL WCA])像素，用於發送基於Web的 [!DNL Audience Manager] 受眾段 [!DNL Facebook]以提高透明度，實現線上廣告定位。

## 概述 {#overview}

[Facebook網站自定義受眾(WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) 允許您建立訪問特定頁面或在您的網站上執行特定操作的人員清單。 [!DNL Audience Manager] 啟用激活 [!DNL WCA] 使用 [!DNL URL] 目標，您可以通過該目標配置基於像素的自定義整合，以將基於Web的受眾發送到 [!DNL Facebook] 目標。

![Facebook WCA 整合](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能要求您選擇 [!UICONTROL Website] 用戶在社交平台選項中 [URL目標](/help/using/features/destinations/create-url-destination.md)。 社交平台要求在將參考資訊發送到其平台時，必須對其進行解密。 請注意，這意味著目標平台/合作夥伴將能夠在您的引用者中查看資訊 [!DNL URL]。

## 必要條件 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] 段，準備分配給新 [!DNL Facebook] 目標。 這是 [如何建立段](/help/using/features/segments/segment-builder.md) 的 [!DNL Audience Manager] UI。
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID])4.1.0版或更高版本。 下載最新版本 **[這裡](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**。
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL])9.0版或更高版本，可從 **[這裡](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。 或者，如果您 [伺服器端轉發(SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) 將資料導入 [!DNL Audience Manager]，必須使用AppMeasurement 2.12或更高版本。 下載 [!DNL AppMeasurement] 使用 [分析代碼管理器](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html)。

我們建議您在步驟3和4中使用 [Adobe Experience Platform標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html)。

## 步驟1 — 建立 [!UICONTROL Facebook Destination] 在 [!DNL Audience Manager] {#step-1-create-facebook-destination}

新建 [!UICONTROL URL Destination] 在 [!DNL Audience Manager] 然後點名 [!DNL Facebook Website Custom Audiences]。 建立目標時，請使用下面的設定。 您還可以參考 [配置URL目標](/help/using/features/destinations/create-url-destination.md) 的子菜單。

### 基本資訊

* **[!UICONTROL Category]**: 自訂
* **[!UICONTROL Type]**: [!DNL URL]
* 選擇 **[!UICONTROL Auto-fill Destination Mapping]** 複選框，然後選擇 **[!UICONTROL Segment ID]**。

### [!UICONTROL Data Export Labels]

選擇選項 **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**。

>[!NOTE]
>
> 此導出標籤防止從設備圖形導出的第三方資料和資料包含在段中。

### 設定

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. 通過選擇此 [!UICONTROL URL Type] 選項， [!DNL Audience Manager] 不會模糊引用者 [!DNL URL] 觸發時的資訊 [!DNL Facebook WCA] 像素。
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* 在 **[!UICONTROL Base URL]** 和 **[!UICONTROL Secure URL]** ，輸入 [!DNL Facebook WCA] 像素。
* **[!UICONTROL Delimiter]**: `,`

基本 [!DNL URL] 示例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

從頁面觸發的示例像素。 此示例顯示符合三個條件的用戶 [!DNL Audience Manager] ID為3401321、2993399、3263410的資料段：

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 參數 | 說明 |
|---------|----------|
| `id` | 您 [!DNL Facebook] 像素ID，可在 [!DNL Facebook Ad Manager] 建立受眾像素時的用戶介面。 |
| `ev` | Event. 這是任意值，將出現在 [!DNL Facebook Ad Manager] 當像素開始在現場啟動時用戶介面。 查看 [!UICONTROL Include] 項目 [步驟3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)的子菜單。 |
| `cd[segID]` | 將開始在 [!DNL Facebook Ad Manager] 當像素開始在現場啟動時用戶介面。 `segID` 也是武斷的。 |
| `%ALIAS%` | 安 [!DNL Audience Manager] 宏，將動態替換為 [!DNL Audience Manager] [!UICONTROL segment] 站點訪問者符合的ID，以逗號分隔， |

您 [!UICONTROL URL destination] 配置應如下所示：

![目標配置](/help/using/integration/assets/facebook-wca.png)

保存 [!UICONTROL destination]。 然後，您可以 **段映射** 的子菜單。

## 步驟2 — 段映射 — 將段映射到目標 {#step-2-segment-mappings}

在 [配置URL目標](/help/using/features/destinations/create-url-destination.md) 工作流，將適用段映射到新建立的 [!UICONTROL destination]。 注意，映射值將自動填充 [!DNL Audience Manager] [!UICONTROL segment ID]。

輸入結束日期（如果適用），否則留空，無結束日期。

## 步驟3 — 建立 [!UICONTROL Audience] 內 [!DNL Facebook Ads Manager] {#step-3-create-audience}

請參閱 [建立網站自定義受眾](https://www.facebook.com/business/help/666509013483225) 的 [!DNL Facebook] 幫助文檔。 選擇 [!UICONTROL Create Audience] 選項：

| 項目 | 說明 |
|---------|----------|
| 網站流量 | 自定義組合 |
| 包含 | <ul><li>選擇 **[!UICONTROL Event]** >選擇 **[!UICONTROL Adobe-Audience-Manager-Segment]**。 這是 `ev` 示例像素中的參數。 請注意，如果像素尚未激發， **[!UICONTROL Event]** 選項 **[!UICONTROL Adobe-Audience-Manager-Segment]** 可能未出現在 [!DNL Facebook] 用戶介面。</li><li>添加參數：選擇 `segID`。</li><li><p>選擇 **包含** 運算子。</p><p>這一點很重要，因為訪問者可能有資格訪問多個網段，因此可能有多個 [!UICONTROL segment IDs] 的子菜單。 使用等號(`=`)操作員可能不會為觀眾提供訪問者資格，而您將觀看較少的內容。</p></li><li>添加值：輸入 [!DNL Audience Manager] 段ID。</li></ul> |
| 添加新條件 | 可選設定。 |
| 《在最後 | 可選設定。 |
| 受眾名稱 | 我們建議您使用 [!DNL Audience Manager] 段名稱以保證一致性，除非您向此訪問群體添加附加條件。 |

## 步驟4 — 分配 [!UICONTROL Audience] 到 [!UICONTROL Campaign] 在 [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

建立 [!DNL Custom Audience]，將其分配給廣告市場活動。 建立新市場活動或編輯現有市場活動，您會發現新建立的受眾列在 [!DNL Facebook] 用戶介面。 您的廣告活動將針對在訪問您的站點時看到其瀏覽器上像素著火的用戶(如果 [!DNL Audience Manager] 包括於分部內。

## 摘要 {#summary}

既然你已經 [!DNL Audience Manager] 分部至 [!DNL Facebook WCA] 目標， [!DNL Audience Manager] 會有選擇地發射 [!DNL Facebook WCA] 像素到給定段的用戶的像素，其中像素中各段ID填充 [!DNL Facebook Audience]。 這導致在GM的 [!DNL Facebook Audience] 標籤被激發到您站點上適用的受眾的次數越多。

>[!NOTE]
>
> 如果用戶從 [!DNL Audience Manager] 段，目前無法 [!DNL Audience Manager] 通知 [!DNL Facebook] 從 [!DNL Custom Audience]。
