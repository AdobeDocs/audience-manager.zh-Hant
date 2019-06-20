---
description: 本頁說明建立Facebook網站自訂觀眾(WCA)像素的程序，目的是為了將線上Audience Manager觀眾區段傳送至Facebook，以便透過改進的透明度進行線上廣告鎖定。
seo-description: 本頁說明建立Facebook網站自訂觀眾(WCA)像素的程序，目的是為了將線上Audience Manager觀眾區段傳送至Facebook，以便透過改進的透明度進行線上廣告鎖定。
seo-title: Facebook WCA整合
solution: Audience Manager
title: Facebook WCA整合
translation-type: tm+mt
source-git-commit: 56999c1968a486bed0e2e672a4de1774d049e09d

---


# Facebook WCA Integration {#facebook-wca-integration}

本頁說明建立Facebook網站自訂觀眾(WCA)像素的程序，目的是為了將線上Audience Manager觀眾區段傳送至Facebook，以便透過改進的透明度進行線上廣告鎖定。

## 概述 {#overview}

[Facebook網站自訂觀眾(WCA)](https://www.facebook.com/business/help/449542958510885) 可讓您建立已瀏覽特定頁面或在網站上執行特定動作的人員清單。Audience Manager可使用URL目的地啓用WCA中的啓動功能，您可使用此功能設定自訂像素整合，以便將網頁對象傳送至Facebook以進行定位。

![Facebook WCA整合](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> This capability requires that you select the Website audience for social platforms option in [URL destinations](/help/using/features/destinations/manage-destinations.md#configure-url-destination). Social平台要求反向連結資訊在傳送至其平台時會被遮色片。請注意，這表示目的地平台/合作夥伴將能夠在反向連結URL中看到資訊。

## 必備條件 {#prerequisites}

1. Facebook廣告帳戶
2. Audience Manager區段，準備要指派至您的新Facebook目的地。Here is [how to create a segment](/help/using/features/segments/segment-builder.md) in the Audience Manager UI.
3. Adobe Experience Cloud ID Service(ECID)4.1.0版或更新版本。Download the latest version **[here](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternatively, if you use [Server-Side Forwarding (SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to import data into Audience Manager, you must use AppMeasurement version 2.12 or newer. Download AppMeasurement using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

We recommend that you install or upgrade the libraries in steps 3 and 4 using [Adobe Launch](https://docs.adobelaunch.com/) or [Adobe Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

## Step 1 - Create a Facebook Destination in Audience Manager {#step-1-create-facebook-destination}

在Audience Manager中建立新的URL目標，並將其命名為Facebook網站自訂觀眾。請在建立目的地時使用下列設定。You can also refer to the [Configure a URL Destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) page.

**基本資訊**

* **類別**：自訂
* **類型**：URL
* Select the **Auto-fill Destination Mapping** check box, then select **Segment ID**.

**資料匯出標籤**

Select the option **This destination may enable a combination with personally identifiable information (PII)**.

>[!NOTE]
>
> 此匯出標籤可防止協力廠商資料和從裝置圖表衍生的資料納入區段中。

**設定**

* **URL類型**：選取 **社交平台的網站對象**。選取此URL類型選項後，Audience Manager不會在引發Facebook WCA像素時遮蔽反向連結URL資訊。
* **序列化**：選取 **「啓用**」。
* In the **Base URL** and **Secure URL** field, enter the Facebook WCA pixel.
* **分隔字元**: ,

Base URL example: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

頁面引發的像素範例。此範例顯示三個Audience Manager區段符合資格的使用者，其中ID3401321、2993399、3263410：

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| 參數 | 說明 |
---------|----------|
| `id` | 您的Facebook像素ID，您可以在建立觀眾像素時在Facebook廣告管理員UI中找到此ID。 |
| `ev` | 事件. 這是任意值，當像素在網站上開始引發時，會出現在Facebook廣告管理員UI中。See the Include item in [Step 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), for more information. |
| `cd[segID]` | 另一個參數，當像素在網站上開始引發時，此參數會開始在Facebook廣告管理員UI中填入。`segID` 也是任意的。 |
| `%ALIAS%` | Audience Manager巨集，此巨集會動態替換為網站訪客符合逗號分隔、以逗號分隔的Audience Manager區段ID； |

您的URL目的地組態應該類似於下列影像：

![目的地組態](/help/using/integration/assets/facebook-wca.png)

儲存目的地。Then, you can proceed to the **Segment Mappings** step.

## Step 2 - Segment Mappings - Map Segment to Destination {#step-2-segment-mappings}

In the [Configure URL destination](/help/using/features/destinations/manage-destinations.md#configure-url-destination) workflow, map the applicable segment to your newly created destination. 請注意，對應值會自動填入Audience Manager區段ID。

請輸入結束日期(如果適用)，否則不會結束日期的空白。

## Step 3 - Create an Audience within Facebook Ads Manager {#step-3-create-audience}

See [Create a Website Custom Audience](https://www.facebook.com/business/help/666509013483225) in the Facebook help documentation. 選取下表中的「建立對象」選項：


| 項目 | 說明 |
---------|----------|
| 網站流量 | 自訂組合 |
| 包含 | <ul><li>Select **Event** &gt; Select **Adobe-Audience-Manager-Segment**. 這是步驟中範例像素中ev參數的值。Note that if the pixel is yet to fire, the **Event** option or **Adobe-Audience-Manager-Segment** may not appear in the Facebook UI.</li><li>Add a parameter: Select `segID`.</li><li><p>Select the **contains** operator.</p><p>很重要的是，考慮到訪客可能符合多個區段，像素參數中可能會有多個區段ID。使用等於(=)運算子可能不會使訪客符合您的訪客資格，而您會看到較低的數量。</p></li><li>新增值：輸入Audience Manager區段ID。</li></ul> |
| 新增條件 | 可選設定。 |
| 在最後一個 | 可選設定。 |
| 對象名稱 | 建議您使用相同的Audience Manager區段名稱作為一致性，除非您要新增其他條件給此對象。 |

## Step 4 - Assign the Audience to a Campaign in Facebook Ads Manager {#step-4-assign-audience-to-campaign}

建立自訂對象後，將其指派給廣告促銷活動。建立新促銷活動或編輯現有的促銷活動，然後您會發現新建立的對象已列在Facebook UI中。如果Audience Manager包含區段，則您的廣告促銷活動會定位在瀏覽器上瀏覽像素引發像素引發的使用者。

## 摘要 {#summary}

現在您已將Audience Manager區段指派至Facebook WCA目的地，Audience Manager會選擇性地將Facebook WCA像素觸發給指定區段的使用者，並使用像素中的個別區段ID填入Facebook對象。這會導致Facebook對象逐漸增加，標籤會引發給您網站上適用的對象。

>[!NOTE]
>
> 如果使用者不是Audience Manager區段，Audience Manager目前不會通知Facebook將使用者從「自訂對象」移除。

