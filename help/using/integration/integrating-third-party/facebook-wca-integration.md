---
description: 本頁說明建立Facebook網站自訂對象(WCA)像素的程式，以將網頁型Audience Manager對象區段傳送至Facebook，以提高透明度進行線上廣告鎖定目標。
seo-description: 本頁說明建立Facebook網站自訂對象(WCA)像素的程式，以將網頁型Audience Manager對象區段傳送至Facebook，以提高透明度進行線上廣告鎖定目標。
seo-title: Facebook WCA 整合
solution: Audience Manager
title: Facebook WCA 整合
feature: 協力廠商整合
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 5%

---

# [!DNL Facebook WCA] 整合 {#facebook-wca-integration}

本頁說明建立[!DNL Facebook Website Custom Audiences]([!DNL WCA])像素的程式，目的是傳送以網頁為基礎的[!DNL Audience Manager]對象區段至[!DNL Facebook]，以利透明度改善的線上廣告鎖定目標。

## 概述 {#overview}

[Facebook網站自訂對象(WCA)](https://www.facebook.com/business/help/449542958510885) 可讓您建立已造訪特定頁面或在您的網站上採取特定動作的人員清單。[!DNL Audience Manager] 可讓您使 [!DNL WCA] 用目 [!DNL URL] 的地來啟動，透過目的地，您可以設定自訂像素式整合，將網頁型受眾傳送至以 [!DNL Facebook] 進行鎖定。

![Facebook WCA 整合](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能需要您在[URL目的地](/help/using/features/destinations/create-url-destination.md)中選取社交平台的[!UICONTROL Website]對象選項。 社交平台要求在傳送至其平台時，要揭露反向連結資訊。 請注意，這表示目的地平台/合作夥伴將能在您的反向連結[!DNL URL]中看到資訊。

## 必要條件 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] 區段，已準備好指派至新目 [!DNL Facebook] 的地。以下是如何在[!DNL Audience Manager] UI中建立區段](/help/using/features/segments/segment-builder.md)的方法。[
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID])4.1.0版或更新版本。請在這裡](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**下載最新版本**[。
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL])9.0版或更新版本，可從這裡 **[下載](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。或者，如果您使用[伺服器端轉送(SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)將資料匯入[!DNL Audience Manager]，則必須使用AppMeasurement 2.12版或更新版本。 使用[Analytics代碼管理器](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)下載[!DNL AppMeasurement]。

建議您使用[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html)安裝或升級步驟3和4中的程式庫。

## 步驟1 — 在[!DNL Audience Manager] {#step-1-create-facebook-destination}中建立[!UICONTROL Facebook Destination]

在[!DNL Audience Manager]中建立新的[!UICONTROL URL Destination]，並將其命名為[!DNL Facebook Website Custom Audiences]。 建立目的地時，請使用下方的設定。 您也可以參閱[設定URL目的地](/help/using/features/destinations/create-url-destination.md)頁面。

### 基本資訊

* **[!UICONTROL Category]**: 自訂
* **[!UICONTROL Type]**: [!DNL URL]
* 選中&#x200B;**[!UICONTROL Auto-fill Destination Mapping]**&#x200B;複選框，然後選擇&#x200B;**[!UICONTROL Segment ID]**。

### [!UICONTROL Data Export Labels]

選擇選項&#x200B;**[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**。

>[!NOTE]
>
> 此匯出標籤可防止從裝置圖表衍生的第三方資料和資料納入區段中。

### 設定

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. 選取此[!UICONTROL URL Type]選項後，當觸發[!DNL Facebook WCA]像素時，[!DNL Audience Manager]不會遮蔽反向連結[!DNL URL]資訊。
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* 在&#x200B;**[!UICONTROL Base URL]**&#x200B;和&#x200B;**[!UICONTROL Secure URL]**&#x200B;欄位中，輸入[!DNL Facebook WCA]像素。
* **[!UICONTROL Delimiter]**:  `,`

基[!DNL URL]示例：`https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

從頁面引發的範例像素。 此範例顯示符合三個[!DNL Audience Manager]區段(ID為3401321、2993399、3263410)的使用者：

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 參數 | 說明 |
|---------|----------|
| `id` | 您的[!DNL Facebook]像素ID，在建立對象像素時，您可在[!DNL Facebook Ad Manager]使用者介面中找到。 |
| `ev` | Event.     這是任意值，一旦像素開始在網站上引發，就會顯示在[!DNL Facebook Ad Manager]使用者介面中。 如需詳細資訊，請參閱[步驟3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)中的[!UICONTROL Include]項目。 |
| `cd[segID]` | 一個額外參數，像素開始在網站上引發後，就會開始填入[!DNL Facebook Ad Manager]使用者介面中。 `segID` 也是武斷的。 |
| `%ALIAS%` | [!DNL Audience Manager]巨集，會以網站訪客符合資格的[!DNL Audience Manager] [!UICONTROL segment] ID動態取代，並以逗號分隔。 |

您的[!UICONTROL URL destination]設定應如下圖所示：

![目標配置](/help/using/integration/assets/facebook-wca.png)

保存[!UICONTROL destination]。 接著，您可以繼續進行&#x200B;**區段對應**&#x200B;步驟。

## 步驟2 — 區段對應 — 將區段對應至目的地{#step-2-segment-mappings}

在[設定URL目標](/help/using/features/destinations/create-url-destination.md)工作流程中，將適用的區段對應至您新建立的[!UICONTROL destination]。 請注意，對應值會自動填入[!DNL Audience Manager] [!UICONTROL segment ID]。

輸入終止日期（如果適用），否則留空不輸入終止日期。

## 步驟3 — 在[!DNL Facebook Ads Manager] {#step-3-create-audience}內建立[!UICONTROL Audience]

請參閱[!DNL Facebook]說明檔案中的[建立網站自訂對象](https://www.facebook.com/business/help/666509013483225) 。 選取下表中的[!UICONTROL Create Audience]選項：

| 項目 | 說明 |
|---------|----------|
| 網站流量 | 自訂組合 |
| 包含 | <ul><li>選擇&#x200B;**[!UICONTROL Event]** >選擇&#x200B;**[!UICONTROL Adobe-Audience-Manager-Segment]**。 這是步驟1範例像素中`ev`參數的值。 請注意，如果像素尚未引發，**[!UICONTROL Event]**&#x200B;選項或&#x200B;**[!UICONTROL Adobe-Audience-Manager-Segment]**&#x200B;可能不會出現在[!DNL Facebook]使用者介面中。</li><li>新增參數：選擇`segID`。</li><li><p>選擇&#x200B;**contains**&#x200B;運算子。</p><p>考慮到訪客可能符合多個區段的資格，像素參數中可能有多個[!UICONTROL segment IDs]，這點很重要。 使用等於(`=`)運算子可能無法讓訪客符合對象的資格，而您將會看到較低的量。</p></li><li>新增值：輸入[!DNL Audience Manager]區段ID。</li></ul> |
| 新增條件 | 可選設定。 |
| 最後 | 可選設定。 |
| 對象名稱 | 建議您使用相同的[!DNL Audience Manager]區段名稱來維持一致，除非您要新增其他條件至此對象。 |

## 步驟4 — 將[!UICONTROL Audience]指派給[!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}中的[!UICONTROL Campaign]

建立[!DNL Custom Audience]後，將其指派至廣告促銷活動。 建立新促銷活動或編輯現有促銷活動，您會發現新建立的對象列在[!DNL Facebook]使用者介面中。 如果[!DNL Audience Manager]將像素納入區段中，您的廣告促銷活動將鎖定在瀏覽器上看見像素觸發的使用者。

## 摘要 {#summary}

現在您已將[!DNL Audience Manager]區段指派給[!DNL Facebook WCA]目的地，[!DNL Audience Manager]會選擇性地將[!DNL Facebook WCA]像素觸發給指定區段的使用者，並在像素中使用各自的區段ID填入[!DNL Facebook Audience]。 這會導致[!DNL Facebook Audience]逐漸增加，導致對您網站上適用的對象觸發的標籤越多。

>[!NOTE]
>
> 如果使用者掉出[!DNL Audience Manager]區段，目前沒有辦法讓[!DNL Audience Manager]通知[!DNL Facebook]將使用者從[!DNL Custom Audience]中移除。

