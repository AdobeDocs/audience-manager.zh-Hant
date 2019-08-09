---
description: 本頁說明建立Facebook網站自訂觀眾(WCA)像素的程序，目的是為了將線上Audience Manager觀眾區段傳送至Facebook，以便透過改進的透明度進行線上廣告鎖定。
seo-description: 本頁說明建立Facebook網站自訂觀眾(WCA)像素的程序，目的是為了將線上Audience Manager觀眾區段傳送至Facebook，以便透過改進的透明度進行線上廣告鎖定。
seo-title: Facebook WCA整合
solution: Audience Manager
title: Facebook WCA整合
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Facebook WCA整合 {#facebook-wca-integration}

本頁說明建立Facebook網站自訂觀眾(WCA)像素的程序，目的是為了將線上Audience Manager觀眾區段傳送至Facebook，以便透過改進的透明度進行線上廣告鎖定。

## 概述 {#overview}

[Facebook網站自訂觀眾(WCA)](https://www.facebook.com/business/help/449542958510885) 可讓您建立已瀏覽特定頁面或在網站上執行特定動作的人員清單。Audience Manager可使用URL目的地啓用WCA中的啓動功能，您可使用此功能設定自訂像素整合，以便將網頁對象傳送至Facebook以進行定位。

![Facebook WCA整合](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 此功能需要您在 [URL目的地中選取社交平台選項的網站對象](/help/using/features/destinations/create-url-destination.md)。Social平台要求反向連結資訊在傳送至其平台時會被遮色片。請注意，這表示目的地平台/合作夥伴將能夠在反向連結URL中看到資訊。

## 必備條件 {#prerequisites}

1. Facebook廣告帳戶
2. Audience Manager區段，準備要指派至您的新Facebook目的地。以下是如何在Audience [Manager UI中建立區段](/help/using/features/segments/segment-builder.md) 的方法。
3. Adobe Experience Cloud ID Service(ECID)4.1.0版或更新版本。請在這裡下載最新版本 **[](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**。
4. Audience Manager Data Integration Library(DIL)9.0版或更新版本，可從 **[此處下載](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。或者，如果您使用 [伺服器端轉送(SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) 將資料匯入Audience Manager，則必須使用AppMeasurement2.12版或更新版本。使用 [Analytics代碼管理器下載AppMeasurement](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)。

建議您使用 [Adobe Launch](https://docs.adobelaunch.com/) 或 [Adobe動態標籤管理，在步驟和4中安裝或升級程式庫](https://marketing.adobe.com/resources/help/en_US/dtm/)。

## 步驟-在Audience Manager中建立Facebook目的地 {#step-1-create-facebook-destination}

在Audience Manager中建立新的URL目標，並將其命名為Facebook網站自訂觀眾。請在建立目的地時使用下列設定。您也可以參閱 [設定URL目的地](/help/using/features/destinations/create-url-destination.md) 頁面。

**基本資訊**

* **類別**：自訂
* **類型**：URL
* 選取 **「自動填寫目標對應」** 核取方塊，然後選取 **「區段ID**」。

**資料匯出標籤**

選取此 **選項可讓此目的地啓用個人識別資訊(PII)**。

>[!NOTE]
>
> 此匯出標籤可防止協力廠商資料和從裝置圖表衍生的資料納入區段中。

**設定**

* **URL類型**：選取 **社交平台的網站對象**。選取此URL類型選項後，Audience Manager不會在引發Facebook WCA像素時遮蔽反向連結URL資訊。
* **序列化**：選取 **「啓用**」。
* 在 **「基本URL** 」和 **「保全URL** 」欄位中，輸入Facebook WCA像素。
* **分隔字元**: ,

基本URL範例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

頁面引發的像素範例。此範例顯示三個Audience Manager區段符合資格的使用者，其中ID3401321、2993399、3263410：

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| 參數 | 說明 |
---------|----------|
| `id` | 您的Facebook像素ID，您可以在建立觀眾像素時在Facebook廣告管理員UI中找到此ID。 |
| `ev` | 事件. 這是任意值，當像素在網站上開始引發時，會出現在Facebook廣告管理員UI中。如需詳細資訊，請參閱 [步驟中](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)的包含項目。 |
| `cd[segID]` | 另一個參數，當像素在網站上開始引發時，此參數會開始在Facebook廣告管理員UI中填入。`segID` 也是任意的。 |
| `%ALIAS%` | Audience Manager巨集，此巨集會動態替換為網站訪客符合逗號分隔、以逗號分隔的Audience Manager區段ID； |

您的URL目的地組態應該類似於下列影像：

![目的地組態](/help/using/integration/assets/facebook-wca.png)

儲存目的地。然後，您可以繼續進行 **「區段對應」** 步驟。

## 步驟-區段對應-將區段對應至目的地 {#step-2-segment-mappings}

在 [設定URL目的地](/help/using/features/destinations/create-url-destination.md#) 工作流程中，將適用區段對應至您新建的目的地。請注意，對應值會自動填入Audience Manager區段ID。

請輸入結束日期(如果適用)，否則不會結束日期的空白。

## 步驟-在Facebook廣告管理員中建立觀眾 {#step-3-create-audience}

請參閱 [Facebook說明文件中的建立網站自訂對象](https://www.facebook.com/business/help/666509013483225) 。選取下表中的「建立對象」選項：


| 項目 | 說明 |
---------|----------|
| 網站流量 | 自訂組合 |
| 包含 | <ul><li>選取 **「事件** &gt;選擇 **Adobe-Audience-Manager-Segment**」。這是步驟中範例像素中ev參數的值。請注意，如果像素尚未引發， **「事件** 」選項或 **「Adobe-Audience-Manager-Segment-Segment」** 可能不會出現在Facebook UI中。</li><li>新增參數：選取 `segID`。</li><li><p>選取 **包含** 運算子。</p><p>很重要的是，考慮到訪客可能符合多個區段，像素參數中可能會有多個區段ID。使用等於(=)運算子可能不會使訪客符合您的訪客資格，而您會看到較低的數量。</p></li><li>新增值：輸入Audience Manager區段ID。</li></ul> |
| 新增條件 | 可選設定。 |
| 在最後一個 | 可選設定。 |
| 對象名稱 | 建議您使用相同的Audience Manager區段名稱作為一致性，除非您要新增其他條件給此對象。 |

## 步驟-在Facebook廣告管理器中指派觀眾至促銷活動 {#step-4-assign-audience-to-campaign}

建立自訂對象後，將其指派給廣告促銷活動。建立新促銷活動或編輯現有的促銷活動，然後您會發現新建立的對象已列在Facebook UI中。如果Audience Manager包含區段，則您的廣告促銷活動會定位在瀏覽器上瀏覽像素引發像素引發的使用者。

## 摘要 {#summary}

現在您已將Audience Manager區段指派至Facebook WCA目的地，Audience Manager會選擇性地將Facebook WCA像素觸發給指定區段的使用者，並使用像素中的個別區段ID填入Facebook對象。這會導致Facebook對象逐漸增加，標籤會引發給您網站上適用的對象。

>[!NOTE]
>
> 如果使用者不是Audience Manager區段，Audience Manager目前不會通知Facebook將使用者從「自訂對象」移除。

