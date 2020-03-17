---
description: 本頁說明建立Facebook網站自訂對象(WCA)像素的程式，其目的是將網路型Audience Manager對象區段傳送至Facebook，以利透明度提升的線上廣告定位。
seo-description: 本頁說明建立Facebook網站自訂對象(WCA)像素的程式，其目的是將網路型Audience Manager對象區段傳送至Facebook，以利透明度提升的線上廣告定位。
seo-title: Facebook WCA整合
solution: Audience Manager
title: Facebook WCA整合
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Facebook WCA整合 {#facebook-wca-integration}

本頁說明建立Facebook網站自訂對象(WCA)像素的程式，其目的是將網路型Audience Manager對象區段傳送至Facebook，以利透明度提升的線上廣告定位。

## 概述 {#overview}

[Facebook網站自訂對象(WCA)](https://www.facebook.com/business/help/449542958510885) (Facebook Website Custom Audiences,WCA)可讓您建立已瀏覽特定頁面或在您的網站上採取特定動作的訪客清單。 Audience Manager可啟用WCA中的URL目標啟動，您可透過此目標設定自訂的像素整合，將線上受眾傳送至Facebook進行定位。

![Facebook WCA整合](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 這項功能需要您在 [URL目的地中選取「社交平台的網站對象」選項](/help/using/features/destinations/create-url-destination.md)。 社交平台要求在傳送至其平台時，要揭露反向連結資訊。 請注意，這表示目標平台／合作夥伴將能夠在您的反向連結URL中看到資訊。

## 必備條件 {#prerequisites}

1. Facebook廣告帳戶
2. Audience Manager區段，準備好指派給您的新Facebook目標。 以下是 [如何在Audience Manager](/help/using/features/segments/segment-builder.md) UI中建立區段。
3. Adobe Experience Platform Identity Service(ECID)4.1.0版或更新版本。 請在這裡下載最新 **[版本](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**。
4. Audience Manager資料整合庫(DIL)9.0版或更新版本，可從此處 **[下載](https://github.com/Adobe-Marketing-Cloud/dil/releases)**。 或者，如果您使[用伺服器端轉送(SSF)](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html)，將資料匯入Audience Manager，則必須使用AppMeasurement 2.12版或更新版本。 使用Analytics代碼管理[器下載AppMeasurement](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)。

我們建議您使用 [Adobe Experience Platform Launch或](https://docs.adobelaunch.com/) Adobe Dynamic Tag Management [，在步驟3和4中安裝或升級程式庫](https://marketing.adobe.com/resources/help/en_US/dtm/)。

## 步驟1 —— 在Audience Manager中建立Facebook目標 {#step-1-create-facebook-destination}

在Audience Manager中建立新的URL目標，並將其命名為Facebook網站自訂對象。 建立目標時，請使用以下設定。 您也可以參閱「設 [定URL目標」頁面](/help/using/features/destinations/create-url-destination.md) 。

**基本資訊**

* **類別**:自訂
* **類型**:URL
* 選取「自 **動填滿目標對應** 」核取方塊，然後選 **取區段ID**。

**資料匯出標籤**

選取「此目 **的地可能會啟用包含個人識別資訊(PII)的組合」選項**。

>[!NOTE]
>
> 此匯出標籤可防止從裝置圖形衍生的第三方資料和資料包含在區段中。

**設定**

* **URL類型**:選取 **社交平台的網站對象**。 透過選取此URL類型選項，Audience Manager在觸發Facebook WCA像素時不會遮住反向連結URL資訊。
* **序列化**:選擇 **啟用**。
* 在「基 **本URL** 」和「 **安全URL** 」欄位中，輸入Facebook WCA像素。
* **分隔字元**: ,

基本URL範例： `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

從頁面引發的像素範例。 此範例顯示符合三個Audience Manager區段（ID為3401321、2993399、3263410）的使用者：

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| 參數 | 說明 |
---------|----------|
| `id` | 您的Facebook像素ID，當您建立觀眾像素時，可在Facebook廣告管理員UI中找到。 |
| `ev` | 事件. 這是任意值，當像素開始在網站上觸發時，就會出現在Facebook廣告管理員UI中。 如需詳細資訊，請參 [閱步驟3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)中的包含項目。 |
| `cd[segID]` | 另一個參數，當像素開始在網站上觸發時，就會開始填入Facebook廣告管理員UI。 `segID` 也是武斷的。 |
| `%ALIAS%` | Audience Manager巨集，將動態取代為網站訪客符合的Audience Manager區段ID，以逗號分隔， |

您的URL目標設定應如下圖所示：

![目標配置](/help/using/integration/assets/facebook-wca.png)

保存目標。 然後，您可以繼續「區段 **對應」步驟** 。

## 步驟2 —— 區段對應——將區段對應至目標 {#step-2-segment-mappings}

在「設 [定URL目標」工作流程中](/help/using/features/destinations/create-url-destination.md) ，將適用的區段對應至您新建立的目標。 請注意，對應值會自動填入Audience Manager區段ID。

輸入結束日期（如果適用），否則留空不顯示結束日期。

## 步驟3 —— 在Facebook廣告管理員中建立觀眾 {#step-3-create-audience}

請參 [閱Facebook說明檔案中的](https://www.facebook.com/business/help/666509013483225) 「建立網站自訂對象」。 在下表中選取「建立對象」選項：


| 項目 | 說明 |
---------|----------|
| 網站流量 | 自訂組合 |
| 包含 | <ul><li>選 **擇事件** >選 **擇Adobe-Audience-Manager-Segment**。 這是步驟1中範例像素中ev參數的值。 請注意，如果像素尚未觸發， **Event****選項或** Adobe-Audience-Manager-Segment可能不會出現在Facebook UI中。</li><li>新增參數：選擇 `segID`。</li><li><p>選擇包 **含運算** 子。</p><p>這很重要，因為訪客可能符合多個區段的資格，所以像素參數中可能有多個區段ID。 使用等號(=)運算子可能無法讓訪客符合觀眾的資格，而且您會觀察到較低的量。</p></li><li>新增值：輸入Audience Manager區段ID。</li></ul> |
| 新增條件 | 可選設定。 |
| 在最後一個 | 可選設定。 |
| 對象名稱 | 我們建議您使用相同的Audience Manager區段名稱以維持一致性，除非您要新增其他條件至此Audience。 |

## 步驟4 —— 在Facebook廣告管理員中將對象指派至促銷活動 {#step-4-assign-audience-to-campaign}

建立「自訂對象」後，將其指派至廣告促銷活動。 建立新促銷活動或編輯現有促銷活動，您會發現新建立的「對象」會列在Facebook UI中。 如果Audience Manager將其納入區段，您的廣告促銷活動將會鎖定在瀏覽器上瀏覽過像素觸發的使用者。

## 摘要 {#summary}

現在您已將Audience Manager區段指派給Facebook WCA目標，Audience Manager會選擇性地將Facebook WCA像素觸發給指定區段的使用者，並在像素中各自的區段ID，以填入Facebook Audience。 這會導致「Facebook對象」逐漸增加，而標籤對您網站上的適用對象引發的次數越多。

>[!NOTE]
>
> 如果使用者脫離Audience Manager區段，Audience Manager目前無法通知Facebook將使用者從「自訂對象」中移除。

