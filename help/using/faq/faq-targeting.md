---
description: 常見的定位相關問題和問題。
seo-description: 常見的定位相關問題和問題。
seo-title: 定位常見問答集
solution: Audience Manager
title: 定位常見問答集
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# 定位常見問答集{#targeting-faq}

常見的定位相關問題和問題。

<br> 

<!-- 

faq_targeting.xml

 -->

**我可以在哪裡找到Audience Manager支援的協力廠商資料提供者完整清單？**

如需支 [援之協力廠商資料供應商的完整清單，請參閱](https://exchange.adobe.com/experiencecloud.html) Adobe Exchange Marketplace [!DNL Audience Manager] 。

<br> 

**為了將我從未在網站上看到的使用者與第三方資料一起定位，我是否應在Audience Manager或DSP中使用第三方資料？**

答案取決於你的目標。 例如，如果您的促銷活動是設計來尋找具有第三方資料的新客戶，則直接與DSP搭配使用。 請記住，Audience Manager只會在我們看到該使用者時，才會與協力廠商資料提供者同步資料。 如果我們以前從未見過使用者，我們的系統將沒有該網站訪客的任何資訊。 對於只想使用協力廠商資料來定位從未造訪過您任何屬性的使用者的促銷活動，請透過DSP建立這些區段。

<br> 

**我可以向個人行銷嗎？**

Audience Manager可讓您根據共用屬性或特徵，將使用者和行銷匯總至他們。 但是，為符合業界法規，客 [!DNL Audience Manager] 戶不得將個人識別資訊(PII)傳送至我們的系統。 因此，您無法使用電子郵件地址、個人名稱、實體地址等。 以進行定位。

<br> 

**如何安全地持續重新鎖定資料？**

我們建議您使用伺服器對伺服器連線，與您偏好的重新定位平台交換資料。 Audience Manager透過伺服器對伺服器的連線，與大部份的主要DSP交換資料。 伺服器間資料傳輸有助於防止其他行為者攔截您的資料並轉售該受眾資訊。

<br> 

**Audience Manager的唯一使用者ID(UUID)是否會直接在頁面上以ID同步方式系結至廣告伺服器的唯一使用者ID?**

不會。網站上的發佈者或伺服器不會在頁面上進行ID同步。 Audience Manager UUID會插入廣告伺服 `u=` 器記錄檔的欄位中。 當群體傳入以進行定位時，就會發生此情況。 DIL代碼模組執行此功能。 這個機制可讓我們將伺服器的使用者ID對應至Audience Manager使用者，以便進行區段效能報告。 不過，如果網站上有廣告伺服器，我們會直接在頁面上同步ID。

<br> 

**Audience Manager是否會將從不同裝置登入的使用者計算為一個獨特使用者或不同的獨特使用者？**

[宣告的ID定位](../features/declared-ids.md#declared-id-targeting) ，可協助Audience Manager使用單一唯一識別碼，在多個裝置間識別訪客。 不過，從目標或目標的角度來看，這仍是2（或更多）位使用者，因為DSP無法協調這些多個ID。

<br> 

**Audience Manager是否可從顯示和行動裝置識別使用者。**

是。請參閱 [宣告的ID定位](../features/declared-ids.md#declared-id-targeting)。

<br> 

**我是否可使用線上收集的資料對使用者評分，並根據此模型分數重新定位？**

是。Audience Manager可提供資料檔案以協助您為使用者評分，但您必須與其他廠商或軟體合作，以分析並排名此資訊。 以索引鍵值配對的形式，將此資料傳送至Audience Manager。 我們可將此資訊附加至現有的使用者設定檔。 請連絡您的合作夥伴解決方案代表以檢閱此程式。

<br> 

**指定1 - 2個月期間的Cookie刪除率為何？**

Cookie刪除很難測量。 大部分的Cookie刪除都來自少數經常刪除Cookie的訪客。 不過，大部分的瀏覽器Cookie至少30天內都是穩定的，即使有些人的期限有限。 一些研究顯示，超過30天的上漏斗定位實際上會在30天內消除7%的瀏覽器目標受眾。 如您所知，針對特定創意訊息的30天促銷活動是業界標準。 從我們所見，7%的降幅是準確的。

刪除Cookie會對觸及和頻率計算造成不利影響。 因此，在嘗試瞭解顯示促銷活動規劃的消費者趨勢的真實性時，我們強調行為資料的價值。 我們的客戶可運用Audience Manager區段重疊報表、最佳曝光頻率報表和特定日期範圍的獨特使用者趨勢，以更科學地規劃促銷活動以及最佳日期範圍以執行促銷活動。

<br> 

**Audience Manager Cookie的有效期為何？**

使用者介面可讓您決定Cookie過期間隔。 您可以設定Cookie在 *n天* 或永不過期。

<br> 

**在事件呼叫中實作促銷活動創意素材的成本是否更高？**

這要看情況。 成本是根據不同使用者而定。 如果促銷活動產生淨新使用者，則是，這會花費更多。 如果您的促銷活動到達我們已收集資料的地方，則無需額外付費。 如果您的促銷活動在重大重疊的相關網站上執行，我們會看到新的獨特使用者需要額外付費。

<br> 

**Audience Manager只會顯[!UICONTROL Addressable Audiences]示目標的量度和比[!UICONTROL Server-to-Server]對率。 您能說明為什麼我們看不到Cookie和URL目的地的這些數字嗎？**

歸結於ID同步。 對於目 [!UICONTROL Server-to-Server] 標，我們會離線傳輸資料（即時或批次傳輸），而且我們需要傳送目標合作夥伴瞭解的ID，以便他們將資料映射回瀏覽器。 區段可定址數是總區段人口的子集。

若是Cookie和URL目的地，使用者已在瀏覽器上，而傳送的 [!DNL Audience Manager] 只是使用者符合的區段。 目標合作夥伴只需擷取區段對應並處理該資訊即可。 因此，請考慮Cookie和URL目的地的比對率一律為100%。
