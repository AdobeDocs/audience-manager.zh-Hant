---
description: '回答人們目標的常見問題。  '
seo-description: '回答人們目標的常見問題。  '
seo-title: 以人員為基礎的目標常見問答集
solution: Audience Manager
title: 以人員為基礎的目標常見問答集
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# 以人員為基礎的目標常見問答集 {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**我無法在[!DNL People-Based Destinations]Audience Manager帳戶中看到。我需要瞭解哪些可用性？**

[!DNL People-Based Destinations] is premium Audience Manager features that is available on purchase.如需定價和可用性的詳細資訊，請聯絡您的Adobe銷售代表。

## 資料倉庫 {#data-onboarding}

**我要如何將客戶電子郵件地址放在Audience Manager中，以便將它們用於[!DNL People-Based Destinations]？**

有兩種方式可讓您將離線資料帶入Audience Manager [!DNL People-Based Destinations]。

* **使用檔案ID同步**。如需ID同步檔案的詳細資訊，請參閱 [ID同步檔案](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 的名稱和內容需求。使用此方法時，您可以從 [!DNL CRM] 資料庫鎖定所有雜湊的電子郵件地址。
* **在通過驗證的客戶ID時，使用「宣告的ID** 」宣告雜湊電子郵件地址。使用此方法時，Audience Manager只會啓動已進行線上驗證的使用者的雜湊電子郵件地址。透過Facebook啓動的電子郵件地址僅為宣告ID事件呼叫中的一個。與客戶ID相關聯的其他電子郵件地址不會即時啓用。

**我可以透過Web表格或行動應用程式收集雜湊電子郵件地址嗎？還是必須透過批次檔案進行？**

您可以透過使用宣告ID的 [!DNL ECID] 網路驗證，收集雜湊電子郵件 [地址](../features/declared-ids.md)。批次檔案可讓您收集雜湊電子郵件地址，這些電子郵件地址無法透過驗證傳送([!DNL CRM])，並在以人員為基礎的目的地中啓用它們。

**如何透過Web表格吸收雜湊電子郵件地址，而不是透過批次檔案上傳雜湊電子郵件地址？**

離線資料擷取的設計是為了支援不需要驗證的使用案例，而在所有離線[!UICONTROL All Cross-Device Profiles][!DNL CRM] 設定檔上執行的新描述檔合併規則()可做為一部分來執行 [!DNL People-Based Destinations]。此方法旨在補充從線上來源擷取已驗證對象的功能。

**我可以傳送/更新雜湊電子郵件地址的最大頻率？**

* 使用「宣告ID」時，Audience Manager會即時將雜湊電子郵件地址傳送至目的地。
* 透過ID同步檔案吸收資料時，Audience Manager會每日進行處理。

**如何知道電子郵件地址雜湊是否正確執行？**

Audience Manager無法吸收原始電子郵件地址，而且無法驗證雜湊是否正確執行。如需如何雜湊已登錄資料的詳細資訊，請參閱 [「先決條件和考量事項](../features/destinations/people-based-destinations-prerequisites.md) 」。

## 描述檔合併規則 {#profile-merge-rules}

**是否有新的設定檔合併規則可用於[!DNL People-Based Destinations]？**

是。購買的 [!DNL People-Based Destinations] 客戶也可以存取新的描述檔合併規則，以便離線分段。系統會呼叫 [!DNL All Cross-Device Profiles] 規則，並用於僅離線區段。當您註冊時 [!DNL People-Based Destinations]，這是您可以建立的第四個描述檔合併規則，除了三個現有驗證型規則之外。

**我必須複製現有的對象區段，才能將它們啓動[!DNL People-Based Destinations]嗎？**

視您的使用案例而定。如果您打算在以人員為基礎的管道中啓用現有的第一方區段，則不需要建立新區段。您只能將區段對應至以人員為基礎的目的地。

如果您打算在以人員為基礎的管道中啓用新離線受眾，則需要使用 [!DNL All Cross-Device Profiles] 合併規則建立新的第一方區段。
>[!NOTE]
>
> 您只能將具有第一方資料的區段對應 [!DNL People-Based Destinations]至。我們的目的地平台不接受第二方和第三方資料的區段。

## 匹配比率 {#match-rates}

**是否[!DNL People-Based Destinations]可見率或可定址受眾？**

不會。傳送觀眾區段時 [!DNL People-Based Destinations]，合作夥伴端會發生觀眾配對。Adobe無法存取這些度量。Audience Manager會顯示每個目的地的最高可分享對象，以及屬於區段之人員的即時計數。此資訊可協助您進行促銷活動規劃和預測。

**理論比較如何與[!DNL People-Based Destinations]其他將觀眾傳送至目的地平台的方式相比，使用理論比較？**

只要電子郵件地址被雜湊和吸收，與其他方法之間的匹配率就不會 [!DNL People-Based Destinations] 有任何差別。匹配率低於100%的唯一原因是，如果引入Audience Manager的電子郵件地址無法與目的地平台的使用者群中的電子郵件地址相符。

**我會收集客戶的工作電子郵件地址，這些地址與社交網路中使用的個人電子郵件地址不同。如何在多個電子郵件地址之間匹配身份？**

Audience Manager可針對目標平台收集並傳送高達10封電子郵件至目的地平台，但需要透過同步檔案擷取電子郵件地址。Audience Manager將電子郵件地址傳送至目的地平台後，最多可使用平台來比對電子郵件地址與其使用者群。有些平台可能會有其他電子郵件地址圖表，以比對從Audience Manager傳送到使用者描述檔的地址。

## 資料匯出控制 {#data-export-controls}

**[!DNL Data Export Controls][!DNL People-Based Destinations]如何處理？**

[!DNL Data Export Controls] 將封鎖任何包含使用者嘗試傳送之第二方和第三方資料的區段 [!DNL People-Based Destinations]。[!DNL People-Based Destinations] 僅允許使用第一方資料進行定位。[!DNL Data Export Controls] 也會封鎖使用裝置 [!DNL Profile Merge Rules] 圖表的區段。[!DNL People-Based Destinations] 建立適當的資料匯出標籤，且您無法覆寫匯出設定。

## 合作夥伴特定問題 {#partner-specific-questions}

### [!DNL Facebook]

**我必須先做甚麼才能傳送受眾區段[!DNL Facebook]？**

您必須先執行下列設定工作，才能將 [!DNL People-Based Destinations] 對象區段傳送給 [!DNL Facebook]您：

1. 將Adobe Experience Cloud業務帳戶新增為您 [!DNL Facebook Ad Account]的廣告合作夥伴。使用 `business ID=206617933627973`. 如需詳細資訊，請參閱新增合作夥伴給您的業務經理。

   >[!IMPORTANT]
   >
   > 設定Adobe Experience Cloud的權限時，您必須啓用「管理促銷活動」權限。這是 [!DNL People-Based Destinations] 整合的必要項目。

1. 閱讀並簽署 [!DNL Facebook Custom Audiences Terms of Service]。`https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]``accountID`[!DNL Facebook Ad Account ID]要做到這一點，請前往這裡。

**[!DNL People-Based Destinations]是否支援在其他[!DNL Facebook]應用程式中鎖定受眾，[!DNL Instagram]例如**

您可以使用 [!DNL People-Based Destinations] 各種 [!DNL Facebook]受支援的應用程式系列 [!DNL Custom Audiences]，包括 [!DNL Facebook]、 [!DNL Instagram][!DNL Audience Network] 和 [!DNL Messenger]。位於位置層級的應用程式選擇會顯示在位置層級 [!DNL Facebook Ads Manager]。

**[!DNL People-Based Destinations][!DNL Website Custom Audiences]和之間有何差異？**

[!DNL People-Based Destinations] 運用 [!DNL Custom Audiences (CA)] 整合 [!DNL Facebook]。在傳送觀眾時，客戶會使用 [!DNL WCA] 與 [!DNL CA] 整合的差異 [!DNL Facebook]。[!DNL WCA] 使用 [!DNL Facebook] 像素(此為網站使用者ID)， [!DNL People-Based Destinations] 同時使用雜湊電子郵件地址來整合 [!DNL CA]。

您可以使用Audience Manager [!DNL Facebook][!DNL WCA] 的整合 [!DNL URL Destinations] 功能，無需額外付費。

這兩項整合相輔相成；您可以使用這兩者來確保受眾涵蓋率。例如， [!DNL WCA] 可用於預測公司希望鎖定尚未註冊帳戶的網站訪客，但 [!DNL People-Based Destinations] 可幫助您定位已提供電子郵件地址但可能未造訪網站的現有客戶。
