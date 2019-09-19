---
description: '關於以人為本的目的地的常見問題解答。  '
seo-description: '關於以人為本的目的地的常見問題解答。  '
seo-title: 以人為本的目的地常見問答集
solution: Audience Manager
title: 以人為本的目的地常見問答集
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# 以人為本的目的地常見問答集 {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**我在Audience manager帳[!DNL People-Based Destinations]戶中看不到。 我需要瞭解哪些可用性？**

[!DNL People-Based Destinations] 是Audience manager的優質功能，在購買時可使用。 請連絡您的Adobe銷售代表，以取得有關價格和可用性的詳細資訊。

## 資料上線 {#data-onboarding}

**我要如何將客戶電子郵件地址載入Audience Manager，以便在中使用[!DNL People-Based Destinations]?**

有兩種方式可讓您將離線資料帶入Audience Manager [!DNL People-Based Destinations]。

* **使用檔案式ID同步**。 如需 [ID同步檔案的詳細資訊](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ，請參閱ID同步檔案的名稱和內容需求。 使用此方法時，您可以定位資料庫中所有雜湊的電子郵件地址 [!DNL CRM] 。
* **在傳入已驗證的客戶ID** 時，使用「宣告的ID」來宣告雜湊的電子郵件地址。 使用此方法時，Audience manager只會啟動已線上驗證之使用者的雜湊電子郵件地址。 透過Facebook啟動的電子郵件地址只是宣告的ID事件呼叫中的電子郵件地址。 與客戶ID關聯的其他電子郵件地址不會即時啟用。

**我是否可透過網頁表單或行動應用程式收集雜湊的電子郵件地址，或者必須透過批次檔案進行？**

您可以使用Declared ID透過Web驗證收集雜湊 [!DNL ECID] 的電 [子郵件地址](../features/declared-ids.md)。 此批次檔案也可讓您收集無法透過驗證傳送的雜湊電子郵件地址(例如，您的([!DNL CRM])目的地中的休眠使用者)，並啟用這些地址。

**透過Web表單擷取雜湊電子郵件地址與透過批次檔案上傳雜湊電子郵件地址有何不同？**

離線資料擷取可支援不使用驗證的使用案例，而且提供在所有離線描述檔上執行、不考慮驗證的新描述檔合併規則([!UICONTROL All Cross-Device Profiles]) [!DNL CRM] ，做為一部分 [!DNL People-Based Destinations]。 此方法旨在補充從線上來源擷取已驗證受眾的功能。

**我可以傳送／更新雜湊電子郵件地址的最大頻率是多少？**

* 使用Declared ID時，Audience manager會即時將雜湊的電子郵件地址傳送至目的地。
* 透過ID同步檔案擷取資料時，Audience manager會每日處理資料。

**如何得知電子郵件地址雜湊是否正確？**

Audience manager未擷取原始電子郵件地址，我們無法驗證雜湊是否正確。 如需 [如何散列已登入資料的詳細資訊](../features/destinations/people-based-destinations-prerequisites.md) ，請參閱先決條件和考量事項。

## 描述檔合併規則 {#profile-merge-rules}

**我是否有新的描述檔合併規則可搭配使用[!DNL People-Based Destinations]?**

是。購買的客 [!DNL People-Based Destinations] 戶也可存取新的描述檔合併規則，以便離線劃分。 此規則會被呼 [!DNL All Cross-Device Profiles] 叫，並用於僅離線分段。 當您註冊時，這 [!DNL People-Based Destinations]是除了三個現有的驗證型規則外，您還可以建立的第四個描述檔合併規則。

**我是否必須複製現有的觀眾區隔，才能在中啟動它們[!DNL People-Based Destinations]?**

這取決於您的使用案例。 如果您打算在以人為本的管道中啟用現有的第一方區段，則不需要建立新區段。 您只需將區段對應至以人為本的目的地。

如果您打算在以人為本的管道中啟用新的離線對象，則需要使用合併規則建立新的第 [!DNL All Cross-Device Profiles] 一方區段。
>[!NOTE]
>
> 您只能將具有第一方資料的區段對應至 [!DNL People-Based Destinations]。 我們的目標平台不接受含有第二方和第三方資料的細分。

## 比對率 {#match-rates}

**是否[!DNL People-Based Destinations]可洞悉比賽率或可定址的受眾？**

不會。傳送對象區段至時， [!DNL People-Based Destinations]對象比對會在合作夥伴端進行。 Adobe無權存取這些量度。 Audience manager會顯示每個目的地的最大可分享對象數以及屬於某個區段的即時人員計數。 這些資訊可協助您進行促銷活動規劃和預測。

**理論上來說，使用比[!DNL People-Based Destinations]較其他將觀眾傳送至目的地平台的方法，如何比對比率？**

只要電子郵件地址已正確雜湊並收錄，與其他方法的比對率就 [!DNL People-Based Destinations] 不會有差異。 相符率低於100%的唯一原因是，如果傳入Audience manager的電子郵件地址無法與目標平台使用者群中的電子郵件地址相符。

**我會收集客戶的工作電子郵件地址，這些地址與社交網路中使用的個人電子郵件地址不同。 如何在多個電子郵件地址間比對身分？**

Audience manager可收集並傳送每位使用者最多10封電子郵件至目標平台，但電子郵件位址需透過同步檔案擷取。 當Audience manager將電子郵件地址傳送至目標平台後，必須由平台將電子郵件地址與自己的使用者群相符。 某些平台可能會有其他電子郵件地址圖表，以比對從Audience manager傳送的位址與使用者個人檔案。

## 資料匯出控制 {#data-export-controls}

**如何[!DNL Data Export Controls]使用[!DNL People-Based Destinations]?**

[!DNL Data Export Controls] 將封鎖使用者嘗試傳送至之任何包含第二方與第三方資料的區段 [!DNL People-Based Destinations]。 [!DNL People-Based Destinations] 只允許使用第一方資料進行定位。 [!DNL Data Export Controls] 也可以使用裝置圖 [!DNL Profile Merge Rules] 形來封鎖區段。 [!DNL People-Based Destinations] 會以已勾選的適當資料匯出標籤建立，而且您無法覆寫匯出設定。

## 合作夥伴特定問題 {#partner-specific-questions}

### [!DNL Facebook]

**我需要做什麼才能傳送對象區段至[!DNL Facebook]?**

您必須先執行下 [!DNL People-Based Destinations] 列設定工作，才能 [!DNL Facebook]使用來傳送對象區段至：

1. 將Adobe Experience cloud商業帳戶新增為您的廣告合作夥伴 [!DNL Facebook Ad Account]。 使用 `business ID=206617933627973`. 如需詳細資訊，請參閱將合作夥伴新增至您的業務經理。

   >[!IMPORTANT]
   >
   > 設定Adobe Experience cloud的權限時，您必須啟用「管理促銷活動」權限。 這是整合的必 [!DNL People-Based Destinations] 要項。

1. 閱讀並簽署 [!DNL Facebook Custom Audiences Terms of Service]。 若要這麼做，請前 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`往您的 `accountID` 位置 [!DNL Facebook Ad Account ID]。

**是否支[!DNL People-Based Destinations]援其他應用程式中的受[!DNL Facebook]眾定位，例如[!DNL Instagram]?**

您可以跨 [!DNL People-Based Destinations] 應用程 [!DNL Facebook]式系列使用，包括 [!DNL Custom Audiences]、 [!DNL Facebook][!DNL Instagram]和 [!DNL Audience Network][!DNL Messenger]。 在中的位置層級會指出您要針對哪個應用程式執行促銷活動 [!DNL Facebook Ads Manager]。

**和之間有何差[!DNL People-Based Destinations]異[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] 利用與的 [!DNL Custom Audiences (CA)] 整合 [!DNL Facebook]。 客戶將觀眾傳 [!DNL WCA] 送給 [!DNL CA] 對象時，使用的關鍵是整合與整合的差異 [!DNL Facebook]。 [!DNL WCA] 使用 [!DNL Facebook] 像素（可能是網站使用者ID），同時使 [!DNL People-Based Destinations] 用雜湊電子郵件地址與整合 [!DNL CA]。

您可以透過此功能使用Audience manager [!DNL Facebook] 的整 [!DNL WCA] 合，而 [!DNL URL Destinations] 不需額外付費。

這兩者相輔相成，您可以使用兩者來確保受眾覆蓋率更高。 例如，當公 [!DNL WCA] 司想要定位尚未註冊帳戶的網站訪客時，可用來進行勘察，但 [!DNL People-Based Destinations] 可協助您定位已提供電子郵件地址但可能未造訪網站的現有客戶。
