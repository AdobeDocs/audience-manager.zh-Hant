---
description: 目標定位的相關常見疑問與問題。
seo-description: 目標定位的相關常見疑問與問題。
seo-title: 目標定位常見問題集
solution: Audience Manager
title: 目標定位常見問題集
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
feature: Match Rates
translation-type: tm+mt
source-git-commit: 27ce94084e35ffa770858027d12235ca9f1f8430
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 100%

---


# 目標定位常見問題集{#targeting-faq}

目標定位的相關常見疑問與問題。

<br> 

<!-- 

faq_targeting.xml

 -->

**哪裡可以找到 Audience Manager 支援的第三方資料提供者完整清單？**

如需 [!DNL Audience Manager] 所支援第三方資料提供者的完整清單，請參閱 [Adobe Exchange Marketplace](https://exchange.adobe.com/experiencecloud.html)。

<br> 

**為了使用第三方資料將目標定位為我從未在網站上看到的使用者，我是否應在 Audience Manager 或 DSP 中使用第三方資料？**

答案取決於你的目標。例如，如果您的行銷活動目標是尋找具有第三方資料的新客戶，則可直接搭配 DSP 使用。請記得，Audience Manager 只會在我們看到該使用者時，才會與第三方資料提供者同步資料。如果我們以前從未見過某個使用者，我們的系統就沒有該網站訪客的任何資訊。行銷活動若只想使用第三方資料來將目標定位為從未造訪過您任何屬性的使用者，請透過 DSP 建立這些區段。

<br> 

**我可以向個人行銷嗎？**

Audience Manager 可讓您根據共用屬性或特徵，彙總使用者並對其行銷。但是為符合業界法規，[!DNL Audience Manager] 客戶不得將個人識別資訊 (PII) 傳送至我們的系統。因此，您無法使用電子郵件地址、個人姓名、實際地址等資料進行目標定位。

<br> 

**如何安全地持續對資料重新進行目標定位？**

建議您使用伺服器對伺服器連線，與您偏好的重新目標定位平台交換資料。Audience Manager 是透過伺服器對伺服器連線與大部分的主要 DSP 交換資料。伺服器對伺服器的資料傳輸，有助於防止其他有心人士攔截您的資料並轉售該受眾資訊。

<br> 

**Audience Manager 的不重複使用者 ID (UUID) 是否會直接在頁面上以 ID 同步方式繫結至廣告伺服器的不重複使用者 ID？**

不會。網站上的發佈商或伺服器不會在頁面上進行 ID 同步。Audience Manager UUID 會插入廣告伺服器記錄檔的 `u=` 欄位中。當區段傳入以進行目標定位時，就會發生此情況。DIL 程式碼模組會執行此功能。這個機制便是可讓我們將伺服器的使用者 ID 對應至 Audience Manager 使用者，以便製作區段效能報表的機制。不過，如果網站上存在廣告伺服器，便會直接在頁面上同步 ID。

<br> 

**Audience Manager 會將從不同裝置登入的使用者計算為同一個不重複使用者，還是不同的不重複使用者？**

[宣告 ID 目標定位](../features/declared-ids.md#declared-id-targeting)可協助 Audience Manager 使用單一不重複識別碼，跨多部裝置識別訪客。不過從目標定位或目的地角度來看，這仍是 2 (或更多) 位使用者，因為 DSP 無法協調那幾個 ID。

<br> 

**Audience Manager 是否可從顯示器和行動裝置識別使用者。**

是。請參閱[宣告 ID 目標定位](../features/declared-ids.md#declared-id-targeting)。

<br> 

**我是否可使用線上收集的資料對使用者評分，並根據此模型分數重新目標定位？**

是。Audience Manager 可提供資料檔案協助您為使用者評分，但您必須與其他廠商或軟體合作，才能分析和排名此資訊。以索引鍵值配對的形式將此資料傳送至 Audience Manager。我們可將此資訊附加至現有的使用者設定檔中。請聯絡您的合作夥伴解決方案代表以檢閱此程序。

<br> 

**特定 1 至 2 個月期間的 Cookie 刪除率為何？**

Cookie 刪除率很難測量。大部分的 Cookie 刪除都來自少數經常刪除 Cookie 的訪客。即使部分瀏覽器 Cookie 的有效期可能有限，不過大部分的瀏覽器 Cookie 在至少 30 天內都很穩定。一些研究顯示，超過 30 天的漏斗前端目標定位，會在 30 天內有效消除 7% 的瀏覽器目標受眾。如您所知，針對特定創意訊息的 30 天行銷活動是業界標準。以我們的經驗，7% 的降幅是準確的。

Cookie 刪除會對觸及和頻率計算造成不良影響。因此，為了規劃顯示行銷活動而嘗試瞭解消費者趨勢的本質時，我們很看重行為資料的價值。我們的客戶可運用 Audience Manager 區段重疊報表、最佳曝光頻率報表和特定日期範圍的不重複使用者趨勢，以更科學的方式規劃行銷活動以及執行行銷活動的最佳日期範圍。

<br> 

**Audience Manager Cookie 的有效期多長？**

您可透過使用者介面決定 Cookie 的有效期間隔。您可以設定 Cookie 在 *n* 天後過期或永不過期。

<br> 

**在事件呼叫中實作行銷活動創意內容的成本是否更高？**

視情況而定。成本取決於不重複使用者數。如果行銷活動產生淨新使用者，成本便會較高。如果您的行銷活動觸及我們已收集過資料的位置，則無需額外付費。如果您的行銷活動在大幅重疊的相關網站上執行，我們會針對發現的新不重複使用者額外收費。

<br> 

**Audience Manager 只會顯示[!UICONTROL Server-to-Server]目的地的[!UICONTROL Addressable Audiences]量度和符合率。能否說明為什麼我們看不到 Cookie 和 URL 目的地的這些數字嗎？**

追根究柢與 ID 同步有關。針對 [!UICONTROL Server-to-Server] 目的地，我們會以離線方式傳輸資料 (即時或批次)，而且我們需傳送目的地合作夥伴可瞭解的 ID，方便他們將資料對應回瀏覽器。區段可定址數是總區段母體的子集。

至於 Cookie 和 URL 目的地，使用者已在瀏覽器上，而 [!DNL Audience Manager] 傳送的只是該使用者符合資格的區段。目的地合作夥伴只需擷取區段對應並處理該資訊即可。因此，請將 Cookie 和 URL 目的地的符合率一律視為 100%。
