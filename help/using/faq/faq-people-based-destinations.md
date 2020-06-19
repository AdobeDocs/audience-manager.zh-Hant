---
description: '以人物為基礎的目的地相關常見問題解答。  '
seo-description: '以人物為基礎的目的地相關常見問題解答。  '
seo-title: 以人物為基礎的目的地常見問題集
solution: Audience Manager
title: 以人物為基礎的目的地常見問題集
translation-type: ht
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316
workflow-type: ht
source-wordcount: '1105'
ht-degree: 100%

---


# 以人物為基礎的目的地常見問題集 {#people-based-destinations-faq}

[!DNL People-Based Destinations] 相關常見問題解答。

## 可用性 {#availability}

**我在 Audience Manager 帳戶中看不到[!DNL People-Based Destinations]。關於可用性，我需要瞭解什麼？**

[!DNL People-Based Destinations] 是 Audience Manager 的付費功能，購買後即可使用。請聯絡您的 Adobe 銷售代表，取得有關定價和可用性的詳細資訊。

## 資料上線 {#data-onboarding}

**我要如何將客戶電子郵件地址帶入 Audience Manager 中，以便用於[!DNL People-Based Destinations]？**

有兩種方式可將離線資料帶入 Audience Manager 中以用於[!DNL People-Based Destinations]。

* **使用檔案式 ID 同步**。如需 ID 同步檔案的詳細資訊，請參閱 [ID 同步檔案的名稱和內容要求](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)。使用此方法時，您可以鎖定 [!DNL CRM] 資料庫中的所有雜湊電子郵件地址。
* 傳入已驗證的客戶 ID 時，**使用宣告 ID** 來宣告雜湊的電子郵件地址。使用此方法時，Audience Manager 只會啟用已在線上通過驗證的使用者之雜湊電子郵件地址。透過 Facebook 啟用的電子郵件地址只是宣告 ID 事件呼叫中的電子郵件地址。與客戶 ID 相關聯的其他電子郵件地址不會即時啟用。

**我是否可透過 Web 表單或行動應用程式收集雜湊電子郵件地址，還是必須透過批次檔案進行？**

您可以使用 [!DNL ECID] 搭配[宣告 ID](../features/declared-ids.md) 透過 Web 驗證收集雜湊電子郵件地址。批次檔案也可讓您收集無法透過驗證傳送的雜湊電子郵件地址 (例如您 [!DNL CRM] 中的休眠使用者)，並在以人物為基礎的目的地啟用這些地址。

**透過 Web 表單擷取雜湊電子郵件地址，與透過批次檔案上傳雜湊電子郵件地址有何不同？**

離線資料擷取的用意是支援不進行驗證的使用案例，且現在提供包含在 [!DNL People-Based Destinations] 中的新設定檔合併規則 ([!UICONTROL All Cross-Device Profiles])，可在不考慮驗證的所有離線 [!DNL CRM] 設定檔上執行。此方法的目的是補充從線上來源擷取已驗證受眾的功能。

**我最常可以多久傳送/更新雜湊電子郵件地址一次？**

* 使用宣告 ID 時，Audience Manager 會將雜湊電子郵件地址即時傳送至目的地。
* 透過 ID 同步檔案擷取資料時，Audience Manager 會每天處理資料。

**如何知道電子郵件地址雜湊是否正確？**

Audience Manager 不會擷取原始電子郵件地址，且無法驗證雜湊是否正確。如需如何雜湊已上線資料的詳細資訊，請參閱[必要條件和考量事項](../features/destinations/people-based-destinations-prerequisites.md)。

## 設定檔合併規則 {#profile-merge-rules}

**是否有新的設定檔合併規則可搭配[!DNL People-Based Destinations]使用？**

是。已購買 [!DNL People-Based Destinations] 的客戶也可存取新的設定檔合併規則，用於進行離線細分。[!DNL All Cross-Device Profiles] 會呼叫此規則，並用於僅限離線的細分。您註冊 [!DNL People-Based Destinations] 時，除了三個現有的驗證型規則外，這是您可以建立的第四個設定檔合併規則。

**是否必須複製現有的受眾區段，才能在[!DNL People-Based Destinations]中啟用它們？**

這取決於您的使用案例。如果您打算在以人物為基礎的管道中啟用現有的第一方區段，則不需要建立新區段。您只需將區段對應至以人物為基礎的目的地即可。

如果您打算在以人物為基礎的管道中啟用新的離線受眾，則需要使用 [!DNL All Cross-Device Profiles] 合併規則建立新的第一方區段。
>[!NOTE]
>
> 您只能將具有第一方資料的區段對應至 [!DNL People-Based Destinations]。我們的目的地平台不接受含有第二方和第三方資料的區段。

## 符合率 {#match-rates}

**[!DNL People-Based Destinations]是否可顯示符合率或可定址的受眾？**

不會。將受眾區段傳送至 [!DNL People-Based Destinations] 時，會在合作夥伴端進行受眾比對。Adobe 無權存取這些量度。Audience Manager 會顯示每個目的地的最大可共用受眾數，以及屬於某個區段的即時人員數量。這些資訊可協助您規劃和預測行銷活動。

**理論上來說，相較於其他將受眾傳送至目的地平台的方法，使用[!DNL People-Based Destinations]時符合率有何不同？**

只要電子郵件地址已正確雜湊並擷取，使用 [!DNL People-Based Destinations] 與其他方法的符合率就不會有差異。符合率低於 100% 的唯一原因是，傳入 Audience Manager 的電子郵件地址，無法與目的地平台使用者群中的電子郵件地址比對成功。

**我會收集客戶的工作電子郵件地址，這些地址與社交網路中使用的個人電子郵件地址不同。如何在多個電子郵件地址間識別身分？**

Audience Manager 可收集每位使用者的最多 10 個電子郵件地址並傳送至目的地平台，但電子郵件地址需透過同步檔案擷取。Audience Manager 將電子郵件地址傳送至目的地平台後，平台必須自行比對這些電子郵件地址與自己的使用者群。某些平台可能會有其他電子郵件地址圖表，用於將 Audience Manager 所傳來的地址與使用者設定檔進行比對。

## 資料匯出控制 {#data-export-controls}

**如何搭配[!DNL People-Based Destinations]使用[!DNL Data Export Controls]？**

[!DNL Data Export Controls] 會封鎖使用者嘗試傳送至 [!DNL People-Based Destinations] 且任何包含第二方與第三方資料的區段。[!DNL People-Based Destinations] 只允許使用第一方資料進行目標定位。[!DNL Data Export Controls] 也可以使用 [!DNL Profile Merge Rules] 搭配裝置圖形來封鎖區段。建立 [!DNL People-Based Destinations] 時會使用已勾選的適當資料匯出標籤，且您無法覆寫匯出設定。

## 針對合作夥伴的問題 {#partner-specific-questions}

### [!DNL Facebook]

**需要做什麼才能將受眾區段傳送至[!DNL Facebook]？**

您必須先執行下列設定工作，才能使用 [!DNL People-Based Destinations] 將受眾區段傳送至 [!DNL Facebook]：

1. 將 Adobe Experience Cloud 商業帳戶新增為您 [!DNL Facebook Ad Account] 中的廣告合作夥伴。使用 `business ID=206617933627973`。如需詳細資訊，請參閱「將合作夥伴新增至您的 Business Manager 中」。

   >[!IMPORTANT]
   >
   > 設定 Adobe Experience Cloud 的權限時，您必須啟用「管理行銷活動」權限。這是進行 [!DNL People-Based Destinations] 整合的必要權限。

1. 閱讀並簽署 [!DNL Facebook Custom Audiences Terms of Service]。若要完成此操作，請前往 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`，其中 `accountID` 是您的 [!DNL Facebook Ad Account ID]。

**[!DNL People-Based Destinations]是否支援其他[!DNL Facebook]應用程式 (例如[!DNL Instagram]) 中的受眾目標定位？**

您可以在 [!DNL Facebook] 旗下 [!DNL Custom Audiences] 所支援的應用程式中使用 [!DNL People-Based Destinations]，包括 [!DNL Facebook]、[!DNL Instagram]、[!DNL Audience Network] 和 [!DNL Messenger]。在 [!DNL Facebook Ads Manager] 中的廣告版位層級會指出您選擇針對哪個應用程式執行行銷活動。

**[!DNL People-Based Destinations]和[!DNL Website Custom Audiences]之間有何差異？**

[!DNL People-Based Destinations] 可運用 [!DNL Custom Audiences (CA)] 與 [!DNL Facebook] 的整合。客戶將受眾傳送至 [!DNL Facebook] 時，運用 [!DNL WCA] 與 [!DNL CA] 整合之間的差異是關鍵所在。[!DNL WCA] 使用 [!DNL Facebook] 像素 (可能是網站使用者 ID)，而 [!DNL People-Based Destinations] 使用雜湊電子郵件地址來與 [!DNL CA] 整合。

您可以透過 [!DNL URL Destinations] 功能使用 Audience Manager 的 [!DNL Facebook] [!DNL WCA] 整合，不需額外付費。

這兩項整合相輔相成，您可以同時使用兩者來確保受眾涵蓋範圍更廣。例如，公司想要將目標定位為尚未註冊帳戶的網站訪客時，可使用 [!DNL WCA] 進行勘察，而 [!DNL People-Based Destinations] 可協助您將目標定位為已提供電子郵件地址但可能未造訪網站的現有客戶。
